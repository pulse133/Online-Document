# Online-Document

Claw学习前端的笔记

<hr><br>

[TOC]



# HTML

## h 标签

```html
<!-- h1 h2 h3... -->
<h1>h标签</h1>
```





## p 标签

```html
<p>p标签</p>
```





## a 标签

> target默认为当前窗口跳转 可以设置为"_blank"使其重新打开新的链接页面

```html
<a href="链接地址" target=""></a>
```





## img 标签

```html
<img src="路径 | 相对路径 | 绝对路径" width="宽" height="高" alt="文字描述(必要的标签)" title="鼠标悬停显示的内容">
```





## base标签

> base应该写在head之内

```html
<base target="_blank">
```





## 转义字符

|    代码    |  含义  |
| :--------: | :----: |
| &amp;nbsp; |  空格  |
|  &amp;lt;  |   <    |
|  &amp;gt;  |   >    |
| &amp;yen;  | &yen;  |
| &amp;copy; | &copy; |
| &amp;reg;  | &reg;  |





## 文本格式化标签

> b i s u 是基础的表现形式strong em del ins的语义更强烈 两者都可以实现相同的效果

```html
<b></b> | <strong></strong> 粗体
<i></i> | <em></em> 斜体
<s></s> | <del></del> 删除线
<u></u> | <ins></ins> 下划线
```





## 注释标签

```html
<!-- 注释不会显示在浏览器窗口中，但是可以在网页源代码上看到 -->
```





## 列表

### 无序列表

```html
<ul>
    <li>A</li>
    <li>B</li>
    <li>C</li>
</ul>
```

### 有序列表

```html
<ol>
    <li>A</li>
    <li>B</li>
    <li>C</li>
</ol>
```

### 自定义列表

```html
<dl>
    <dt>题目1</dt>
    <dd>选项1</dd>
    <dd>选项2</dd>
    ...
    <dt>题目2</dt>
    <dd>选项1</dd>
</dl>
```





## div标签（盒子）

```html
<div>
    <h1></h1>
    <p></p>
</div>
```





## span标签

> span标签无语义，通常用来组合行内元素

```html
<p><span></span>text</p>
```

<hr><br>



# CSS (Cascading Style Sheets)

> CSS可以对前端的样式以及位置进行调整





## 行内式（内联样式）

```html
<标签 style="属性:属性值;">content</标签>
<h1 style="color:red;">红色的h1</h1>
```





## 内部样式

> 将CSS代码写在head标签中使用，type="text/css"在HTML5中可以省略

```html
<head>
    <style type="text/css">
        选择器 {
            属性1: 属性值1;
            属性2: 属性值2;
        }
    </style>
</head>
```





## 外部样式

> 使用link标签将外部样式文件链接到当前HTML文档中，同样也要写在head标签中

```html
<head>
    <link href"CSS文件地址/路径" rel="stylesheet">
</head>
```



<hr><br>



## CSS选择器

### 类选择器

类选择器使用 “ **.** ”（英文点）表示，后跟类名格式如下

```css
.类名 {
    属性: 属性值;
    ...
}
```

同时类名选择器可以选择多个

```html
<div class="bor-top bor-c-red">content</div>
```



### id选择器

> id选择器用 “#” 表示， 后接id名，和类选择器不同的是id只能标识一个不可以重复，但是类可以

```css
#id名 {
   属性: 属性值;
   ...
}
```



### 通配符选择器

> 用 “ ***** ” 号表示，作用范围是最广的，可以选择到页面中的所有元素

```css
* {
    属性: 属性值;
    ...
}
```



<hr><br>



## CSS字体样式属性

> **px** 以像素单位
>
> **em** 根据当前对象内的文本大小的尺寸（例：当前对象内字体大小为18px，则1em=18px）

### font-style 字体风格样式

字体倾斜除了用 **i** 和 **em** 标签之外的CSS实现方法

> **italic** 和 **oblique** 都是使字体倾斜，但是有些字体不支持 **italic** 的

```css
.style-demo {
    font-style: normal(默认值) | italic | oblique;
}
```

### font-wight 字体粗细

字体粗细除了用 **b** 和 **strong** 之外的CSS实现方法

> **400 **等价于 **normal** | **700 **等价于 **bold**

```css
.style-demo {
    font-size: normal|bold|bolder|lighter|100 ~ 900 (100的整倍数);
}
```

### font-size 字体大小

```css
.style-demo {
	font-size: px|em;
}
```

### font-family 字体

```css
.style-demo{
    font-family: "微软雅黑";
}
```

### font 字体综合设置

> 属性之间用 **空格** 隔开

```css
.style-demo {
    font: font-style font-weight font-size font-family;
}
```

<hr><br>



## CSS 基本外观属性

### color 文本颜色

rgb模式可以使用 **(0, 0, 0)** 或者 **(0%, 0%, 0%)** 使用百分比表示时不可以省略 **%** 号

rgba模式可以设置透明度数值在 **0 ~ 1** 之间

```css
.style-demo {
    color: red | rgb(0, 0, 0) | rgba(0, 0, 0, 0~1);
}
```

### line-height 行间距

> 行距比字号大 7~8 像素就可以

```css
.style-demo {
    line-height: px|em|%;
}
```

### text-align 水平对齐方式

```css
.style-demo {
    text-align: left|right|center;
}
```

### text-indent 首行缩进

> 可以用负数 建议使用em (2em = 首行缩进2字符)

```css
.style-demo {
    text-indent: 2em;
}
```

### text-decoration

用来修改链接效果

> none 默认样式
>
> underline文本下
>
> overline 文本上
>
> line-through 穿过文本

```css
.style-demo {
    text-decoration: none|underline|overline|line-through
}
```



<hr><br>



## 块级元素

块级元素会独占一行（多行），可以设置它的宽高以及对齐等属性，特点：

> 1. 总是从新的一行开始
> 2. 高度、宽度、内外边距都可以控制
> 3. 宽度默认是100%
> 4. 可以容纳其他行内元素（内联元素）、块元素





## 行内元素

行内元素不会自身不会占独立的空间，它的空间大小是根据自己字体的大小和图像尺寸支撑结构的，所以一般来说不用设置宽高和对齐等属性。

```
常见行内元素：
	<a> <strong> <b> <em> <i> <del> <s> <ins> <u> <span>...
```

