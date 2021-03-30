---
description: HTMLCollection与NodeList
---

# children与childNodes

### ParentNode.children

ParentNode.children是一个只读属性，返回这个Node的子元素，是一个动态更新的集合，是一个**`HTMLCollection`**。

### Node.childNodes

Node.childNodes返回包含指定节点的字节点的集合，该集合为即时更新的集合，返回值是**`NodeList`**类型，只读。

### HTMLCollection

`HTMLCollection`接口表示一个包含了元素（元素顺序为文档流中的顺序）的通用几何，还提供了用来从该集合中选择元素的方法和属性。

注意：由于历史原因（DOM4之前，实现该接口的结合只能包含HTML元素），该接口被称为`HTMLCollection`

HTML DOM中的`HTMLCollection`是即时更新的，当其所包含的文档结构发生改变时，会自动更新

#### 属性

length（只读）

#### 方法

`HTMLCollection.item()`

根据给定的索引（从0开始），返回具体的节点。如果索引超出了范围，则返回null

`HTMLCollection.namedItem()`

根据id返回指定节点，或者作为备用，根据字符串所表示的name属性来匹配。根据name匹配只能作为最后的依赖，并且只有当被引用的元素支持name属性时才能被匹配。如果不存在符合给定的name的节点，则返回null

当使用字符串作为 namedItem 的参数，且匹配的元素多于一个时，不同的浏览器表现不同。Firefox 8 表现如同 DOM 2 和 DOM 4 说明的，返回第一个匹配的元素。而 Webkit 浏览器和 IE 返回另外一个 HTMLCollection，Opera 返回一个包含所有元素的NodeList

#### 使用

在JavaScript中，可直接用方括号语法

```text
var elem1, elem2;

// document.forms 是一个 HTMLCollection

elem1 = document.forms[0];
elem2 = document.forms.item(0);

alert(elem1 === elem2); // 显示 "true"

elem1 = document.forms["myForm"];
elem2 = document.forms.namedItem("myForm");

alert(elem1 === elem2); // 显示 "true"
```

### NodeList

`NodeList`对象是节点的集合，通常是由属性（如Node.childNodes）和方法（如document.querySelectorAll）返回的

NodeList不是一个数组，而是一个类数组（like Array Object）。可以通过数组的相关方法把NodeList转换为数组

#### Node.childNodes返回的是实时集合

如果文档中的节点数发生变化，NodeList也会随之变化。

#### 其他情况下，NodeList是一个静态集合。

意味着随后对文档对象模型的任何改动都不会影响集合的内容，比如document.querySelectorAll\(\)的返回值是不变的。

#### 属性

`NodeList.length`

NodeList中包含的节点个数

#### 方法

`NodeList.item()`

返回NodeList对象中指定索引的节点，如果索引越界，则返回null。等价的写法是nodeList\[i\]，不过这样写的情况下，越界访问会返回undefined。

`NodeList.entries()`

返回一个iterator，允许代码遍历结合中包含的所有键值对（键是从0开始的数字，而值是节点）

`NodeList.forEach()`

每个NodeList元素执行一次提供的函数，然后将该元素作为参数传递给函数

`NodeList.keys()`

返回一个iterator，允许代码遍历集合中包含的键值对的所有键（键是从0开始的数字）

`NodeList.values()`

返回iterator允许代码遍历结合中包含的键值对的所有值的代码

#### NodeList的循环

可以使用for循环遍历NodeList对象中的所有节点

不要用for...in或者for each...in遍历NodeList对象中的元素，如果把length和item属性也看成element对象的话，NodeList对象中的length和item属性也会被遍历出来，这可能会导致脚本运行出错。而且，for...in不能保证访问这些属性的顺序。

提倡用for...of。for...of会正确遍历NodeList对象

浏览器也支持一些遍历方法，比如 `forEach()` 与 `entries()`、`values()`、和 `keys()`。

也有一种使用数组 `Array` 的 `Array.prototype.forEach` 来遍历 `NodeList` 的方法，这种方法兼容 Internet Explorer ：

```text
var list = document.querySelectorAll('input[type=checkbox]');
Array.prototype.forEach.call(list, function (checkbox) {
  checkbox.checked = true;
});
```

{% hint style="info" %}
一些需要注意的点
{% endhint %}

为什么NodeList不是数组

NodeList对象在某些方面和数组非常相似，看上去可以直接使用从Array.prototype上集成度额方法。然而，除了forEach方法，NodeList没有类似数组的方法。

JavaScript的继承机制是基于原型的。

数组元素之所有有一些数组方法（比如forEach和map），是因为它的原型链上有这些方法，如下：

myArray--&gt;Array.prototype--&gt;Object.prototype--&gt;null

NodeList的原型链是这样的

myNodeList--&gt;NodeList.prototype--&gt;Object.prototype--&gt;null

  








