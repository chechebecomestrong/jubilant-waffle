---
description: 在移动端飞速发展的时代，来一波对PC时期指针的怀旧
---

# 指针状态——cursor

### css预置样式

在PC发展的时期，css中提供了指针的多种状态。虽然，现在已经有了很多形形色色的图标状态。不得不说，在标准中，css支持的状态还是很多的。

{% embed url="https://codepen.io/chechebecomestrong/pen/NWbgNNZ" caption="CodePen示例" %}

### 自定义指针样式

&lt;`url`&gt;`url(…)`或者逗号分隔的`url(…), url(…), …`，指向图片文件。用大于一个[`<url>`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/url)值提供后备，以防某些指针图片类型不被支持。最后必须提供一个非URL后备值。详情参见[cursor属性中使用URL值](https://developer.mozilla.org/en-US/docs/CSS/Using_URL_values_for_the_cursor_property)。

`<x>` `<y>`可选 x，y坐标。两个小于32的无单位非负数。

比如：下面的例子使用&lt;url&gt;值指定两个图像，为第二个图像提供&lt;x&gt;&lt;y&gt;坐标，如果两个图像都无法加载，则返回`progress`关键字值

```text
cursor: url(one.svg), url(two.svg) 5 5, progress;
```