> **行内元素特点：**
>
> 1. 和相邻的内联元素在同一行上
> 2. 宽高无效，但是水平方向的内外边距（padding和margin）可以设置，垂直方向的无效
> 3. 默认宽度就是内容的宽度
> 4. 行内元素只能容纳文本和其他内联元素（a是特殊）
>
> **PS：**只有文字才能组成段落，p标签里不能放块级元素，相同的还有h1~h6、dt，他们都是文字类的块级标签，里面不能放其他块级元素。
>
> 行内元素中有几个特殊的标签 <img> <input> <td> 这几个标签可以设置宽高。





## 行内块

行内块同时具备行内元素和块元素的特点

> 1. 和相邻的行内块元素在同一行上，但是它们之间会有空隙
> 2. 默认宽和行内元素一样就是内容的宽度
> 3. 宽高、行高、内外边距都可以设置





## 标签模式转换

```css
display: inline; 转为行内元素

display: block; 转换为块元素

display: inline-block; 转换为行内块元素
```



<hr><br>



## 盒子模型

> CSS分三大板块：盒子模型、浮动、定位加上别的一些细节
>
> 盒子模型就是将整个HTML页面看作一个盒子，所有的文档标签都会有一个元素矩形框（element box），每个矩形框都由元素的内容、内边距（padding）和外边距（margin）组成。



### width 宽度	height 高度

> 只有块元素（block）或者行内块（inline-block）元素才能设置宽高。

```css
width: 100px;
height: 100px;
```



### 边框 border

`border-top border-bottom border-left border-right 同理`

```css
border: border-width border-style border-color;
```

`border-style (边框样式)可以设置为不同样式的边框`

```css
none: 没有边框，忽略宽度(默认值)
solid: 单实线边框
dashed: 虚线边框
dotted: 点线边框
double: 双实线边框
```



### 内边距 (padding)

`padding-top padding-bottom padding-right padding-left`

```css
padding: 3px; 上下左右都是3px
padding: 3px 6px; 上下3px 左右6px
padding: 3px 6px 9px; 上3px 左右6px 下9px
padding: 3px 6px 5px 4px; 上3px 右6px 下5px 左4px
```



### 外边距 (margin)

> margin 属性值位置和 padding 一样

`margin-top margin-bottom margin-left margin-right`



### 外边距实现盒子居中

> 让一个盒子水平居中元素必须是块元素而且指定了宽高

```css
/* 盒子(块元素)水平居中 */
width: 256px;
margin: 0 auto;

/* 文字水平居中 */
text-align: center;
```



### 清除元素默认内外边距

> 行内元素只有左右内外边距，没有上下内外边距，在IE6等低版本浏览器会有问题。
>
> 所以尽量不要给行内元素指定内外边距。

```css
padding: 0;
margin: 0;
```



### 外边距合并问题

使用margin定义块元素的上下外边距时，可能会出现外边距的合并。

如果有两个元素，一个在上面设置了外边距 margin-bottom，一个在下面设置了外边距 margin-top，则他们之间的垂直边距不是，margin-bottom与margin-top之和，而是值较大的一方，这种现象称为相邻块元素垂直外边距的合并 **外边距塌陷**

**解决方案：**

1. 设置父元素的上边框或者内边距为1像素
2. 给父类添加 **overflow:hideen**



### 内容宽高

使用属性 width 和 height 可以控制盒子的大小

符合CSS规范的盒子模型总宽高计算原则是：

元素空间尺寸

```css
空间高度 = content height + padding + border + margin
空间宽度 = content width + padding + border + margin
```

元素实际大小

```css
实际高度 = content height + padding + border + margin
实际宽度 = content width + padding + border + margin
```

1. 大部分浏览器Firefox、Edge、Chrome和IE6以上的版本都采用W3C规范
2. 宽高属性只能用于块级元素，对行内元素无效 (img、input标签除外)
3. 在计算总高度的同时，应该考虑上面说的外边距塌陷的情况
4. 一个盒子（块元素）占满父元素的宽度，如果盒子没有指定宽度，则padding不会影响改盒子的大小



### 盒子模型布局稳定性

稳定性排行：

```
width > padding > margin
```

1. margin 可能会出现外边距合并（塌陷），IE6以下的 margin 会加倍（bug）
2. padding 会影响盒子的大小，需要进行加减计算，稍微有点麻烦



### 怪异盒子模型

```css
box-sizing: border-box; /* 怪异盒子模型 */
box-sizing: content-box; /* 标准盒子模型 */
```

> 怪异盒子模型的宽高计算和标准盒子模型的计算方式不同，怪异盒子模型的  content 内容宽度会把 padding 和 border 算入其中，由外向内的计算宽度



### 两种盒子的区别

`主要区别在于盒子的宽高计算方式不同`

1. 标准盒子模型（正常）主要用于 PC 端，怪异盒子模型主要用于手机端
2. 标准盒子模型的大小是由内向外的，由内部决定外部大小，而怪异盒子模型是由外向内的
3. 可以设置 box-sizing 属性来使用这一特性，使其改变border宽度也不影响其它元素

<hr><br>




## 盒子模型知识点补充

### 高度：

> 图片标签设置了宽度之后，可以将高度设置为 auto (自动) 实现等比例自动计算

### 同行宽度：

> 一行内多个元素的占位宽度 (margin + border + padding + width) 相加大于容器宽度就会被挤到下一行显示

### 内外边距：

> 1. 外边距垂直会合并，值为最大的那一边 | 水平方向会叠加
> 2. 如果父容器没有边界（硬性边界、边框、内边距）就会产生穿透效果 子元素的外边距会穿透父元素生效
> 3. 内外边距都只能设置为整数

### 行高与高度：

> 当行高跟高度相等时，文本会垂直居中



<hr><br>



## CSS背景 (background)

| 代码                                                  | 作用             |
| :---------------------------------------------------- | ---------------- |
| background-color                                      | 背景颜色         |
| background-image                                      | 背景图片地址     |
| background-repeat                                     | 是否平铺         |
| background-position                                   | 背景位置         |
| background-attachment                                 | 背景固定 \| 滚动 |
| background-size                                       | 背景大小（尺寸） |
| background: color url repeat attachment position/size | 背景综合写法     |



### 背景颜色 (color)

> CSS3背景透明使用 rgba(0, 0, 0, 0.3) 第四个参数在 0~1 之间
>
> 透明属性的设置只会影响背景，不会影响元素内容

```css
background-color: hex(16进制) | rgb | rgba;
```



### 背景图片 (image)

> 使用绝对或者相对地址指定背景图片
>
> background-image只允许一张图片展示在背景中，只有CSS3才可以多背景，可以和background-color配合使用，图片不能覆盖的地方会显示填充的颜色，如果平铺图片则会覆盖背景图片
>
> 建议图片地址不加引号

