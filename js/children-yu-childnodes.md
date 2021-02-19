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

意味着随后对文档对象模型的任何改动都不会影响集合的内容。

属性

NodeList.length

NodeList中包含的节点个数

方法

NodeList.item\(\)

返回NodeList对象中指定索引的节点，如果索引越界，则返回null





