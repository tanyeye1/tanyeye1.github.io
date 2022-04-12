---
title: js

---

==

1.是否有NaN
首先判断双等号两边是否有NaN，如果有的话，则一律返回false。

2.是否有boolean值
如果有的话则将true转化为1，false转化为0。

3.null和undefined
遇到null或者undefined，则不会进行类型转换，它们相互的比较都返回true。

4.有一边是字符串

分四种情况：

1） 同样是字符串，则直接进行字符串值的比较

2） 是数字，则需要将字符串转化为数字，然后进行比较

3） 有布尔类型，则要将布尔类型转化为0或则1，然后进行比较

4） 对象或者数组类型，则需要调用toString()或者valueOf()方法转化成简单类型，然后进行比较

### ===  先比较类型，类型不同直接为false，如-0和+0 ， NaN 和 Number.NaN

### Object.is( )  满足以下条件则两个值相等:

- 都是 [`undefined`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/undefined)
- 都是 [`null`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/null)
- 都是 `true` 或 `false`
- 都是相同长度的字符串且相同字符按相同顺序排列
- 都是相同对象（意味着每个对象有同一个引用）
- 都是数字且
  - 都是 `+0`
  - 都是 `-0`
  - 都是 [`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN)
  - 或都是非零而且非 [`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN) 且为同一个值

### 箭头函数和普通函数的区别

 + 写法不同

 + this指向不同（普通函数的this执行环境不同而不同，箭头函数的this指向的是离他最近的执行环境）

 + 普通函数可以被new实例化，箭头函数不可以

 + 普通函数可以被声明提前，箭头函数不可以

   

### 回流和重绘

	+ 某个子元素样式发生改变，直接影响到了其父元素以及往上追溯很多祖先元素（包括兄弟元素），这个时候浏览器要重新去渲染这个子元素相关联的所有元素的过程称为回流。
	+ 如果只是改变某个元素的背景色、文 字颜色、边框颜色等等不影响它周围或内部布局的属性，将只会引起浏览器 repaint（重绘）。
	+ repaint 的速度明显快于 reflow

### 闭包

	+ 原理：函数嵌套函数，通过函数内的函数访问局部变量的规则，实现外部访问函数内的变量。
	+ 特点：函数嵌套函数、函数内部可以引用函数外部的参数和变量、参数和变量不会被垃圾回收机制回收。
	+ 优点：保护变量安全，实现封装，防止变量声明冲突和全局污染。在内存当中维持一个变量，可以做缓存。匿名函数自执行函数可以减少内存消耗。
	+ 缺点：变量会驻留在内存中，造成内存损耗问题。解决办法：把闭包函数设置为 null 。内存泄漏
	+ 经典应用：防抖和节流

### 数组扁平化

	+ 原理：将多维数组变为一维数组
	+ 方法：