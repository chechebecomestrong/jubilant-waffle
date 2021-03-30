---
description: Event到底是个啥
---

# Event简述

 Event在MDN中在Web API中，因此是是接口。

 Event接口表示DOM中发生的事件。

####  事件的触发

1、用户操作触发，比如点击事件、键盘事件

2、由API生成，比如音视频资源的播放、暂停事件

3、通过脚本代码触发，通过代码把目标元素的事件、方法派发到指定的目标地

 有许多不同类型的事件，其中一些使用基于Event接口的其他接口，Event本身包含适用于所有事件的属性和方法。

 有一些DOM元素需要被设计成可以接受或者监听事件，并且执行代码去响应或处理它们。可以使用EventTarget.addEventListener\(\)方法可以将事件处理函数绑定到不同的HTML元素上，比如&lt;button&gt;，&lt;div&gt;等。这种绑定事件处理函数的方式基本替换了老版本中使用的HTML的事件处理属性（注：这里的属性是attribute）。通过正确的使用removeEventListener\(\)方法，这些事件处理函数也能被移除。

 一个元素可以绑定多个事件处理函数，甚至是同一种类型的事件。尤其是这种分离的，并且相互独立的代码模块对同一个元素绑定事件处理函数，每一个模块都有这独立的目的。

 当嵌套了很多的元素，并且每一个严肃都有着自己的事件处理函数，事件处理过程会变得非常复杂。尤其当一个父元素和子元素绑定有相同类型的事件处理函数的时候。因为结构上的重叠，事件处理函数可以回依次被触发，触发的顺序取决于事件冒泡和事件捕获在每一个元素上的设置情况。

 基于Event的接口：所有的时间接口都是以Event结尾的。

#### 构造器

Event\(\)

创建并返回一个Event对象

####  属性

| 属性名 | 属性类型 | 值类型 | 说明 |
| :--- | :--- | :--- | :--- |
| Event.bubbles | 只读 | 布尔值 | 表示该时间是否会在DOM中冒泡 |
| Event.cancelBubble |  | 布尔值 | Event.stopPropagation\(\)的历史别名。在事件处理器函数返回之前，将此属性的值设置为true，也可以阻止事件继续冒泡 |
| Event.canclable | 只读 | 布尔值 | 表示事件是否可以取消 |
| Event.composed | 只读 | 布尔值 | 表示时间是否可以穿过shadow DOM和常规DOM之间的隔阂进行冒泡 |
| Event.currentTarget | 只读 | 对象（引用） | 对时间当前注册的目标的引用。这是一个当前计划将时间发送到的对象。很可能在重定向的过程中被改变。 |
| Event.deepPath |  | 数组 | 一个由事件流所经过的DOM节点组成的数组 |
| Event.defaultPrevented | 只读 | 布尔值 | 表示event.preventDefault\(\)方法是否取消了事件的默认行为 |
| Event.eventPhase | 只读 |  | 表示事件流正被处理到了哪个阶段 |
| Event.explicitOriginalTarget | 只读 | Mozilla专有属性 | 事件明确的原始目标 |
| Event.originalTarget | 只读 | Mozilla专有属性 | 重设目标前的事件原始目标 |
| Event.returnValue |  |  | 旧版IE引入的一个非标准历史属性，为保证依赖属性的网页正常运作，此属性最终被收入规范。可用Event.preventDefault\(\)与Event.defaultPrevented代替，但由于已进入规范，也可使用此属性 |
| Event.target | 只读 |  | 对事件原始目标的引用，这里的原始目标指最初派发（dispatch）事件时指定的目标 |
| Event.timeStamp | 只读 | 毫秒 | 事件创建的时间戳（精度为毫秒）。按照规范，这个时间戳是Unix纪元起经过的毫秒数，但实际上，在不同的浏览器中，对此时间戳的定义也有所不同。另外，规范整将其修改为DOMHighResTimeStamp（一个double类型，用于存储毫秒级的时间值。这种类型可以用来描述离散的时间点或者一段时间） |
| Event.type | 只读 |  | 事件的类型，不区分大小写 |
| Event.isTrusted | 只读 |  | 表示事件是由浏览器（比如用户点击）发起的，还是由脚本（使用事件创建方法）发出的 |

