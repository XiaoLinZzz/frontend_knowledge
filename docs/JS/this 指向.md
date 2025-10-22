# this 指向

> 谁调用它，this就指向谁

this 指向的规律：

- 在函数体中，非显式或隐式地简单调用函数时，在严格模式下，函数内的 this 会被绑定到 undefined 上，在非严 格模式下则会被绑定到全局对象 window/global 上。
- 一般使用 new 方法调用构造函数 时，构造函数内的 this 会被绑定到新创建的对象上。
- 一般通过 call/apply/bind 方法显式调用函数时，函数体内的 this 会被绑定到指定参数的对象上。
- 一般通过上下文调用函数时，函数体内的 this 会被绑定到该对象上。
- 在箭头函数中，this 的指向是由外层（函数或全局）作用域来决定的。



## 全局对象中的 this

```js
// 以普通函数形式调用 -> 返回全局对象 global/window
function fn1() {
    console.log(this); // 指向全局对象
}
fn1();

// 严格模式
function fn2() {
    'use strict'
    console.log(this); // undefined
}
fn2();

// ----------------

var foo = {
    bar: 10,
    fn: function () {
        console.log(this);
        console.log(this.bar);
    }
}

var fn = foo.fn;
fn();      // this -> global
foo.fn();  // this -> foo 对象
```



## 上下文中调用 this

```js
var stu = {
    name: "test",
    son: {
        name: "test son",
        fn: function () {
            console.log(this.name); // this -> stu.son
        }
    }
}

stu.son.fn() // test son
```



比较复杂的示例：

```javascript
var o1 = {
    text: 'o1',
    fn: function () {
        return this.text;
    }
}

var o2 = {
    text: 'o2',
    fn: function () {
        return o1.fn();
    }
}

var o3 = {
    text: 'o3',
    fn: function () {
        var fn2 = o1.fn;
        return fn2(); // 这里this指向全局对象
    }
}

console.log(o1.fn()); // o1
console.log(o2.fn()); // o1
console.log(o3.fn()); // undefined
```



## 改变 this 指向

### *call, apply, bind* 方法

#### call()

call 方法的第一个参数，应该是 ***对象***

	1. 如果参数为 *空/null/undefined*，就是指向全局
	1. 如果参数不是一个对象，会自动包装成对象

```js
var obj = {
    name: "test"
}
function test() {
    return this;
}
console.log(test());  // this 指向全局
console.log(test.call(obj)) // this 指向obj
console.log(test.call(true)) // 回把 true 包装成一个对象
```

后续的参数时一个参数列表，会传递给前面的方法。

```js
function showDetails(age, job) {
    console.log(this.name + " is " + age + job);
}

const person1 = {
    name: "Alice"
};

const person2 = {
    name: "Bob"
};

// 其中第二个和第三个参数就会被当成 showDetails 的参数被传递进去
showDetails.call(person1, 28, 'doctor');
showDetails.call(person2, 25, 'developer');

// apply 方法
showDetails.apply(person1, [28, 'doctor']);
showDetails.apply(person2, [25, 'developer']);

```



#### apply()

apply 和 call 作用类似，改变 this 指向，但是区别是 apply 接收数组作为函数执行时的参数。

```
func.apply(thisValue, [arg1, arg2, ...])
```



同过 apply 把类数组对象转换成数组

```js
let obj = {
    0: 1,
    1: 2,
    2: 3,
    length: 3
}

console.log(Array.prototype.slice.apply(obj));
```



#### bind()

bind() 返回一个函数  

```js
var counter = {
    count: 0,
    add() {
        this.count++;
    }
}

var obj = {
    count: 100
}

// 这里改变了 add() 里面的 this 指向，绑定到了 obj
var fn = counter.add.bind(obj); 
fn();

// counter.add();
console.log(counter.count); // 0
console.log(obj.count);     // 101
```

   

## 箭头函数

箭头函数的 this 指向始终是外层作用域

```javascript
var x = 20;
var obj = {
    x: 10,
    fn: () => {
        console.log(this);   // {  }
        console.log(this.x); // undefined (浏览器运行是 20)
    }
}

obj.fn();
```

















