# JavaScript

**JavaScript是什么**

JavaScript 是一种脚本，一门编程语言，它可以在网页上实现复杂的功能，网页展现给你的不再是简单的静态信息，而是实时的内容更新，交互式的地图，2D/3D 动画，滚动播放的视频等等。

**JavaScript可以干什么**

> 嵌入动态文本于HTML页面
> 对浏览器事件作出响应
> 读写HTML元素
> 在数据被提交到服务器之前验证数据
> 检测访客的浏览器信息
> 控制cookie，包括创建和修改等
>                                                                    -- [JavaScript - 维基百科](https://zh.wikipedia.org/zh-hans/JavaScript)

[试一试 ](jQuery learn\demo.html)

## HTML

**超文本标记语言**（英语：**H**yper**T**ext **M**arkup **L**anguage，简称：**HTML**）是一种用于创建[网页](https://zh.wikipedia.org/wiki/网页)的标准[标记语言](https://zh.wikipedia.org/wiki/标记语言)。[浏览器](https://zh.wikipedia.org/wiki/网页浏览器)可以读取HTML文件，并将其渲染成可视化网页。HTML描述了一个网站的结构语义随着线索的呈现，使之成为一种标记语言而非[编程语言](https://zh.wikipedia.org/wiki/编程语言)。


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>文档标题</title>
    <link rel="stylesheet" type="text/css" href="mystyle.css">
    <style type="text/css">
      body {background-color:yellow}
      p {color:blue}
    </style>
    <script>
        
    </script>
  </head>
  <body>
    <p>这是用户看到的页面</p>
  </body>
</html>
```

## CSS

**层叠样式表**（英语：**C**ascading **S**tyle **S**heets，缩写：**CSS**）是一种用来为结构化文档（如[HTML](https://zh.wikipedia.org/wiki/HTML)文档或[XML](https://zh.wikipedia.org/wiki/XML)应用）添加样式（字体、间距和颜色等）的计算机语言。

### 导入方式

#### 外部样式表

```html
<link rel="stylesheet" href="styles.css">
```

```css
@charset "UTF-8";

body {
    font-family: 'Comic Sans MS', cursive;
}
th {
    font-size: 40px;
    font-style: italic;
}

```

#### 内部样式表

```html
<style>
    body {
        font-family: 'Comic Sans MS', cursive;
    }
    th {
        font-size: 40px;
        font-style: italic;
    }
</style>
```

#### 内联样式(不推荐)

```html
<h1 style="color: blue;">Hello World!</h1>
<h1 style="color: black;">Hello World!</h1>
```

**除非你有充足的理由，否则不要这样做！**它难以维护（在需要更新时，你必须在修改同一个文档的多处地方），并且这种写法将文档结构和文档表现混合起来了，这使得代码变得难以阅读和理解。将不同类型的代码分开存放在不同的文档中，会让我们的工作更加清晰。

### 选择器

#### [元素选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Type_selectors)**（**[Type selector](https://wiki.developer.mozilla.org/en-US/docs/Web/CSS/Type_selectors)**）**

按照给定的节点名称，选择所有匹配的元素。
**语法：**`elementname`
**例子**：`span`匹配任何 <span>元素。


```html
span {
  background-color: DodgerBlue;
  color: #ffffff;
}

<span>这里是由 span 包裹的一些文字.</span>
```

#### [类选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Class_selectors)**（**[Class selector](https://wiki.developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors)**）**

按照给定的 `class` 属性的值，选择所有匹配的元素。
**语法**：`.classname`
**例子**：`.index` 匹配任何 `class` 属性中含有 "index" 类的元素。


```html
.classy {
  background-color: grey;
}

<span class="classy">Here's a span with some text.</span>
```

#### [ID 选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/ID_selectors)（[ID selector](https://wiki.developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors)）

按照 `id` 属性选择一个与之匹配的元素。需要注意的是，一个文档中，每个 ID 属性都应当是唯一的。
**语法：**`#idname`
**例子：**`#toc` 匹配 ID 为 "toc" 的元素。


```html
#identified {
  background-color: DodgerBlue;
}

<span id="identified">Here's a span with some text.</span>
<span>Here's another.</span>
```

#### [属性选择器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Attribute_selectors)（[Attribute selector](https://wiki.developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)）

按照给定的属性，选择所有匹配的元素。
**语法：**`[attr]` `[attr=value]` `[attr~=value]` `[attr|=value]` `[attr^=value]` `[attr$=value]` `[attr*=value]`
**例子：**`[autoplay]` 选择所有具有 `autoplay` 属性的元素（不论这个属性的值是什么）。


```html
a[title] {
  color: purple;
}

<a title="test">Jump to </a>
```

#### [组合器（Combinators）](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Selectors#组合器（combinators）)

##### [后代组合器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Descendant_combinator)（[Descendant combinator](https://wiki.developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator)）

  （空格）组合器选择前一个元素的后代节点。 

  **语法：**`A B` 

  **例子：**`div span` 匹配所有位于任意`<div> `元素之内的 `<span>` 元素。


  ```html
  a span {
    color: DodgerBlue;
  }
  
  <a>
    <span>Item 1</span>
  </a>
  ```

##### [直接子代组合器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Child_combinator)（[Child combinator](https://wiki.developer.mozilla.org/en-US/docs/Web/CSS/Child_combinator)）

  `>` 组合器选择前一个元素的直接子代的节点。 

  **语法**：`A > B` 

  **例子**：`ul > li` 匹配直接嵌套在`<ul>`元素内的所有`<li>`元素。


```html
  a > span {
    color: DodgerBlue;
  }

  <a>
    <span>Item 1</span>
  </a>
```
##### [一般兄弟组合器](https://developer.mozilla.org/zh-CN/docs/Web/CSS/General_sibling_combinator)（[General sibling combinator](https://wiki.developer.mozilla.org/en-US/docs/Web/CSS/General_sibling_combinator)）

  `~` 组合器选择兄弟元素，也就是说，后一个节点在前一个节点后面的任意位置，并且共享同一个父节点。 

**语法**：`A ~ B` 

**例子**：`p ~ span` 匹配同一父元素下，`<p>`元素后的所有`<span>`元素。


```html
  p > span {
    color: DodgerBlue;
  }

  <a>
    <p>11</p>
    <span>Item 1</span>
  </a>
```

#### [伪选择器（Pseudo）](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Selectors#伪选择器（pseudo）)

##### [伪类](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Pseudo-classes)

  `:` 伪选择器支持按照未被包含在文档树中的状态信息来选择元素。 

  **例子：**`a:visited` 匹配所有曾被访问过的`<a>`元素。

[试一试 ](jQuery learn\css-demo-selector.html)

### 冲突规则

#### [导入顺序](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance#层叠)

Stylesheets **cascade（样式表层叠）** — 简单的说，css规则的顺序很重要；当应用两条同级别的规则应用到一个元素的时候，写在后面的就是实际使用的规则。

下面的例子中，我们有两个关于 `h1` 的规则。`h1` 最后显示蓝色 — 这些规则有相同的优先级，所以顺序在最后的生效。

```html
h1 { 
    color: red; 
}
h1 { 
    color: blue; 
}
```
#### [优先级](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance#优先级)

一个选择器的优先级可以说是由四个部分相加 (分量)，可以认为是个十百千 — 四位数的四个位数：

1. **千位**： 如果声明在 [`style`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes#attr-style) 的属性（内联样式）则该位得一分。这样的声明没有选择器，所以它得分总是1000。
2. **百位**： 选择器中包含ID选择器则该位得一分。
3. **十位**： 选择器中包含类选择器、属性选择器或者伪类则该位得一分。
4. **个位**：选择器中包含元素、伪元素选择器则该位得一分。

| 选择器                                    | 千位 | 百位 | 十位 | 个位 | 优先级 |
| :---------------------------------------- | :--- | :--- | :--- | :--- | :----- |
| `h1`                                      | 0    | 0    | 0    | 1    | 0001   |
| `h1 + p::first-letter`                    | 0    | 0    | 0    | 3    | 0003   |
| `li > a[href*="en-US"] > .inline-warning` | 0    | 0    | 2    | 2    | 0022   |
| `#identifier`                             | 0    | 1    | 0    | 0    | 0100   |
| 内联样式                                  | 1    | 0    | 0    | 0    | 1000   |

#### [!important](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance#!important)

有一个特殊的 CSS 可以用来覆盖所有上面所有优先级计算，不过需要很小心的使用 — `!important`。用于修改特定属性的值， 能够覆盖普通规则的层叠。

[试一试 ](jQuery learn\css-demo-primary.html)

### Layout布局

### [标准盒模型](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/The_box_model#标准盒模型)

在 CSS 中，所有的元素都被一个个的“盒子（box）”包围着，理解这些“盒子”的基本原理，是我们使用CSS实现准确布局、处理元素排列的关键。

CSS中组成一个块级盒子需要:

- **Content box**: 这个区域是用来显示内容，大小可以通过设置 [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width) 和 [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height).
- **Padding box**: 包围在内容区域外部的空白区域； 大小通过 [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding) 相关属性设置。
- **Border box**: 边框盒包裹内容和内边距。大小通过 [`border`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border) 相关属性设置。
- **Margin box**: 这是最外面的区域，是盒子和其他元素之间的空白区域。大小通过 [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin)属性设置。

![Diagram of the box model](https://mdn.mozillademos.org/files/16558/box-model.png)

### [替代（IE）盒模型](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/The_box_model#替代（ie）盒模型)

默认浏览器会使用标准模型。如果需要使用替代模型，您可以通过为其设置 `box-sizing: border-box` 来实现。 这样就可以告诉浏览器使用 `border-box` 来定义区域，从而设定您想要的大小。

```css
div {
  width: 300px;
  height: 100px;  
  padding: 50px;
  border: 1px solid red;
  box-sizing: border-box;
}
```

[试一试 ](jQuery learn\css-demo-box.html)

### [CSS属性](https://www.runoob.com/cssref/pr-font-weight.html)

#### 字体（Font）


| 属性                                                         | 说明                                 |
| :----------------------------------------------------------- | :----------------------------------- |
| [font](https://www.runoob.com/cssref/pr-font-font.html)      | 在一个声明中设置所有的字体属性       |
| [font-family](https://www.runoob.com/cssref/pr-font-font-family.html) | 指定文本的字体系列                   |
| [font-size](https://www.runoob.com/cssref/pr-font-font-size.html) | 指定文本的字体大小                   |
| [font-style](https://www.runoob.com/cssref/pr-font-font-style.html) | 指定文本的字体样式                   |
| [font-variant](https://www.runoob.com/cssref/pr-font-font-variant.html) | 以小型大写字体或者正常字体显示文本。 |
| [font-weight](https://www.runoob.com/cssref/pr-font-weight.html) | 指定字体的粗细。                     |

[试一试 ](jQuery learn\css-demo-font.html)

#### 文本（Text）

| 属性                                                         | 说明                                 |
| :----------------------------------------------------------- | :----------------------------------- |
| **[color](https://www.runoob.com/cssref/pr-text-color.html)** | 设置文本的颜色                       |
| **[text-align](https://www.runoob.com/cssref/pr-text-text-align.html)** | 规定文本的水平对齐方式               |
| **[white-space](https://www.runoob.com/cssref/pr-text-white-space.html)** | 设置怎样给一元素控件留白             |
| [word-break](https://www.runoob.com/cssref/css3-pr-word-break.html) | 指定非CJK文字的断行规则              |
| **[word-wrap](https://www.runoob.com/cssref/css3-pr-word-wrap.html)** | 设置浏览器是否对过长的单词进行换行。 |

#### 外边距(Margin) 

| 属性                                                         | 说明                           |
| :----------------------------------------------------------- | :----------------------------- |
| [margin](https://www.runoob.com/cssref/pr-margin.html)       | 在一个声明中设置所有外边距属性 |
| [margin-bottom](https://www.runoob.com/cssref/pr-margin-bottom.html) | 设置元素的下外边距             |
| [margin-left](https://www.runoob.com/cssref/pr-margin-left.html) | 设置元素的左外边距             |
| [margin-right](https://www.runoob.com/cssref/pr-margin-right.html) | 设置元素的右外边距             |
| [margin-top](https://www.runoob.com/cssref/pr-margin-top.html) | 设置元素的上外边距             |

#### 内边距(Padding) 

| 属性                                                         | 说明                         |
| :----------------------------------------------------------- | :--------------------------- |
| [padding](https://www.runoob.com/cssref/pr-padding.html)     | 在一个声明中设置所有填充属性 |
| [padding-bottom](https://www.runoob.com/cssref/pr-padding-bottom.html) | 设置元素的底填充             |
| [padding-left](https://www.runoob.com/cssref/pr-padding-left.html) | 设置元素的左填充             |
| [padding-right](https://www.runoob.com/cssref/pr-padding-right.html) | 设置元素的右填充             |
| [padding-top](https://www.runoob.com/cssref/pr-padding-top.html) | 设置元素的顶部填充           |

#### 尺寸(Dimension)

| 属性                                                         | 描述               |
| :----------------------------------------------------------- | :----------------- |
| [height](https://www.runoob.com/cssref/pr-dim-height.html)   | 设置元素的高度     |
| [max-height](https://www.runoob.com/cssref/pr-dim-max-height.html) | 设置元素的最大高度 |
| [max-width](https://www.runoob.com/cssref/pr-dim-max-width.html) | 设置元素的最大宽度 |
| [min-height](https://www.runoob.com/cssref/pr-dim-min-height.html) | 设置元素的最小高度 |
| [min-width](https://www.runoob.com/cssref/pr-dim-min-width.html) | 设置元素的最小宽度 |
| [width](https://www.runoob.com/cssref/pr-dim-width.html)     | 设置元素的宽度     |

#### 弹性盒子模型（Flexible Box）

| 属性                                                         | 说明                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [flex](https://www.runoob.com/cssref/css3-pr-flex.html)      | 复合属性。设置或检索弹性盒模型对象的子元素如何分配空间。     |
| [flex-grow](https://www.runoob.com/cssref/css3-pr-flex-grow.html) | 设置或检索弹性盒的扩展比率。                                 |
| [flex-shrink](https://www.runoob.com/cssref/css3-pr-flex-shrink.html) | 设置或检索弹性盒的收缩比率。                                 |
| [flex-basis](https://www.runoob.com/cssref/css3-pr-flex-basis.html) | 设置或检索弹性盒伸缩基准值。                                 |
| [flex-flow](https://www.runoob.com/cssref/css3-pr-flex-flow.html) | 复合属性。设置或检索弹性盒模型对象的子元素排列方式。         |
| [flex-direction](https://www.runoob.com/cssref/css3-pr-flex-direction.html) | 该属性通过定义flex容器的主轴方向来决定felx子项在flex容器中的位置。 |
| [flex-wrap](https://www.runoob.com/cssref/css3-pr-flex-wrap.html) | 该属性控制flex容器是单行或者多行，同时横轴的方向决定了新行堆叠的方向。 |
| [align-content](https://www.runoob.com/cssref/css3-pr-align-content.html) | 在弹性容器内的各项没有占用交叉轴上所有可用的空间时对齐容器内的各项（垂直）。 |
| [align-items](https://www.runoob.com/cssref/css3-pr-align-items.html) | 定义flex子项在flex容器的当前行的侧轴（纵轴）方向上的对齐方式。 |
| [align-self](https://www.runoob.com/cssref/css3-pr-align-self.html) | 定义flex子项单独在侧轴（纵轴）方向上的对齐方式。             |
| [justify-content](https://www.runoob.com/cssref/css3-pr-justify-content.html) | 设置或检索弹性盒子元素在主轴（横轴）方向上的对齐方式。       |
| [order](https://www.runoob.com/cssref/css3-pr-order.html)    | 设置或检索弹性盒模型对象的子元素出现的順序。                 |

#### 定位（Positioning）

| 属性                                                         | 说明                                                 |
| :----------------------------------------------------------- | :--------------------------------------------------- |
| [bottom](https://www.runoob.com/cssref/pr-pos-bottom.html)   | 设置定位元素下外边距边界与其包含块下边界之间的偏移   |
| [clear](https://www.runoob.com/cssref/pr-class-clear.html)   | 规定元素的哪一侧不允许其他浮动元素                   |
| [clip](https://www.runoob.com/cssref/pr-pos-clip.html)       | 剪裁绝对定位元素                                     |
| [cursor](https://www.runoob.com/cssref/pr-class-cursor.html) | 规定要显示的光标的类型（形状）                       |
| [display](https://www.runoob.com/cssref/pr-class-display.html) | 规定元素应该生成的框的类型                           |
| [float](https://www.runoob.com/cssref/pr-class-float.html)   | 规定框是否应该浮动                                   |
| [left](https://www.runoob.com/cssref/pr-pos-left.html)       | 设置定位元素左外边距边界与其包含块左边界之间的偏移   |
| [overflow](https://www.runoob.com/cssref/pr-pos-overflow.html) | 规定当内容溢出元素框时发生的事情                     |
| [position](https://www.runoob.com/cssref/pr-class-position.html) | 规定元素的定位类型                                   |
| [right](https://www.runoob.com/cssref/pr-pos-right.html)     | 设置定位元素右外边距边界与其包含块右边界之间的偏移   |
| [top](https://www.runoob.com/cssref/pr-pos-top.html)         | 设置定位元素的上外边距边界与其包含块上边界之间的偏移 |
| [visibility](https://www.runoob.com/cssref/pr-class-visibility.html) | 规定元素是否可见                                     |
| [z-index](https://www.runoob.com/cssref/pr-pos-z-index.html) | 设置元素的堆叠顺序                                   |

更多属性，可以参照以下文档。

https://www.runoob.com/cssref/css-reference.html

## jQuery

jQuery 是一个高效、精简并且功能丰富的 JavaScript 工具库。它提供的 API 易于使用且兼容众多浏览器，这让诸如 HTML 文档遍历和操作、事件处理、动画和 Ajax 操作更加简单。

### 基础语法

``` js
$(selector).action()
```
美元符号定义: jQuery
选择符（selector）“查询”和“查找” HTML 元素
jQuery 的 action() 执行对元素的操作

### 选择器(selector)

#### 元素选择器

jQuery 使用 CSS 选择器来选取 HTML 元素。

```javascript
$("p") 选取 <p> 元素。

$("p.intro") 选取所有 class="intro" 的 <p> 元素。

$("p#demo") 选取所有 id="demo" 的 <p> 元素。
```

#### ID选择器

```javascript
$("#demo") 选取所有 id="demo" 的元素。
```

#### 类选择器

```javascript
$(".demo") 选取所有 class="demo" 的元素。
```

#### 属性选择器

```javascript
$("[href]") 选取所有带有 href 属性的元素。

$("[href='#']") 选取所有带有 href 值等于 "#" 的元素。

$("[href!='#']") 选取所有带有 href 值不等于 "#" 的元素。

$("[href$='.jpg']") 选取所有 href 值以 ".jpg" 结尾的元素。

$("[href^='aa']") 选取所有 href 值以 "aa" 开头的元素。

$("[href*='aa']") 选取所有 href 值包含 "aa" 的元素。
```

#### CSS 选择器

jQuery CSS 选择器可用于改变 HTML 元素的 CSS 属性。

下面的例子把所有 p 元素的背景颜色更改为红色：

```javascript
$("p").css("background-color","red");
```

### 事件(Event)

jQuery 事件处理方法是 jQuery 中的核心函数。
事件处理程序指的是当 HTML 中发生某些事件时所调用的方法。

#### 文档就绪事件

```javascript
$(document).ready(function(){

   // 开始写 jQuery 代码...

 }); 

 $(function(){

   // 开始写 jQuery 代码...

 }); 
```

#### 简单绑定click事件

- 语法格式：`click([[data],fn])`
- 参数：
  - data 可以省略，给可传入到函数fn处理。可以通过事件处理程序的事件对象的data属性获取此值。
  - fn 事件处理程序。fn的内部作用域中this指向当前的DOM对象（注意不是jQuery的包装对象)

```javascript
$('#btn').click(function(){
    alert(1);
});

// 触发
$('#btn').click();

// trigger触发
$('#btn').trigger("click")
```

#### bind绑定事件

语法：`bind(type,[data],fn)`，这个也是包装对象的方法。
含义：为每个匹配元素的特定事件绑定事件处理函数。在绑定事件之前，一定要确保页面中的DOM元素已经就绪。如果没有就绪或者后面动态添加的DOM元素则不会动态更新事件处理程序。

参数：

- type: 含有一个或多个事件类型的字符串，由空格分隔多个事件。比如"click"或"submit"，还可以是自定义事件名。
- data:作为event.data属性值传递给事件对象的额外数据对象
- fn:绑定到每个匹配元素的事件上面的处理函数

```javascript
$("form").bind("submit", function() {
  return false; // 取消默认操作。
})

// 同时绑定多个事件
$('#foo').bind('mouseenter mouseleave', function() {
  $(this).toggleClass('entered');
});

//同时绑定多个事件类型/处理程序
$("button").bind({
  click: function(){
    $("p").slideToggle();
  },
  mouseover: function(){
    $("body").css("background-color","red");
  },
  mouseout: function(){
    $("body").css("background-color","#FFFFFF");
  }
});
```

#### on绑定事件方法

语法： `$dom.on(events,[selector],[data],fn)`

> 说明：在选择元素上绑定一个或多个事件的事件处理函数。on()方法绑定事件处理程序到当前选定的jQuery对象中的元素。on汇总了bind和live两种绑定事件的方式。可以支持一般的bind方法或者委托的方法。

参数:

- events:一个或多个用空格分隔的事件类型和可选的命名空间，如"click"或"keydown.myPlugin" 。
- selector:一个选择器字符串用于过滤器的触发事件的选择器元素的后代。如果选择的< null或省略，当它到达选定的元素，事件总是触发。
- data:当一个事件被触发时要传递event.data给事件处理函数。
- fn:该事件被触发时执行的函数。 false 值也可以做一个函数的简写，返回false。

```javascript
// bind绑定事件
$("p").on("click", function(){
  alert( $(this).text() );
});

// 事件委托
$('div').on('click', 'p', function(e){
  console.log(this.innerHTML);
})
```

### 效果(Effect)
#### 隐藏和显示

语法：

```
$(selector).hide(speed,callback);

$(selector).show(speed,callback);
```

可选的 speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是隐藏或显示完成后所执行的函数名称。

```
// 使用 toggle() 方法来切换 hide() 和 show() 方法。
$("button").click(function(){
  $("p").toggle();
});
```

#### 动画(animate)

jQuery animate() 方法用于创建自定义动画。

### 语法：

```
$(selector).animate({params},speed,callback);
```

必需的 params 参数定义形成动画的 CSS 属性。

可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是动画完成后所执行的函数名称。

下面的例子演示 animate() 方法的简单应用；它把 <div> 元素移动到左边，直到 left 属性等于 250 像素为止：

### 实例

```javascript
$("button").click(function(){
  $("div").animate({left:'250px'});
}); 
```

### HTML / CSS 操作

jQuery 中非常重要的部分，就是操作 DOM 的能力。

jQuery 提供一系列与 DOM 相关的方法，这使访问和操作元素和属性变得很容易。

**提示：**DOM = Document Object Model（文档对象模型）

DOM 定义访问 HTML 和 XML 文档的标准：

“W3C 文档对象模型独立于平台和语言的界面，允许程序和脚本动态访问和更新文档的内容、结构以及样式。”

## 获得/设置 内容 - text()、html() 以及 val()

三个简单实用的用于 DOM 操作的 jQuery 方法：

- text() - 设置或返回所选元素的文本内容
- html() - 设置或返回所选元素的内容（包括 HTML 标记）
- val() - 设置或返回表单字段的值

下面的例子演示如何通过 jQuery text() 和 html() 方法来获得内容：

### 实例

```javascript
$("#btn1").click(function(){
  alert("Text: " + $("#test").text());
});
$("#btn2").click(function(){
  alert("HTML: " + $("#test").html());
});
```

## attr()

下面的例子演示如何获得链接中 href 属性的值：

### 实例

```
$("button").click(function(){
  alert($("#w3s").attr("href"));
});
```

# 添加元素

## jQuery append() 方法

jQuery append() 方法在被选元素的结尾插入内容。

### 实例

```javascript
$("p").append("Some appended text.");
```

## jQuery prepend() 方法

jQuery prepend() 方法在被选元素的开头插入内容。

### 实例

```javascript
$("p").prepend("Some prepended text.");
```

## jQuery after() 和 before() 方法

jQuery after() 方法在被选元素之后插入内容。

jQuery before() 方法在被选元素之前插入内容。

### 实例

```javascript
$("img").after("Some text after");

$("img").before("Some text before");
```

# 删除元素

## jQuery remove() 方法

jQuery remove() 方法删除被选元素及其子元素。

### 实例

```javascript
$("#div1").remove();
```

## 过滤被删除的元素

jQuery remove() 方法也可接受一个参数，允许您对被删元素进行过滤。

该参数可以是任何 jQuery 选择器的语法。

下面的例子删除 class="italic" 的所有 <p> 元素：

### 实例

```javascript
$("p").remove(".italic");
```

## 设置 CSS 属性

如需设置指定的 CSS 属性，请使用如下语法：

```javascript
css("propertyname","value");
```

下面的例子将为所有匹配元素设置 background-color 值：

### 实例

```javascript
$("p").css("background-color","yellow");
```



## 遍历(Traversing )

## jQuery first() 方法

first() 方法返回被选元素的首个元素。

下面的例子选取首个 <div> 元素内部的第一个 <p> 元素：

### 实例

```javascript
$(document).ready(function(){
  $("div p").first();
});
```

## jQuery last() 方法

last() 方法返回被选元素的最后一个元素。

下面的例子选择最后一个 <div> 元素中的最后一个 <p> 元素：

### 实例

```javascript
$(document).ready(function(){
  $("div p").last();
});
```

## jQuery eq() 方法

eq() 方法返回被选元素中带有指定索引号的元素。

索引号从 0 开始，因此首个元素的索引号是 0 而不是 1。下面的例子选取第二个 <p> 元素（索引号 1）：

### 实例

```javascript
$(document).ready(function(){
  $("p").eq(1);
});
```

## jQuery filter() 方法

filter() 方法允许您规定一个标准。不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回。

下面的例子返回带有类名 "intro" 的所有 <p> 元素：

### 实例

```javascript
$(document).ready(function(){
  $("p").filter(".intro");
});
```

## jQuery not() 方法

not() 方法返回不匹配标准的所有元素。

**提示：**not() 方法与 filter() 相反。

下面的例子返回不带有类名 "intro" 的所有 <p> 元素：

实例

```javascript
$(document).ready(function(){
  $("p").not(".intro");
});
```

each() 方法

## 定义和用法

each() 方法规定为每个匹配元素规定运行的函数。

**提示：**返回 false 可用于及早停止循环。

### 语法

```javascript
$(selector).each(function(index,element))
```

### AJAX （Asynchronous JavaScript and XML）

AJAX是与服务器交换数据并更新部分网页的技术，而无需重新加载整个页面。

AJAX = 异步 JavaScript 和 XML（Asynchronous JavaScript and XML）。

简短地说，在不重载整个网页的情况下，AJAX 通过后台加载数据，并在网页上进行显示。

### 创建 XMLHttpRequest 对象





| Method                                                       | Description                                                  |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [$.ajax()](https://www.w3schools.com/jquery/ajax_ajax.asp)   | Performs an async AJAX request                               |
| $.ajaxPrefilter()                                            | Handle custom Ajax options or modify existing options before each request is sent and before they are processed by $.ajax() |
| [$.ajaxSetup()](https://www.w3schools.com/jquery/ajax_ajaxsetup.asp) | Sets the default values for future AJAX requests             |
| $.ajaxTransport()                                            | Creates an object that handles the actual transmission of Ajax data |
| [$.get()](https://www.w3schools.com/jquery/ajax_get.asp)     | Loads data from a server using an AJAX HTTP GET request      |
| [$.getJSON()](https://www.w3schools.com/jquery/ajax_getjson.asp) | Loads JSON-encoded data from a server using a HTTP GET request |
| $.parseJSON()                                                | Deprecated in version 3.0, use [JSON.parse()](https://www.w3schools.com/js/js_json_parse.asp) instead. Takes a well-formed JSON string and returns the resulting JavaScript value |
| [$.getScript()](https://www.w3schools.com/jquery/ajax_getscript.asp) | Loads (and executes) a JavaScript from a server using an AJAX HTTP GET request |
| [$.param()](https://www.w3schools.com/jquery/ajax_param.asp) | Creates a serialized representation of an array or object (can be used as URL query string for AJAX requests) |
| [$.post()](https://www.w3schools.com/jquery/ajax_post.asp)   | Loads data from a server using an AJAX HTTP POST request     |
| [ajaxComplete()](https://www.w3schools.com/jquery/ajax_ajaxcomplete.asp) | Specifies a function to run when the AJAX request completes  |
| [ajaxError()](https://www.w3schools.com/jquery/ajax_ajaxerror.asp) | Specifies a function to run when the AJAX request completes with an error |
| [ajaxSend()](https://www.w3schools.com/jquery/ajax_ajaxsend.asp) | Specifies a function to run before the AJAX request is sent  |
| [ajaxStart()](https://www.w3schools.com/jquery/ajax_ajaxstart.asp) | Specifies a function to run when the first AJAX request begins |
| [ajaxStop()](https://www.w3schools.com/jquery/ajax_ajaxstop.asp) | Specifies a function to run when all AJAX requests have completed |
| [ajaxSuccess()](https://www.w3schools.com/jquery/ajax_ajaxsuccess.asp) | Specifies a function to run when an AJAX request completes successfully |
| [load()](https://www.w3schools.com/jquery/ajax_load.asp)     | Loads data from a server and puts the returned data into the selected element |
| [serialize()](https://www.w3schools.com/jquery/ajax_serialize.asp) | Encodes a set of form elements as a string for submission    |
| [serializeArray()](https://www.w3schools.com/jquery/ajax_serializearray.asp) | Encodes a set of form elements as an array of names and values |
|                                                              |                                                              |