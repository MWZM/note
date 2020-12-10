#### 数组部分

**1**  遍历数组：就是把数组的元素从头到尾都访问一次

**2 ** 数组长度：用length将数组中的字符个数打印出来

             注意点1.(数组长度是元素的个数  不要和索引号混淆）
    
             注意点2：（length可以进行动态检测数组元素的个数）

**3**在进行for循环时   数组元素为arr[i]  而不是计数器i

**4**数组新增元素：1.可以通过修改length属性进行数组扩容

                 2.通过修改索引号(相当于追加数组元素）比较常用   如果索引号已经被占用，则会将之前的元素进行替换
    
                 3.不要直接给数组名赋值，否则会直接将之前的数组直接覆盖

**5**数组排序（冒泡排列）：是一种算法，把一系列的数据按照一定的顺序进行排列显示

**6**函数：封装了一段可以被重复调用的代码块，目的是为了让大量代码重复使用

    (1) 函数的使用：函数的使用分为两步
    
      .1-声明函数
    
      .2-调用函数：通过调用函数名来执行代码
    
      .3-匿名函数的作用是用于闭包和避免全局变量的污染以及函数名的冲突

**7**函数的封装：函数封装是把一个或者多个功能通过   函数的方式  封装起来，对外只提供一个简单的函数接口

**8**函数的参数： 参数的作用：在函数内部某些值不能固定，可以通过参数在调用参数时传递不同的值进去

        形参和实参
    
            1.形参：在声明函数的小括号里面的是形参    形参相当于一个变量
    
            2.实参：在函数调用的小括号里面    在调用时会将形参进行覆盖



**9**函数的返回值： return    函数只是实现某种功能，最终结果需要返回给函数的调用者  函数名（）  通过return来实现的

                  renturn： 不仅可以退出循环，还能返回结果，同时也可以结束当前函数体内的代码
    
                  只返回一个值
    
                  没有的话返回undefined



2020/10/22

#### 函数部分（js第四天）



##### **一**、函数

    arguments：函数内部内置对象
    
        伪数组：
    
            像数组 但是不是数组，具有数组的某些特性
    
            （有长度，可以通过索引值取出来其中包括的数据）
    
        其中包括了所有传入的实参,可以通过索引值取出来其中的实参
    
    函数声明的两种方式
    
        1) function 函数名(){ }
    
        2) var 变量名 = function(){}
    
        注意：
    
            1)方式声明的函数，在声明前后都可以调用
    
            2)表达式声明的函数，只能在声明之后调用

##### **二**、作用域

    全局作用域：整个页面
    
    局部作用域：一个函数(只有在函数调用的时候才能产生局部作用)

##### **三**、变量

    全局变量：在全局作用域中声明的变量、未声明即赋值的变量
    
        全局变量的使用范围：在全局作用域的任何位置都可以使用
      
    局部变量：在局部作用域中声明的变量、形参
    
        局部变量的使用范围：在当前局部作用域中使用

##### **四**、作用域链

    操作某个变量时，会从当前作用域开始依次向上层作用域中查找该变量
    
    （若全局作用域中也没有：如果是取值操作会报错，如果是赋值操作会把当前变量当做全局变量）

##### **五**、预解析

    浏览器执行js代码时，会让当前作用域中某部分代码（声明部分：声明变量、声明函数）先执行
    
            声明变量：var 变量;
    
            声明函数：function 函数名(){}
    注意：
            先提升var  再提升function
    
            在任一作用域开始执行代码的时候都会先去预解析

##### **六**、对象

数据的集合，给每一个存储的数据起一个名字

    创建对象：
    
            对象的字面量：{}
    
            new Object()
    
            var obj = {}; 创建了一个空对象
    
            var obj = new Object(); 创建了一个空对象
    
    对象的属性的使用
    
            对象.属性名
    
    对象的方法的使用
    
            对象.方法名()
    
    修改对象的属性和方法：
    
            对象.原属性名 = 新数据
    
            对象.原方法名 = 新函数体
    
    为对象添加新属性和方法：
    
            对象.新属性名 = 新数据
    
            对象.新方法名 = 新函数体



2020/10/23

#### 函数部分（js第五天）