```css
background-image: none | url(url)
```



### 背景平铺 (repeat)

| 参数      | 含义               |
| --------- | ------------------ |
| repeat    | 图片平铺（默认值） |
| no-repeat | 图片不平铺         |
| repeat-x  | 图片横向平铺       |
| repeat-y  | 图片纵向平铺       |



```css
background-repeat: repeat | no-repeat | repeate-x | repeat-y;
```



### 图片位置 (position)

> x y 坐标默认时(0% 0%) 如果只指定了一个值默认是 x 坐标
>
> position 大多用于背景图片的居中对齐

```css
background-position: length-x | length-y;
background-position: position-x | position-y;
```

position参数: top | center| bottom | left | right



### 背景附着 (attachment)

```css
background-attachment: scroll | fixed;
```

`scroll 滚动	fixed 固定`



### 背景大小（尺寸）

> 单位 px | % | cover
>
> 只设置 width 时 height 会等比例缩放

```css
background-size: width height;
```



### 背景裁剪 (clip)

| 参数        | 含义                     |
| ----------- | ------------------------ |
| content-box | 将图片裁剪和内容大小一致 |
| border-box  | 将图片裁剪至边框位置     |
| padding-box | 将图片裁剪至内边距位置   |



```css
background-clip: content-box | border-box |padding-box;
```

设置图片原点位置 (origin)

> 用来设置背景图片起始位置
>
> 属性值和 **clip** 一样

<hr><br>



## CSS复合选择器

### 交集选择器

```html
<!-- CSS -->
<style>
    p.one {
        color: red;
    }
</style>

<!-- HTML -->
<p>A</p>
<p class="one">A</p>
```

`带有 one 类的 p 标签文本变为红色，第一个 p 标签不受影响`



### 并集选择器

不同选择器之间通过 <b style="color: orange">, 逗号</b> 连接

```css
.one,
.two,
.three {
    color: orange;
}
```

```html
<!-- HTML -->
<h1 class="one">橘色标签1</h1>
<h1 class="two">橘色标签2</h1>
<h1 class="three">橘色标签3</h1>
```

<img src="./img/css/并集选择器.png" style="width:150px;" title="显示效果"></img>

<hr><br>




### 后代选择器

后代选择器又称为包含选择器

```css
/* CSS */
div ul li {
        color: green;
    }
```

```html
<!-- HTML -->
<div>
    <h1>title</h1>
	<ul>
        <li>list-1</li>
        <li>list-2</li>
    </ul>
</div>
```

<img src="./img/css/后代选择器.png" style="width:150px;" title="显示效果"></img>

<hr><br>




### 子代选择器

只能选择该元素的子代元素，子代优先级高于后代，使用时优先选择使用子代选择器

```css
/* CSS */
.style-demo > h1 {
    color: green;
}
```

```html
<!-- HTML -->
<div>
	<h1>测试样例-1</h1>
</div>
    
<div class="style-demo">
	<h1>测试样例-2</h1>
</div>
```

<img src="./img/css/子代选择器.png" style="width:150px;" title="显示效果"></img>

<hr><br>




### 伪类选择器

> <b style="color:orange;">类选择器 .</b>	**.style**
>
> <b style="color:orange;">伪类选择器 :</b>	**:link**
>
> 写链接伪类时注意顺序：
>
> 1. :link
> 2. :visited
> 3. :hover
> 4. :active

**链接伪类选择器**

| 伪类     | 作用                 |
| -------- | -------------------- |
| :link    | 未访问的链接         |
| :visited | 已访问的链接         |
| :hover   | 鼠标移动到连接链接上 |
| :active  | 已经点击访问过的链接 |

**一个简单的例子：**

```css
a {
    font-size: 24px;
    color: black;
}

/* 鼠标滑过字体会变为28px 而且颜色会变为天蓝色
   当鼠标移开时会变回初始样式  
*/
a:hover {
    font-size: 28px;
    color: skyblue;
}
```

<img src="./img/gif/链接伪类.gif" style="width:150px;" title="显示效果"></img>



<hr><br>



## CSS 特性

<b style="color:orange;">叠层 继承 优先级</b> 是CSS必须掌握的三个特性



### CSS 层叠性

举一个简单的例子 :chestnut: 当我们已经写好了一个样式，样式设置原色颜色为蓝色，字体大小为16px，但是接下来我们需要一个新的样式，它和刚才那个样式一样，但是它比前面的那个样式多了一个边框设置并且字体大小为24px，这个时候我们除了重新写一篇一模一样的并加上新规则还可以使用CSS的一特性 <b style="color:orange;">叠层性</b>

`如果重复的话，谁在最底层就会是谁	CSS样式优先级 内联样式 > 内部样式 > 外联样式`

```css
/* CSS */
.style-base {
    color: blue;
    font-size: 16px;
}

.style-border {
    font-size: 24px;
    border: 1px solid black;
}
```

```html
<!-- HTML -->
<span class="style-base style-border">content</span>
```

<img src="./img/css/层叠性.png" style="width:150px;" title="显示效果"></img>

<hr><br>




### CSS继承性

再举一个简单的例子 (我有很多:chestnut:) 我们写了一个 **div** 的CSS样式设置字体颜色为green，我们在div标签中写入其他内容会发现其他字体内容也是绿色，这就是继承性。

> 常见的继承属性：开头是 **font- text- line-** 以及 **color** 都可以继承
>
> 自身有默认样式的情况下优先显示，也就是继承性优先级最低。

```css
div {
    color: green;
}

.bg-black {
    background: black;
}
```

```html
<div>
    <h3 class="bg-black">我是div标签里的h3</h3>
</div>
```

<img src="./img/css/继承性.png" style="width:150px;" title="显示效果"></img>

<hr><br>




### CSS 优先级

权重越大优先级越高

- 继承样式权重为0
- 行内样式优先级最高，权重非常高
- 权重相同时 CSS 会选择最排在最后的样式
- CSS 有一个 **!important** 命令，该命令被赋予最大的优先级，不管权重大小以及位置的前后，**!important** 都拥有最大的优先级



### CSS特殊性（Specificity）

CSS的权重有一个计算公式，称为 CSS 特性或者 非凡性，是一个衡量 CSS 值优先级的一个标准

值从左往右，越往左权重越大，数位之间没有进制

