# let var const 关键字

最早的时候只存在 var

ES6 新增了 let const



**作用域**

ES5 只有全局作用域和函数级作用域，ES6 新增块级作用域



## var

1. 没有块级作用域的概念

   ```js
   // Global Scope
   {
     var a = 10;
   }
   console.log(a); // 10
   ```

2. 有全局作用域和函数级作用域的概念

   ```js
   var a = 10;
   function checkscope() {
     // Local Scope
     var b = 20;
     console.log(a); // 10
     console.log(b); // 20
   }
   checkscope();
   console.log(b); // error: not defined
   ```

3. 不初始化，默认为 undefined

4. 变量提升

   ```js
   console.log(a); // undefined
   var a = 10;
   
   // 相当于
   
   var a;
   console.log(a);
   a = 10;
   ```

5. 全局作用域会被挂载到 window 上

   ```js
   var a = 10;
   console.log(a); // 10
   console.log(window.a); // 10
   ```

6. 同一作用域允许重复声明

   ```js
   var a = 10;
   var a = 20;
   console.log(a); // 20
   ```

   

## let - ES6 新增

1. 有块级作用域的概念

   ```js
   {
   	let a = 10;
   }
   console.log(a); // error: not defined
   ```

2. 不会变量提升
3. 暂时性死区

​	let/const 变量在声明（初始化）前没办法被使用

4. 不允许作用域重复声明



## const - ES6 新增

1. 必须立即初始化

   ```js
   const a; // error
   
   const b = 10;
   ```

2. 常量的值不能改变

   ```js
   const a = 10;
   a = 20; // error
   ```

   



















