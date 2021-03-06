#### 块级作用域

- 暂时性死区问题：

  **1**. **let** 声明的变量只在块级作用域内生效

  **2**. **let **声明的变量不存在变量提升的问题

  - 例如：

  ```javascript
  console.log(num);
  let num = 10 //这里会报错
  ```

     **3**.**暂时性死区**

  -  只要块级作用域内存在`let`命令，它所声明的变量就相当于 “绑定” 这个区域，不再受外部的影响。 (但是只有**let** 在声明与外部变量名相同的情况下才会出现暂时性死区，如果改变变量名称则不会出现 **暂时性死区**)

  ```javascript
    let x = 10;
          let foo = () => {
              console.log(x);//这里会报错
              let x = 20;
              x++;
          }
          foo();
  ```

  -  `ES6` 明确规定，如果区块中存在`let`和`const`命令，这个区块对这些命令声明的变量，从一开始就形成了封闭作用域。凡是在声明之前就使用这些变量，就会报错。 

    ```javascript
    function bar(x = y, y = 2) {
      return [x, y];
    }
    
    bar(); // 报错
    
    function bar(x = 2, y = x) {
      return [x, y];
    }
    bar(); // [2, 2]
    ```

    - 上面代码中之所以报错是因为 `x`还变量未被定义就去等于参数 `y`，但此时 `y`还为被定义，这时就属于 **死区** ，如果 `x` 已经提前声明就不会就行报错 ，例如第二段代码

  -  暂时性死区的本质就是，只要一进入当前作用域，所要使用的变量就已经存在了，但是不可获取，只有等到声明变量的那一行代码出现，才可以获取和使用该变量。 

   **4**. 块级作用域内不允许重复声明变量

  

  #### **为什么要使用块级作用域呢**？

  由于 `ES5` 中只有全局作用域以及函数作用域，带来了诸多不合理的地方

  1. 内层变量可能会覆盖外层变量

     ```javascript
     var tmp = new Date();
     
     function f() {
       console.log(tmp);
       if (false) {
         var tmp = 'hello world';
       }
     }
     
     f(); // undefined
     ```

     - 上面代码中 `if` 代码块外部存在 `tmp` 由于变量提升，所以最终输出为undefined

  2. 一些变量可能会被泄露，成为全局变量

     ```javascript
     var s = 'hello';
     
     for (var i = 0; i < s.length; i++) {
       console.log(s[i]);
     }
     
     console.log(i); 
     ```

     