##### **一**、构造函数

    构造函数：创建对象的函数（构造函数的名称一般第一个字母大写）
    
    构造函数的常规结构：
    
        function Star(starName, starAge, starSex) {               
            this.name = starName;
            this.age = starAge;                                       
            this.sex = starSex;
        }
        new Star


        构造函数的名称一般第一个字母大写
    
    构造函数的使用方式
    
        new Star("刘德华",20,"男")
    
    new的作用
    
        1、在函数代码执行之前，创建了一个空对象，并且把this指向该对象（隐式）
    
        2、正常执行函数代码
    
        3、在函数代码执行结束之后，返回this（隐式）





##### **二**、遍历对象

    for(var 变量 in 对象){
    
        变量表示对象属性名（是一个字符串）
    
        对象[变量]
    }

##### **三**、内置对象

    Math对象
    
        PI：圆周率
        max(): 求最大值
        min(): 求最小值
        abs(): 取绝对值
        floor(): 向下取整  往最小了取值  取更小的整数
        ceil(): 向上取整  往最大了取值  取更大的整数
        round(): 四舍五入  其他数字都是四舍五入  .5 特殊 取更大的数
        random(): 取随机值 返回值是 0-1之间的小数  [0,1)  取不到1
            获取指定区间的随机整除
                function getRandom(min, max) {
                    return Math.floor(Math.random() * (max - min + 1)) + min;
                }
     
    Date构造函数
    
        创建日期对象：new Date(日期参数)
    
            1、如果创建的时候没有设置参数，得到的日期对象记录的是当前时间
            2、可以传入一个时间格式的字符串  得到记录指定时间的日期对象
            3、可以传入若干数字  注意：月份从0开始  0-1月  1-2月

​        

#####         日期对象的方法：

​    

            获取年份：getFullYear()
            获取月份：getMonth()
            获取几号：getDate()
            获取星期：getDay()
            获取小时：getHours()
            获取分钟：getMinutes()
            获取秒钟：getSeconds()


        获取总毫秒数：
    
            日期对象.valueOf()  
            日期对象.getTime()
            +日期对象
            Date.now()
    
    数组的操作
    
        创建数组的方式：
    
            var arr = new Array();
            参数：
                一个参数 —— 设置数组的长度    var arr = new Array(2)
                多个参数 —— 设置数组的内容    var arr = new Array(2,3,4,5)
    
        检测是否是数组：
    
            instanceof 用于判断一个变量是否某个对象的实例
    
            Array.isArray(数据)
    
              返回值是true——是数组   返回值是false——不是数组


2020/10/24

#### 字符串部分（js初级最后一天）

#####  <1>增加和减去数组中的元素  

      减去数组最后一个  pop 
      删除第一个  shift
      添加数组   push 添加在第一个
                unshift 添加在最后一个

##### <2>数组的颠倒和排序

       将数组颠倒  arr.reverse（）
       将数组进行排序  arr.sort(function(a, c) {
                              return a - c}

##### <3>查找数组中的索引  arr.indexof（）

                    indexof 是从前往后进行查找的 如果后面有重复的则不进行后面的输出
                    如果没有当前插找的元素 则输出值为-1 
                    indexOf用来查找元素索引
                    arr.indexOf('h', 5)
                    lastindexof（）
                    是从后往前进行查找的 如果后面有重复的则不进行后面的输出
                           数组去重是用indexof和push进行联合使用
                    includes判断是否存在   存在为true   不存在为false
        转换字符串  arr.tostring（）
                    arr.join可以在数组中添加分隔符

##### <4>根据位置判断字符位置  str[索引值]  这是h5新增标签

       str.charAt(索引值)   照顾低版本浏览器

##### <5> 截取字符串  

```
str.substr（参数1，参数2） 进行截取字符串  第一个参数是开始的位置  第二个参数是截取的个数
```

##### <6> replace

```
 进行字符替换  只能替换一个  str.replace('被替换部分', '新的部分')
```



##### <7> split  

```
将字符串进行分割  分割为数组的形式   str.split(',')
```



#### <8> str . padStart(3, 0) 

```
用来判断字符串够不够第一个参数的值， 够的话就不进行操作， 不够的话则会在前面添加第二个参数
```





常见一些事件

**鼠标点击事件**onclick

**鼠标按下事件**onmousedown

**鼠标抬起事件**onmouseup

**鼠标移动事件**onmousemove

**鼠标经过事件**onmouseover

**鼠标离开事件**onmouseout

**获取光标事件**onfocus 

**失去光标事件**onblur

**键盘按下事件**keydown（按下就开始执行）   keyup（放开后开始执行)





#### **异步事件**： 事件(click,focus等等)，定时器(setTimeout和setInterval)，ajax,都是会触发异步