| 元素/样式        | 权重值  |
| ---------------- | ------- |
| 继承 / *         | 0,0,0,0 |
| 每个元素（标签） | 0,0,0,1 |
| 每个类 / 伪类    | 0,0,1,0 |
| 每个ID           | 0,1,0,0 |
| 每个行内样式     | 1,0,0,0 |
| 每个 !important  | **∞**   |

权重是可以叠加的，比如下面的例子：

```
div a img : 0,0,0,3
.bg a img : 0,0,1,2
a:hover   : 0,0,1,1
#only p   : 0,1,0,1
```

<hr><br>



## vertical-align

设置垂直对齐方式

vertical-align 不会影响到块级元素的内容对齐，他只针对行内元素或行内块元素，通常用来控制 <b style="color: skyblue;">图片 </b>或者 <b style="color:skyblue;">表单 </b>与文字之间的对齐方式

```css
vertical-align: baseline(默认) | top | middle | [bottom sub];
```

`baseline 对齐基线、top 对齐顶线、middle 对齐中线、bottom \ sub 对齐底线`

> 图片的在块元素中以基线对齐的方式 (vertical-align: baseline) 底部会有一点空隙，可以将 **img标签** 的**vertical-align**设置为**除了baseline**以外的其他属性值，最好的就解决方法就是将图片标签设置为块元素 <b style="color:greenyellow;">block</b>

| 属性值                             | 效果图                                                       |
| ---------------------------------- | ------------------------------------------------------------ |
| vertical-align: baseline; 对齐基线 | <img src="./img/css/vertical-align/baseline.png" width="280px;"> |
| vertical-align: middle; 对齐中线   | <img src="./img/css/vertical-align/middle.png" width="280px;"> |
| vertical-align: top; 对齐顶线      | <img src="./img/css/vertical-align/top.png" width="280px;">  |
| vertical-align: bottom; 对齐底线   | <img src="./img/css/vertical-align/bottom.png" width="280px;"> |

<hr>
<br>



## 溢出文字隐藏

### white-space（自动换行）

```css
white-space: normal(默认值) | pre | nowrap | pre-wrap | pre-line | inherit;
```

| 属性值   | 描述                                                     |
| -------- | -------------------------------------------------------- |
| normal   | **默认值** 空白位置会被浏览器忽略                        |
| pre      | 浏览器会保留空白位置 这种行为类似于 **pre** 标签         |
| nowrap   | 文本不会换行，会一直在同一行上显示，直到遇到 **br** 标签 |
| pre-wrap | 保留空白的序列，会正常的换行                             |
| pre-line | 合并空白的序列，保留换行符                               |
| inherit  | 从父元素继承 **white-space** 属性                        |

<hr>

### text-overflow（文字溢出）

```css
text-overflow: clip | cllipsis | string;
```

| 属性值   | 描述                             |
| -------- | -------------------------------- |
| clip     | 裁剪文本                         |
| ellipsis | 使用省略号来表示被裁剪的文本     |
| string   | 使用指定的字符来表示被裁剪的文本 |

### 多行文本超出隐藏设定

> 使用此方法需要注意高度和宽度的设置

```
display: -webkit-box;	/* -webkit-inline-box; 行内元素 */
-webkit-box-orient: vertical;	/* 单词vertical释义: 垂直 */
-webkit-line-clamp: 3;	/* 设定在第几行结束后显示 ... */
overflow: hidden;	/* 单词hidden释义: 隐藏的 */
```



<hr><br>

## opacity (透明)


> **opacity** 单词释义 **不透明度**
>
> 属性值范围在 0 ~ 1 之间

```css
opacity: (0~1) | inherit;
```

`在IE8以及以下的浏览器中 使用不透明度需要写为 filter(过滤器)`

```css
filter: Alpha(opacity=(0~100));
```



<hr><br>
## 复合选择器

指定选择器后的第一个选择器：<b style="color:orange;">element-1 + element-2</b>

指定选择器后的所有的 **element-2**：<b style="color:orange;">element-1 ~ element-2</b>

> 复合选择器只对同一层的元素生效

```css
.wrap+h2 {
    color: red;	/* 设置wrap类后面的第一个h2为红色字体 */
}
```

```html
<h1 class="wrap">我是wrap</h1>
<h2>h2-1</h2>
<h2>h2-2</h2>
<h2>h2-3</h2>
```

<img src="./img/css/复合选择器+.png" style="width:150px;" title="显示效果"></img>

```css
.wrap~h2 {
    color:red;	/* 设置wrap类后面所有的h2为红色字体 */
}
```

<img src="./img/css/复合选择器~.png" style="width:150px;" title="显示效果"></img>

<hr><br>

## 结构伪类选择器 (CSS3)

> **:first-child**	匹配该元素的父元素下的的第一个子元素
>
> **:last-child**	匹配该元素的父元素下的最后一个元素
>
> **:nth-child(n)**	匹配所选元素的父元素下的第 n 个元素
>
> **:nth-last-child(n)**	匹配所选元素的父元素下的第 n 个子元素的每个元素
>
> **:nth-of-type(n)**	匹配所选元素的父元素下同类型中的第 n 个兄弟元素
>
> **:first-of-type**	匹配同类型中的第一个兄弟元素
>
> **:last-of-type**	匹配同类型中的最后一个兄弟元素
>
> **:only-of-type**	匹配同类型中的父元素下唯一的一个元素
>
> **:not(selection)**	匹配所选元素的父元素下除了 selection(选择器) 的所有元素 
>
> *上面的选择器中带 **(n)** 的都可以使用公式或者 **odd奇数 even偶数***

```css
/* 选择p标签父元素下的第一个元素 */
p:first-child {
    style: value;
}

/* 选择p标签父元素下的最后一个元素 */
p:last-child {
    style: value;
}

/* 选择p标签父元素下的第二个元素如果元素不是p则无法，因为虽然选中了但因为不是p标签所以无法生效 */
p:nth-chile(2) {
    style: value;
}

/* 选择p标签父元素下同类型的第二个元素 */
p:nth-of-type(3) {
    style: value;
}

/* 选择p标签父元素下同类型的第一个元素 */
p:first-of-type {
    style: value;
}

/* 选择p标签父元素下同类型的第一个元素 */
p:last-of-type {
    style: value;
}

/* 选择只有一个子元素的父元素容器 并且这个唯一的子元素是p */
p:only-of-type {
    style: value;
}

p:not(.wrap) {
    /* 选择p标签父元素下同类型除了带.wrap的p的所有p */
    style: value;
}
```



<hr><br>

## 属性选择器


