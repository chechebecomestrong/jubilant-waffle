---
description: 虽然有些废弃的属性，有些浏览器还在兼容，建议不使用Event废弃的属性和方法
---

# Event非标准的属性和方法

#### 废弃属性

| 废弃属性 | 标准属性 | 说明 |
| :--- | :--- | :--- |
| Event.scoped | Event.composed | 一个布尔值，表示给定的时间是否会穿过ShadowDOM，进入到标准DOM |
| Event.srcElement | Event.target | 旧IE版本对Event.target的非标准别称。由于兼容原因，一些其他浏览器也支持别称 |
|  |  |  |

#### 废弃方法

| 废弃方法 | 标准 | 说明 |
| :--- | :--- | :--- |
|  Event.getPreventDefault\(\) | Event.defaultPrevented属性 | 返回Event.defaultPrevented的值 |
| event.preventBubble | event.stopPropagation | 阻止事件继续冒泡 |
| event.preventCapture | event.stopPropagation | 阻止事件继续冒泡 |
| Event.initEvent\(\) | Event\(\) | 创建自定义事件。该特性已经从Web标准中删除，虽然一些浏览器目前仍然支持。可以使用特定的event构造器函数，比如Event\(\) |



