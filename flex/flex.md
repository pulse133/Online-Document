[TOC]

所有插图和知识点均来自[此站](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-order)

# flex

2009年，W3C提出了一种新的布局方案 **flex** 弹性布局，弹性布局的主要思想是能够使 容器(container) 改变 项目(item)的 **宽度、高度和顺序** 以便于更好的填充利用可用空间(适应所有类型的显示设备和屏幕尺寸)，弹性容器扩展项目可以填充可用空间，或缩小项目以防止溢出。

与常规布局不同的是，弹性布局更为灵活，特别是在方向更改、调整大小、拉伸、缩小等方面。

> PS：**弹性布局** 适合用在程序的组件或者小规模布局，而 **网格** 布局适用于比例较大的布局。



## flex container

### display

> 定义一个flex容器(container)，inline 或者 block 元素都可以设定为flex。

![container](\01-container.svg)

```css
.conrainer {
    display: flex;	/* or inline-flex */
}
```



### flex-direction

> direction(方向) 定义主轴的方向，这将决定 flex项目(item) 在 flex容器(container) 中的元素的排序方向。

| 属性值         | 作用                                           |
| -------------- | ---------------------------------------------- |
| row            | 默认项 主轴从**左->右** 交叉轴不变**(上->下)** |
| row-reverse    | 主轴从**右->左**排序 交叉轴不变**(上->下)**    |
| column         | 主轴从**上->下** 交叉轴从**左->右**            |
| column-reverse | 主轴从**下->上** 交叉轴不变                    |

```css
.container {
    display: flex;
    flex-direction: row | row-reverse | column | column-reverse;
}
```



### flex-wrap

> 默认 `nowrap` 情况下所有的 `flex项(item)` 都只会显示在同一行上，可以根据项目的需求来设置。

| 属性值       | 作用                              |
| ------------ | --------------------------------- |
| nowrap       | 默认值 所有的flex项都会在同一行   |
| wrap         | 超出flex容器宽度自动换行          |
| wrap-reverse | 超出容器换行 但是方向是从下到上的 |

```css
.container {
	dispaly: flex;
    flex-wrap: nowrap | wrap | wrap-reverse;
}
```





### flex-flow

> `flex-direction` 和 `flex-wrap` 的复合写法默认值为 `row`  `nowrap`

```css
.container {
	flex-flow: column wrap;
}
```



### justify-content

>设置主轴的对齐方式，能够更好的分配空出来的空间，并在有溢出发生时会对flex项对齐做一定的调整。

```css
.container {
    display: flex;
    justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

`不同浏览器对这些属性值可能在显示上会有细微的差别，最安全的值是space-between flex-start flex-end center`

<img src=".\justify-content.svg" width=400>



### align-items

> 定义 `flex项` 在交叉轴上的弹性布局显示

```css
.container {
    align-items: stretch(default) | flex-start | flex-end | center | baseline;
}
```

`flex-start = start = self-start` `flex-end = end = self-end`

<img src=".\align-items.svg" width=400>



### align-content

> 设置交叉轴 `flex容器` 线条对齐的方式，类似主轴的对齐方式 `justify-content` 。

```css
.container {
    display: flex;
    align-content: flex-start | flex-end | center | space-between | space-around | space-evenly | stretch | normal(default);
}
```

`flex-start = start` `flex-end = end`

`PS：此属性只能够在多行的flex容器上生效 单行的flex容器将不会生效`

<img src=".\align-content.svg" width=400>



### gap row-gap column-gap

> 用来控制 `flex项` 之间的距离。可以认为这个属性是设置元素之间的最小间隔，当空间变小时它才会生效



```css
. container {
    display: flex;
    gap: 10px;
    gap: 10px 20px;	/* row-gap column-gap */
    row-gap: 10px;
    column-gap: 20px;
}
```

`gap 不仅仅适用于弹性布局，也同样适用于网格和多列布局`

<img src=".\gap-1.svg" width=400>

## flex items

### order

> 控制 `flex项` 的排序先后，默认情况下是按照顺序排列。

```css
.item {
    order: 4;	/* default 0 */
}
```

<img src=".\order.svg" width=400>



### flex-grow

> 用来定义 `flex项` 的放大比例，数值为放大倍数且不能为 `负数` 。

```css
.item {
    flex-grow: 2;	/* default 0 */
}
```

<img src=".\flex-grow.svg" width=400>



### flex-shrink

>用来定义 `flex项` 的缩小比例，在参数上和 `flex-grow` 一样。

```css
.item {
    flex-shrink: 4;	/* default 1 */
}
```



### flex-basis

> 定义了在分配 `flex容器` 之前元素 `flex项` 的默认大小，单位可以是长度 `20% 5rem等` 或者关键字暂时不建议使用关键字。

```css
.item {
    flex-basis: length | auto;	/* default auto */
}
```



### flex

> `flex` 是 `flex-grow` `flex-shrink` `flex-basis` 的复合写法，建议使用简写。默认值是：`0` `1` `auto` 后两个属性可以忽略。

```css
.item {
    flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ];
}
```



### align-self

> `align-self` 允许单个flex项与其他的flex项有不一样的对齐方式，设置此属性将会覆盖 `align-items` 默认值为auto，继承父元素的 `align-items` 如果没有父元素则等于 `stretch`

```css
.item {
    align-self: auto | flex-start | flex-end | center | stretch;
}
```

<img src=".\align-self.svg" width=400>