> **^**	在开始位置
>
> **$**	在结束位置
>
> *****	在任意位置

```css
/* 选择div标签以 border 类开头的div元素 */
div[class^="border"] {
    color: red;
}

/* 选择div标签以 end id结尾的div元素 */
div[id$="end"] {
    color:red;
}

/* 选择div标签类名中任意位置有 font 的div元素 */
div[class$="font"] {
    color:red;
}
```



<hr><br>


## 伪元素 (CSS3)

> ::first-letter	文本中的第一个字或者字母
>
> ::first-line	文本中的第一行
>
> ::selection	改变文本选中时的样式
>
> ::before	最前面的
>
> ::after	最后面的
>
> 伪元素不是真正的元素，但是可以显示在页面上，同样也可以对伪元素设置CSS样式
>
> 默认display:inline;	::before和::after 必须配合content使用否则无效

`IE9以下不支持::的写法，如果考虑兼容性可以写为 : 不用强制写为::`

```css
.style::after {
	content: '' | attr(元素属性) | counter(name);	/* 必要元素 */
}
```



<hr><br>



## 精灵技术


> 用户访问一个网站的时候每张图片都要见过一次请求才能返回给用户使用精灵技术可以很好的解决这个问题，CSS精灵是一种处理网页背景图像的方法，它可以将很多零散的的小图标这类的图片合并到一张图片中，对图片使用 position 定位来使用精灵图。

```css
bg-top {
	width: 20px;
	height: 20px;
	background: url(path) no-repeat -10px -10px;
}
```

### 制作精灵图

可以自己做也可以有更好的方法：<a href="https://www.toptal.com/developers/css/sprite-generator/" style="text-decoration:none;">[ 精灵图制作网站 ]</a>

<hr><br>

## 表格

### 创建表格

```html
<table>
    <caption>表格标题</caption>
    <thead>
    	<tr>
        	<th>标题1</th>
            <th>标题2</th>
            <th>标题3</th>
        </tr>
    </thead>
    
    <tbody>
    	<tr>
	        <td>内容1</td>
            <td>内容2</td>
            <td>内容3</td>
        </tr>
        <tr>
	        <td>内容1</td>
            <td>内容2</td>
            <td>内容3</td>
        </tr>
    </tbody>
</table>
```

### 合并单元格

> 跨行合并：rowspan	跨列合并：colspan
>
> 合并顺序：行上优先合并左边	列上优先合并上面

### 表格相关样式

> 表格具有双线条边框，因为table、th、td都有自己独立的边框
>
> 使用折叠边框 border-collapse 来设置是否折叠为单线边框

```css
table {
    /* 
	separate: 默认样式
    collapse: 边框会合并为一条线，会忽略border-spacing和empty-cells
    inherit: 继承父元素的border-collapse属性
    */
    border-collapse: separate | collapse | inherit;
}
```

#### 单元格边框距离 border-spacing

> 只能在 border-collapse: separate（边框分离）模式下使用

```css
table {
    border-collapse: separate;
    border-spacing: 10px 10px;
}
```

#### 标题位置 caption-side

```css
caption {
    caption-side: top(默认) | buttom | inherit;
}
```



<hr><br>

## 表单标签 form

**一个完整的表单通常由表单控件、提示信息、表单域 3 个部分组成**

<hr>

**表单控件：input	select	textarea	button**

> input：输入框（文本框、密码框、复选框、提交按钮、重置按钮）

**提示信息：label**

> 表单部分地方需要添加说明性的文字提示

**表单域：form**

> 相当于填写表单的容器，容纳所有的 **表单控件** 和 **提示信息** 可以定义表单数据的后台url地址

### input控件

| 属性        | 属性值         | 描述                         |
| ----------- | -------------- | ---------------------------- |
| type        | 查看type属性表 | 指定 input 类型              |
| name        | 自定义         | 数据返回后台时的 key 值      |
| value       | 自定义/输入    | input 输入框中的默认值       |
| size        | 0 ~ +∞         | input 输入框在页面中的宽度   |
| checked     | checked        |                              |
| maxlength   | 0 ~ +∞         | 允许输入的最大字符长度       |
| required    | required       | 在提交时要求用户必须填写此空 |
| readonly    | readonly       | 只读内容                     |
| placeholder | 文本           | 提示用户的文本               |
| multiple    | multiple       | 可上传多个文件               |

<h3 id="type">type属性</h3>

| 属性类型 | 作用                                                         |
| :------- | :----------------------------------------------------------- |
| text     | 单行文本输入框（明文）                                       |
| password | 密码框输入（密文）                                           |
| radio    | 单选按钮                                                     |
| file     | 输入框和“浏览”按钮提供文件上传（设置 multiple 属性可以上传多个文件） |
| checkbox | 复选框/多选框                                                |
| submit   | 提交按钮（将用户填写的所有数据提交至form指定url）            |
| button   | 普通按钮                                                     |
| reset    | 重置按钮                                                     |
| image    | 图片提交按钮                                                 |
| hidden   | 隐藏的文本输入框                                             |
| number   | 限定输入字符为数字                                           |
| deta     | 日期选择框                                                   |
| tel      | 电话号码框                                                   |
| time     | 时间选择框                                                   |
| email    | 电子邮件框                                                   |
| search   | 查询框                                                       |

### label标签

> 用for属性绑定一个input元素的id，当点击label标签时，就会指向绑定的input输入点

```html
<label for=""></label>
<input type="text" id="name">
```

### texrarea 文本域

```html
<textarea cols="每行字符数量" rows="显示的行数">
	内容
</textarea>
```

### 下拉菜单

> 可以给option添加selected="selected"属性设置默认选项

```html
<select>
    <option>1</option>
    <option>2</option>
    <option>3</option>
</select>
```



<hr><br>



##  浮动 float


CSS单位机制有三种：标准流（普通流）、浮动和定位

> 设置为浮动的元素display默认是 block 

```css
.style {
	float: left | right | none;
}
```

`关于在使用浮动布局的时候放大页面会改变布局的问题，可以使用 box-sizing: border-box (怪异盒子模型)解决`

### 清除浮动

#### 添加额外标签

```html
<head>
    <style>
        div {
            float: left;
        }
        
        .clear {
            clear: both;
        }
    </style>
</head>

<body>
    <div>
        <div>content</div>
        <div>content</div>
        <div>content</div>
        <div class="clear"></div>
    </div>
</body>
```

#### 使用after伪元素

```css
.clear::after {
    content: "";
    display: block;
    height: 0;
    clear: both;
    visibility: hidden;
}

/* IE6、7专有 */
.clear {
    *zoom: 1;
}
```