###   **Web API 第一天**



   document.getElementsByTagName

      1.element.getElementsByTagName()  可以得到这个元素里面的某些标签
    
      2.返回的是 获取过来元素对象的集合 以伪数组的形式存储的
    
      3.我们想要依次打印里面的元素对象我们可以采取遍历的方式

   getElementsByClassName 根据类名获得某些元素集合

   querySelector 返回指定选择器的第一个元素对象  切记 里面的选择器需要加符号 .box  #nav

   querySelectorAll()返回指定选择器的所有元素对象集合



#### <2>事件三要素

   1. 事件是有三部分组成  事件源  事件类型  事件处理程序   我们也称为事件三要素

     (1) 事件源 事件被触发的对象   谁  按钮
    
     (2) 事件类型  如何触发 什么事件 比如鼠标点击(onclick) 还是鼠标经过 还是键盘按下
    
     (3) 事件处理程序  通过一个函数赋值的方式 完成

#### <3> innerText 和 innerHTML的区别 

     1. innerText 不识别html标签 非标准  去除空格和换行
    
     2. innerHTML 识别html标签 W3C标准 保留空格和换行的
    
          这两个属性是可读写的  可以获取元素里面的内容

#### <4>className的使用

    1. 使用 element.style 获得修改元素样式  如果样式比较少 或者 功能简单的情况下使用
    
    2. 我们可以通过 修改元素的className更改元素的样式 适合于样式较多或者功能复杂的情况
    
    3. 如果想要保留原先的类名，我们可以这么做 多类名选择器



###    Web API 第二天





##### <1>获取属性 element.getAttribute('属性')

   我们程序员自己添加的属性我们称为自定义属性 在用 getAttribute进行获取

##### <2> 移除属性 removeAttribute(属性) 

   举例：div.removeAttribute('index');

##### <3> element.setAttribute('属性', '值');  主要针对于自定义属性

  可以添加属性

##### <4>节点

 1. 父节点 parentNode

   var box = document.querySelector('.box');

    得到的是离元素最近的父级节点(亲爸爸) 如果找不到父节点就返回为 null

 2. 子节点  childNodes 所有的子节点 包含 元素节点 文本节点等等

     children 获取所有的子元素节点 也是我们实际开发常用的

        console.log(ul.children);

###    Web API 第三天

##### <1>节点操作之删除节点

   1. 获取元素

   2. 删除元素  node.removeChild(child)

        3. 点击按钮依次删除里面的孩子

##### <2>克隆节点

   1. node.cloneNode(); 括号为空或者里面是false 浅拷贝 只复制标签不复制里面的内容

   2. node.cloneNode(true); 括号为true 深拷贝 复制标签复制里面的内容

##### <3>三种创建元素方式区别

   1. document.write() 创建元素  如果页面文档流加载完毕，再调用这句话会导致页面重绘

   2. innerHTML 创建元素

   3. document.createElement() 创建元素

##### <4>注册事件

   1. 传统方式注册事件

   2. 事件侦听注册事件  addEventListener 

      (1) 里面的事件类型是字符串 必定加引号 而且不带on

      (2) 同一个元素 同一个事件可以添加多个侦听器（事件处理程序）

   3. attachEvent ie9以前的版本支持

##### <5>删除事件

   1. 传统方式删除事件

   2. removeEventListener 删除事件

##### <6>dom事件流执行过程

######    dom 事件流 三个阶段

        1. JS 代码中只能执行捕获或者冒泡其中的一个阶段。
    
        2. onclick 和 attachEvent（ie） 只能得到冒泡阶段。
    
        3. 捕获阶段 如果addEventListener 第三个参数是 true 那么则处于捕获阶段  document -> html -> body -> father -> son
    
        var son = document.querySelector('.son');
        son.addEventListener('click', function() {
            alert('son');
        }, true);
        var father = document.querySelector('.father');
        father.addEventListener('click', function() {
            alert('father');
        }, true);
    
        4. 冒泡阶段 如果addEventListener 第三个参数是 false 或者 省略 那么则处于冒泡阶段  son -> father ->body -> html -> document

##### <7> 事件对象

   1. event 就是一个事件对象 写到我们侦听函数的 小括号里面 当形参来看

   2. 事件对象只有有了事件才会存在，它是系统给我们自动创建的，不需要我们传递参数

   3. 事件对象 是 我们事件的一系列相关数据的集合 跟事件相关的 比如鼠标点击里面就包含了鼠标的相关信息，鼠标坐标啊，如果是键盘事件里面就包含的键盘事件的信息 比

