---
layout: post
title: bind、call、apply函数的区别及几种常见用法
date: 2022-04-12
tags: "#bind, #call, #apply"
categories: ["面试合集","零散的知识点积累"]
---

#### 讲区别之前，先讲一下三者的共同点：
> 1. 都是用来改变函数的this对象的指向的。
> 2. 第一个参数都是this要指向的对象。
> 3. 都可以利用后续参数传参。

#### 三者的区别：
> 1. call/apply都是对函数的直接调用。二者传参有区别。 <br/> call(this,arg1,arg2,...)  /  apply(this,[arg1,arg2,...])
> 2. bind函数返回的还是一个函数。【后面写一个bind函数的实现】<br/> bind(thisArgs, arg1, arg2, ...)

&nbsp;

#### 1. 先来说说bind函数

#### bind函数的几种常见用法：

##### 1. 偏函数。使一个函数拥有预设的初始参数。

```javascript
function add(x, y){
    console.log('x+y', x+y)
}
var add1 = add(1,2) // x+y 3

var add2 = add.bind(null,100)
add2(1,2) // x+y 100+1 = 101  第二个参数2无效
```

##### 2. 改变this指向

```javascript
// 在默认情况下，使用 window.setTimeout() 时，this 关键字会指向 window （或 global）对象。
// 当类的方法中需要 this 指向类的实例时，你可能需要显式地把 this 绑定到回调函数，就不会丢失该实例的引用。
function Test(){
    this.x = 1
}
Test.prototype.boom = function(){
    window.setTimeout(this.declare.bind(this), 1000)
}
Test.prototype.declare = function(){
    console.log(this.x, this)
}
var test = new Test()
test.boom() // 1 Test{x: 1}
```

#### 来实现一个简易的bind函数，需要注意的是，bind函数返回的还是一个函数：

```javascript
// 简易实现
Function.prototype.myBind = function(context){
    var self = this
    return function(){
        // 把当前函数(调用myBind方法的函数)的this，指向myBind的第一个参数对象的this
        self.apply(context)
    }
 }

 var obj = {x: 1}
 var fun = function(){
     console.log(this.x)
 }.myBind(obj)
 fun() // 1

```