#### 使用overflow清除

`超出高度会无法显示`

| 属性值  | 描述                                               |
| ------- | -------------------------------------------------- |
| visible | 默认值                                             |
| hidden  | 修剪内容，超过元素大小不可见                       |
| scroll  | 修剪内容，超出的内容可以用滚动条查看               |
| auto    | 如果没有超出则正常显示，如果超出则使用scroll的方法 |
| inherit | 继承                                               |

#### 使用before和after清除浮动

```css
.clear:before,
.claer:after {
    content: "";
    display: table;
}

.clear:after {
    clear: both;
}

.clear {
  *zoom:1;
}
```

#### 安全版

```css
.clear{
	zoom:1;
}
.clear:after,
.clearfix:before{
    content:"";
    display:table;
}
.clear:after{
    clear:both;
    visibility:hidden;
    font-size:0;
    height:0;
}
```



<hr><br>
## 定位 position

#### position属性值

| 属性值   | 描述                                         |
| -------- | -------------------------------------------- |
| static   | 默认定位方式                                 |
| relative | 相对定位，在自己原始文档流的位置进行定位     |
| absolute | 绝对定位，相对于上一个已经定位的父元素进定位 |
| fixed    | 固定定位，基于浏览器视窗定位                 |

```css
.style {
	position: static(默认) | relative | absolute | fixed;
}
```

#### 偏移量

> 定位之后需要配合偏移量使用：**top	bottom	left	right**

```css
.style {
	position: relative | absolute | fixed;
    left: 10px;
    top: 10px;
}
```



### 静态定位 static

静态位置就是元素在HTML文档流中默认的位置，也是标准文档流的特性



### 相对定位 relative

相对定位就是用元素在他标准流中的位置进行定位



### 绝对定位 absolute

绝对定位的位置参考为相对定位父级的左上角定点

绝对定位于相对定位设置 left right时 都会保留自身外边距

绝对定位通过边偏移移动位置，但是它完全脱标，完全不占位置。

绝对定位元素的宽度高度100%  是相对于定位父级来的 不是结构父级

**绝对定位与相对定位不同的地方在于：**

> 1. 绝对定位完全脱标 相当于自建一个新的层级
> 2. 绝对定位的移动相对坐标原点为 相对定位父级的左上角原点
>    1. 没有相对定位父级的情况下 以浏览器窗口显示区域(window view)左上角为定位原点
>    2. 有相对定位父级(绝对、固定或相对定位)的父元素/祖先的情况下 以相对定位父级的左上角为定位原点
> 3. 绝对定位的宽度百分比 继承自相对定位父级 并不继承于 结构父级

`定位父级可以是除static以外的三个元素`

### 固定定位 fixed

固定定位的特点：

1. 固定定位的元素跟然后元素都没有关系，只认浏览器窗口(window view)。
2. 固定定位完全脱标，不占有位置，不随着滚动条滚动。



### 绝对定位盒子水平/垂直居中

普通盒子可以将margin的左右设置为auto就可以，但是在绝对定位上无效

```css
/* 方法一 */
.style {
    position: absolute;
    width:100px; 
    height:100px;
    left:50%;
    top:50%;
    margin-bottom: -100px;
    margin-right: -100px;
}

/* 方法二 */
.style {
	position: absolute;
	width: 100px;
	height: 100px;
	left: 0;
	top: 0;
	right: 0;
	bottom: 0;
	margin: auto;
	background-color: aqua;
}
```

### 叠放次序 z-index

同一个位置有多个定位元素时会发生重叠现象，默认情况下，谁写在文档后面谁就在最上面，可以设置 z-index(默认0) 来修改优先级，数值越大优先级越高



### 定位总结

| 定位模式          | 是否脱标/占位置  | 是否可以使用偏移量 | 移动位置基准                     |
| ----------------- | ---------------- | ------------------ | -------------------------------- |
| static 静态       | 正常模式，不脱标 | 不可以             | 正常模式                         |
| relative 相对定位 | 脱标，占位置     | 可以               | 相对于自生位置移动               |
| 绝对定位 absolute | 脱标，不占位置   | 可以               | 相对于定位父级位置移动           |
| fixed 固定定位    | 脱标，不占位置   | 可以               | 相对于浏览器窗口位置移动（固定） |

`和浮动一样，当给元素添加了绝对定位(absolute)和固定定位(fixed)之后，元素的display也会转换为block(块)模式`

<hr><br>
## CSS2文本补充

| 属性            | 描述                                 | 属性值                                                       |
| --------------- | ------------------------------------ | ------------------------------------------------------------ |
| color           | 设置文本颜色                         | rgb rgba HEX                                                 |
| direction       | 设置文本方向                         | ltr(左-右) rtl(右-左)                                        |
| letter-spacing  | 设置字符间距                         | px                                                           |
| line-height     | 设置行高                             | px                                                           |
| text-align      | 设置文本对齐方式                     | left \| center \| right \| justify(两端对齐)                 |
| text-decoration | 添加划线                             | none \| underline \| overline \| line-through                |
| text-indent     | 设置文本首行缩进                     |                                                              |
| text-transform  | 设置文本字母                         | capitalize(单词首字母大写) \| uppercase(全大写) \| lowercase(全小写) |
| vertical-align  | 设置元素垂直对齐                     | baseline \| middle \| super \| sub \| top \| bottom \| text-top \| text-bottom |
| white-space     | 设置文本中空白的处理方式（控制换行） | normal(默认 忽略空白) \| pre(保留空白) \| nowrap(文本不换行) \| pre-wrap(保留空白 正常换行) \| pre-line(合并空白 保留换行符) |
| word-spacing    | 设置字符间距                         | px em                                                        |

<hr><br>

## CSS3文本补充

| 属性            | 描述                                     | 属性值                                                       |
| --------------- | ---------------------------------------- | ------------------------------------------------------------ |
| text-align-last | 设置对齐最后一行或者是接着换行符之前的行 | left right justify center                                    |
| text-overflow   | 设置当文本溢出包含元素时的样式           | clip(裁剪) \| ellipses(省略号)                               |
| text-shadow     | 设置文本阴影                             | 参数一(水平偏移) <br>参数二(垂直偏移)<br>参数三(颜色)        |
| word-break      | 规定非中日韩文本的换行规则               | break-all(单词内换行)<br>keep-all(只在半角空格或者连字符处换行) |
| word-wrap       | 允许对超过元素长度的单词分割换行到下一行 | normal(不换行) \| break-word(换行)                           |