如 判断用户按下了那个键

   4. 这个事件对象我们可以自己命名 比如 event 、 evt、 e

   5. 事件对象也有兼容性问题 ie678 通过 window.event 兼容性的写法  e = e || window.event;

##### <8>常见事件对象的属性和方法

   1. e.target 返回的是触发事件的对象（元素）  this 返回的是绑定事件的对象（元素）

      区别 ： e.target 点击了那个元素，就返回那个元素 this 那个元素绑定了这个点击事件，那么就返回谁

     e.target 指向我们点击的那个对象 谁触发了这个事件 我们点击的是li e.target 指向的就是li

##### <9>阻止事件的默认行为   e.preventDefault()

   阻止默认行为（事件） 让链接不跳转 或者让提交按钮不提交

   传统方法  return  false

##### <10>阻止事件冒泡

   e.stopPropagation();

##### <11>事件委托

  事件委托的核心原理：给父节点添加侦听器， 利用事件冒泡影响每一个子节点

   优点：1.减少时间绑定次数

         2.可以进行动态的注册事件

   e.target 这个可以得到我们点击的对象

##### <12>鼠标事件对象

  1. client 鼠标在可视区的x和y坐标

  2. page 鼠标在页面文档的x和y坐标

  3. screen 鼠标在电脑屏幕的x和y坐标



### Web API 第四天

##### <1>键盘事件

  1. keyup 按键弹起的时候触发 

  2. keydown 按键按下的时候触发  能识别功能键 比如 ctrl shift 左右箭头啊

  3. keypress 按键按下的时候触发  不能识别功能键 比如 ctrl shift 左右箭头啊

##### <2>  键盘事件对象中的keyCode属性可以得到相应键的ASCII码值

      我们可以利用keycode返回的ASCII码值来判断用户按下了那个键

##### <3>Bom顶级对象

      window.document.querySelector()

##### <4>windown 常见事件

   1. ```
         1. window.onload = function(){}
            
            load 等页面内容全部加载完毕，包含页面dom元素 图片 flash  css 等等
            
         2. DOMContentLoaded 是DOM 加载完毕，不包含图片 falsh css 等就可以执行 加载速度比 load更快一些
      ```

      

##### <5>调整窗口大小

      resize

##### <6>定时器

```
      1. setTimeout

  语法规范：  window.setTimeout(调用函数, 延时时间);

      1. 这个window在调用的时候可以省略

      2. 这个延时时间单位是毫秒 但是可以省略，如果省略默认的是0

      3. 这个调用函数可以直接写函数 还可以写 函数名 还有一个写法 '函数名()'

      4. 页面中可能有很多的定时器，我们经常给定时器加标识符 （名字)
```



##### <7>清除定时器

      clearTimeout(); 括号里面放定时器的名字

##### <8> 循环定时器

    setInterval 
    
    语法规范：  window.setInterval(调用函数, 延时时间);
    
    2. setTimeout  延时时间到了，就去调用这个回调函数，只调用一次 就结束了这个定时器
    
    3. setInterval  每隔这个延时时间，就去调用这个回调函数，会调用很多次，重复调用这个函数

##### <9> 清除循环定时器

   clearInterval（定时器的变量名）

##### <10>this指向问题

   一般情况下this的最终指向的是那个调用它的对象  除过构造函数和箭头函数

   方法调用中谁调用this指向谁

##### <11>location常见的方法

          href  当前url内容
    
          hash  锚点
    
          search  表单提交内容
    
          port  获取端口


  记录浏览历史，所以可以实现后退功能

  location.assign()

  不记录浏览历史，所以不可以实现后退功能

  location.replace()

##### <12>navigator 对象

      navigator.userAgent: 当前浏览器的相关信息

##### <13>history对象

      history.forward()返回上一层
    
      history.go（）可以返回上一层或者下一层
    
      history.back返回下一层

##### <14>offset系列

	offsetLeft
	
		元素距离页面左边的距离，如果父元素是定位的，则是距离父元素的距离
	
	offsetTop
	
		元素距离页面顶部的距离，如果父元素是定位的，则是距离父元素的距离
	
	offsetWidth  获取当前元素宽度
	
		wdth + 2 padding + 2border
	
	offsetHeight  获取当前元素高度
	
		height + 2 padding + 2 border



   补充的知识点

   prop操作html元素的固有属性

   arrt操作html中一些自定义的属性