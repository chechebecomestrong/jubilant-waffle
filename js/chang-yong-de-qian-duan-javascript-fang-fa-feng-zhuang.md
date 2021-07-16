# 常用的前端JavaScript方法封装

1、输入一个值，返回数据类型

```javascript
function type(para) {
    return Object.prototype.toString.call(para)
}
```

2、数组去重

```javascript
function unique(arr) {
    return [...new Set(arr)]
}
```

```javascript
function unique(arr) {
    var obj = {}
    return arr.filter(ele => {
        if(!obj[ele]) {
            obj[ele] = true
            return true
        }
    })
}
```

```javascript
function unique(arr) {
    var result = []
    arr.forEach(ele=>{
        if(result.indexOf(ele) == -1) {
            result.push(ele)
        }
    })
    return result
}
```

3、字符串去重

```javascript
String.prototype.unique = function() {
    var obj = {}
    var str = ''
    var len = this.length
    for(var i = 0; i < len; i++) {
        if(!obj[this[i]]) {
            str =+ this[i]
            obj[this[i]] = true
        }
    }
    return str
}
```

4、去除连续的字符串

```javascript
function uniq(str) {
    return str.replace(/(\w)\1+/g, $1)
}
```

5、深拷贝

6、浅拷贝

7、reverse

8、圣杯模式的继承

9、找出字符串中第一次只出现一次的字母

10、找元素的第n级父元素

11、返回元素的第n个兄弟节点

12、封装mychildren，解决浏览器的兼容问题

13、判断元素有没有子元素

14、把一个元素插入到另一个元素的后面

15、返回当前的时间

16、获得滚动条的滚动距离

17、获得视口的尺寸

18、获取任一元素的任意属性

19、绑定事件的兼容代码

20、解绑事件

21、取消冒泡的兼容代码

22、检验字符串是否是回文

23、