<hr><br>

# CSS3

## border-radius（圆角）

> **一个参数：**四个角
>
> **两个参数：**（左上，右下）（右上，左下）
>
> **三个参数：**（左上）（右上，左下）（右下）
>
> **四个参数：**（左上）（右上）（右下）（左下）
>
> **四 / 四 个参数：**和标准的四个参数一样 **/** 左边四个是 **y** 值； **/** 右边四个是x值。

```css
/* 复合写法 */
.style {
    border-radius: 12px |50%;
}

/* 单例写法 */
.style {
	border-top-left-radius: 2em;
    border-bottom-right: 2em;
    ...
}
```

<hr><br>

### border-image（边框图片）

> 可以将图片设置为边框

```css
.style {
    border-image: 图片路径 内偏移量 宽度 边框外部绘制量 设置铺满|拉伸;
    border-image: url(path) 30 round;
    
    /* 单例写法 */
    border-image-source:;
    border-image-slice:; 
    border-image-width:;
    border-image-outset:;
    border-image-repeat:;
}
```



### border-shadow（盒子阴影）

```css
.style {
    box-shadow: x偏移量 y偏移量 模糊半径 扩展半径 阴影颜色 模式(内。外);
    box-shadow: 0 10px 15px 4px black inset
}
```



## CSS 渐变	(Gradients)

> **线性渐变（Linear Gradient）上下左右对角方向**
>
> **径向渐变（Radial Gradient）由中心定义**
>
> 颜色可以使用透明度 rgba

```css
.style {
    /* 默认从上到下 */
    background-image: linear-gradient(red, blue);
    
    /* 从左到右 */
    background-image: linear-gradient(to right, red, blue);
    
    /* 左上到右下 */
    background-image: linear-gradient(to bottom right, red, blue);
    
    /* 任意角度 */
	background-image: linear-gradient(45deg, red, blue)
}
```

**deg 大部分浏览器使用了旧的标准默认情况下 0deg 就是从左到右 90deg 才是从上到下** 

<img src="img/css/deg.jpg" alt="img" style="zoom:50%" />

颜色可以设置多种

```css
.style {
    /* 彩虹色 */
    background-image: linear-gradient(red, orange, yellow, green, blue, indigo, violet)
}
```

重复线性渐变

```css
.style {
    background-image: repeating-linear-gradient(red, yellow 20%, blue %10%)
}
```



### 径向渐变

```css
.style {
    /* 普通样式 */
    background-image: radial-gradient(red, yellow, green);
    
    /* 分配比例 */
    background-image: radial-gradient(red %10, yellow %20, blue %40);
    
    /* 设置形状（默认是椭圆 ellipse） */
    background-image: radial-gradient(circle, red, yellow, green);
    
    /* 重复渐变 */
    background-image: repeating-radial-gradient(red, yellow 10%, green 15%);
}
```

<hr><br>



## CSS3 transform 2d变换

> 在平面上的平移(translate)、旋转(rotate)、缩放(scale)、倾斜(skew)

```css

.style {
    /* 复合写法 */
	transform: translate() rotate() scale() skew();
    transform-origin: x-axis y-axis z-axis;
    
    /* translate(x值, y值) 平移 */
    /* 单独设置 translateX/translateY */
    transform: translate(10px, 40px);
    
    /* rotate(旋转值) 旋转 单位:deg*/
    transform: rotate(45deg);
    
    /* scale(等比例缩放值)/scale(x缩放值, y缩放值) 缩放 */
    transform: scale(2,4);
    
    /* skew(x值, y值) 倾斜 单位:deg */
    transform: skew(10deg, 30deg);
}
```

<hr><br>

## CSS3 transition（过度）

```css
.style {
    transition: 过度属性名称 过度需要的时间 过度速度曲线 延时过度开始时间;
   	transition: color 1s linear 0.5s;
}
```

| 值           | 描述                                                         |
| ------------ | ------------------------------------------------------------ |
| linear       | 从开始到结束都是相同的速度（等于：cubic-bezier(0,0,1,1)）    |
| ease         | 开始慢随后变快结束又变慢（等于：cubic-bezier(0.25, 0.2, 0.25, 1) |
| ease-in      | 开始慢随后变快（等于 cubic-bezier(0.42, 0, 1, 1)）           |
| ease-out     | 结束慢（等于 cubic-bezier(0, 0, 0.58, 1)）                   |
| ease-in-out  | 和ease差不多（等于 cubic-bezier(0.42, 0, 0.58, 1)）          |
| cubic-bezier | cubic-bezier(n, n, n, n) n 的值可以是0~1之间                 |

> cubic-bezier是贝兹曲线的绘画方法

<img src="img/css/贝兹曲线.jpg">

<hr><br>
## CSS3 animation @keyframes（帧动画）

```css
@keyframes AnimationName {
	0% {
        color、left、width等属性;
    }
    25% {
        color、left、width等属性;
    }
    50% {
        color、left、width等属性;
    }
    100% {
        color、left、width等属性;
    }
}
```

### 播放动画 animation

```css
.style {
	animation: Name(动画帧名字) | duration(持续时间) | timing-function(贝兹曲线) | delay(延迟时间) | iteration-count(迭代次数) | direction(动画方向)
}
```

| 属性            | 单位                                                         |
| --------------- | ------------------------------------------------------------ |
| duration        | s(秒)                                                        |
| timing-function | ease \| linear \| ease-in \| ease-out \| ease-in-out \|cubic-bezier(0,0,0) |
| delay           | s(秒)                                                        |
| iteration-count | number \| infinite(无限一直循环)                             |
| direction       | normal \| alternate                                          |



### animation-play-state

> 控制动画播放状态：running(播放(默认值))、pause(暂停)



# CSS3 flex 弹性布局

> 传统的布局方式基于**盒子模型**，依赖属性 **display float position** 对于一些特殊的布局相对来说比较麻烦，如**垂直居中**就不容易实现。
>
> 2009年 W3C提出了新方案 **flex** 布局，它可以简便、完整、且具有响应式的实现各种页面布局。目前所有浏览器均支持，flex布局已经是现在主流的布局方式，特别是在移动端、小程序上表现出色。->[flex](flex\flex.md)



## Web字体

### 字体格式

.ttf .otf .woff .eot .svg



### 字体图标

> 字体图标可以和图片一样，更改透明度、旋转等，同时它本质上是属于文字，它也拥有颜色、阴影、透明效果等各种属性，本身体积会更小，但是携带的信息没有缩减，放大缩小不会失真，几乎支持所有浏览器，移动端很常用。



