# Online-Document

> Claw学习前端的笔记

------

# HTML

### h 标签

```html
<!-- h1 h2 h3... -->
<h1>h标签</h1>
```

### p 标签

```html
<p>p标签</p>
```

### a 标签

```html
<a href="链接地址" target=""></a>
```

`target默认为当前窗口跳转 可以设置为"_blank"使其重新打开新的链接页面`

### img 标签

```html
<img src="路径 | 相对路径 | 绝对路径" width="宽" height="高" alt="提示文字" title="">
```

### base标签

```html
<base target="_blank">
```

`base应该写在head之内`

### 转义字符

|    代码    |  含义  |
| :--------: | :----: |
| &amp;nbsp; |  空格  |
|  &amp;lt;  |   <    |
|  &amp;gt;  |   >    |
| &amp;yen;  | &yen;  |
| &amp;copy; | &copy; |
| &amp;reg;  | &reg;  |

### 文本格式化标签

```html
<b></b> | <strong></strong> 粗体
<i></i> | <em></em> 斜体
<s></s> | <del></del> 删除线
<u></u> | <ins></ins> 下划线
```

` b i s u 是基础的表现形式strong em del ins的语义更强烈 两者都可以实现相同的效果`

