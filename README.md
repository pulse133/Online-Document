# Online-Document

> Claw学习前端的笔记

------

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
<img src="路径 | 相对路径 | 绝对路径" width="宽" height="高" alt="文字描述" title="鼠标悬停显示的内容">
```



## base标签

```html
<base target="_blank">
```

`base应该写在head之内`



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

> 可以用负数 建议使用em

```css

```