### 字体包网站

**icomoon字库：**http://icomoon.io

**阿里icon font字库：**http://www.iconfont.cn/

**fontello：**http://fontello.com/

**Font-Awesome：**http://fortawesome.github.io/Font-Awesome/

**Glyphicon Halflings：**http://glyphicons.com/

**Icons8：**https://icons8.com/



### 字体引入到HTML

```css
/* 声明字体 */
@font-face {
  font-family: "font-icon";
  src: url('fonts/icomoon.eot?7kkyc2');
  src: url('fonts/icomoon.eot?7kkyc2#iefix') format('embedded-opentype'),
    url('fonts/icomoon.ttf?7kkyc2') format('truetype'),
    url('fonts/icomoon.woff?7kkyc2') format('woff'),
    url('fonts/icomoon.svg?7kkyc2#icomoon') format('svg');
  font-weight: normal;
  font-style: normal;
}

/* 给盒子使用该字体 */
span {
  font-family: "font-icon";
}

/* 添加内容使用字体 */
span::before {
  content: "\e913";
}

/* 自定义图标 */
.iconfont {
  font-family: "font-icon" !important;
  font-size: 16px;
  font-style: normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

```html
<!-- 应用于页面(Unicode引用) -->
<span class="iconfont">&#x33;</span>
```



### Symbol引用

> 和前面上面不一样的是，它支持多色图标，缺点也明显，兼容性差，浏览器渲染 SVG 性能一般，还不如直接使用图片



## 兼容处理

### meta强制解析模式

> x-ua-compatible 用来指定IE浏览器解析编译页面的model
> x-ua-compatible 头标签大小写不敏感，必须用在 head 中，必须在除 title 外的其他 meta 之前使用。

```html
<meta http-equiv="x-ua-compatible" content="IE=8" >
<meta http-equiv="x-ua-compatible" content="IE=EmulateIE8" >
<meta http-equiv="x-ua-compatible" content="IE=edge" >
<meta http-equiv="x-ua-compatible" content="IE=7,9,10" >
<meta http-equiv="x-ua-compatible" content="IE=Edge,chrome=1" >
```

### 指定多和浏览器(360、搜狗)渲染内核

> **极速核：**webkit	
>
> **ie兼容内核：**ie-comp	
>
> **ie标准内核：**ie-stand

```html
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```



### 兼容前缀

| 浏览器前缀 | 浏览器                                     |
| ---------- | ------------------------------------------ |
| -webkit-   | Google Chrome \| Safari \| Android Browser |
| -moz-      | Firefox                                    |
| -ms-       | IE \| Edge                                 |
| -o-        | Opera                                      |
| -khtml-    | Konqueror                                  |

> 如果css样式在主流浏览器中需要加兼容前缀才能生效, 就先写兼容写法 最后写标准写法。

```css
.style {
    -webkit-box-shadow: 2px 2px 4px #333;
    -moz-box-shadow: 2px 2px 4px #333;
    box-shadow: 2px 2px 4px #333;
}
```



### 兼容查询

**[工具网站](https://www.caniuse.com/)**

> 输入要查询的属性一般有一下三种情况：
>
> 1、红色标签代表 完全不兼容
>
> 2、绿色标签代表 完全兼容
>
> 3、黄色标签代表 兼容但需要加 兼容方案



## 3D变换 transform3D

**位置属性：**

1. translateX
2. translateY
3. translateZ
4. translate3D(x, y, z)



### 3D景深 perspective

> z轴的深度 perspective只影响3D元素，默认情况下 Z轴 的起始位置在水平线垂直线的交叉点，可以设置perspactive-origin来调整起始位置

```css
.style{
    perspactive: 100px;
    perspactive: 
}
```



### transform-style

> 必须设置 transform 才可以进行3D的变换

| 值          | 描述                       |
| :---------- | :------------------------- |
| flat        | 子元素将不保留其 3D 位置。 |
| preserve-3d | 子元素将保留其 3D 位置。   |

```css
.style {
    transform-style: flat | preserve-3d;
}
```



### backface-visibility 

> backface-visibility 元素背面是否可见

| 值      | 描述             |
| :------ | :--------------- |
| visible | 背面是可见的。   |
| hidden  | 背面是不可见的。 |



## visibility

> visibility 用来控制一个元素是否可见，与 display: none; 不一样的是display: none; 浏览器不会渲染此元素，而使用visibility隐藏元素，元素还是存在文档流当中，只是不可见。
>
> 1、visibility 有继承性，给父元素设置了visibility: hidden; 后，它的子元素也会继承这个属性跟着隐藏。
>
> 2、设置属性 visibility: hidden; 不会影响计数器计数，而 display:none 是直接不存在，也就会有相应的影响。
>
> 3、transition 支持 visibility属性，但是不支持display。
>
> 4、因为visibility有继承，所以子元素需要显示可以单独设置，visibility:visible; 来显示该元素。
>
> 5、属性 opacity 也有继承性，但是对子元素单独设置 opacity 来将其元素重新显示。



## filter 滤镜

| 属性           | 属性值           |
| -------------- | ---------------- |
| none           | 默认值（无效果） |
| blur (px)      | 高斯模糊         |
| brightness (%) | 控制亮度         |
| contrast (%)   | 对比度           |
| grayscale      | 灰度             |



## CSS 变量

> 设置统一变量，方便修改维护，而且变量也有权重关系

```css
/* 声明变量 */
body {
    --value: red;
}

.style {
    /* 调用变量 */
    color: var(--value);
    /* 变量可以有多个参数 如果第一个不存在会选择第二个参数且不管后面有几个参数都算是第二参数 */
    color: var(--value, #fff);
}
```



## CSS content 计数器

> 设置一个初始变量来工具规则递增

### CSS 计数器属性

- **counter-reset - 创建/重置计数器**
  - `counter-reset: counter名称`

- **conter-increment - 递增值**
  - `counter-increment: counter名称 起始数值(默认1)`
- **counter() 或 counters 函数将计数器添加到content中**
  - 配合伪元素的 `content` 使用 `content: counter(counter名称)`

```html
<head>
	<style>
        .container {
            counter: counter-1;
        }
        
        .container p::before {
			content: '这是第 ' counter(counter-1) '个元素';
            display: inline;
            counter-increment: counter-1 1;
        }
    </style>
</head>

<body>
    <div class="container">
        <p></p>
        <p></p>
    </div>
</body>
```

