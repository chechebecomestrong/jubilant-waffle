---
description: 在移动端飞速发展的时代，来一波对PC时期指针的怀旧
---

# 指针状态——cursor

### 指针状态

 在PC发展的时期，css中提供了指针的多种状态。

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="chechebecomestrong" data-slug-hash="NWbgNNZ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="css cursor">
  <span>See the Pen <a href="https://codepen.io/chechebecomestrong/pen/NWbgNNZ">
  css cursor</a> by Yully Che (<a href="https://codepen.io/chechebecomestrong">@chechebecomestrong</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>




<div class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="chechebecomestrong" data-slug-hash="NWbgNNZ" data-prefill='{"title":"css cursor","tags":[],"scripts":[],"stylesheets":[]}'>
  <pre data-lang="html">&lt;a href="https://developer.mozilla.org/zh-CN/docs/Web/CSS/cursor">MDN-cursor&lt;/a>
&lt;div class="piece">
 1、指针下有可用内容目录&lt;div class="cursor context-menu">context-menu&lt;/div>
&lt;/div>
&lt;div class="piece">
 2、提示帮助&lt;div class="cursor help">help&lt;/div>
&lt;/div>
&lt;div class="piece">
 3、指针变成小手&lt;div class="cursor pointer">pointer&lt;/div>
&lt;/div>
&lt;div class="piece">
 4、响应进程中，可交互&lt;div class="cursor progress">progress&lt;/div>
&lt;/div>
&lt;div class="piece">
 5、响应进程中，不可交互&lt;div class="cursor wait">wait&lt;/div>
&lt;/div>
&lt;div class="piece">
 6、指示单元格可被选中&lt;div class="cursor cell">cell&lt;/div>
&lt;/div>
&lt;div class="piece">
 7、交叉指针，通常指示位图中的框选&lt;div class="cursor crosshair">crosshair&lt;/div>
&lt;/div>
&lt;div class="piece">
 8、文字可被选中&lt;div class="cursor text">text&lt;/div>
&lt;/div>
&lt;div class="piece">
 9、垂直文字可被选中&lt;div class="cursor vertical-text">vertical-text&lt;/div>
&lt;/div>
&lt;div class="piece">
 10、复制或快捷方式将要被创建&lt;div class="cursor alias">alias&lt;/div>
&lt;/div>
&lt;div class="piece">
 11、可复制&lt;div class="cursor copy">copy&lt;/div>
&lt;/div>
&lt;div class="piece">
 12、可移动&lt;div class="cursor move">move&lt;/div>
&lt;/div>
&lt;div class="piece">
 13、不能执行&lt;div class="cursor not-allowed">not-allowed&lt;/div>
&lt;/div>
&lt;div class="piece">
 14、放大&lt;div class="cursor zoom-in">zoom-in&lt;/div>
&lt;/div>
&lt;div class="piece">
 15、缩小&lt;div class="cursor zoom-out">zoom-out&lt;/div>
&lt;/div>
</pre>
  <pre data-lang="css">.piece + .piece {
  margin-top: 15px;
}
.cursor {
  display: inline-block;
  margin: 0 0 0 5px;
  padding: 5px;
  border: 1px solid transparent;
  outline: none; 
  background-color: lightblue;
  border-radius: 6px;
}
.context-menu {
  cursor: context-menu;
}
.help {
  cursor: help
}
.pointer {
  cursor: pointer
}
.progress {
  cursor: progress
}
.wait {
  cursor: wait
}
.cell {
  cursor: cell
}
.crosshair {
  cursor: crosshair
}
.text {
  cursor: text
}
.vertical-text {
  writing-mode:vertical-lr;
  cursor: vertical-text;
}
.alias {
  cursor: alias;
}
.copy {
  cursor: copy;
}
.move {
  cursor: move;
}
.not-allowed {
  cursor: not-allowed;
}
.zoom-in {
  cursor: zoom-in;
}
.zoom-out {
  cursor: zoom-out;
}
</pre></div>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
