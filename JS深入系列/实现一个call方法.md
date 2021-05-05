首先我们要清楚call是用来做什么的

mdn文档:`**call()**` 方法使用一个指定的 `this` 值和单独给出的一个或多个参数来调用一个函数。

因此我们可以明确一件事，call方法是给函数的一个方法，因此我们有了实现call方法的第一步。

就是在Funcation.prototype上定义一个方法，用于函数实例的调用.

接下来就要实现这个方法了。

```javascript
Funcation.prototype.myCall = funcation(){
	
}
```

如何实现呢？

那我们先看看call方法是如何使用的，再去实现这个方法。

1.指定this

2.给出一个或多个参数来调用一个函数

我们先来完成第一步

给这个方法一个this

```javascript
Funcation.prototype.myCall = funcation(context){
	context = context || window;
    // this 本身是一个 Funcation 实例
    context[fn] = this;
    
    
}
```

call 实现过程

1. 将函数设为对象的属性
2. 执行该函数
3. 删除该函数