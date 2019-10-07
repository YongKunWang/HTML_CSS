# 课程目标

>1. 学会使用CSS选择器
>2. 熟记CSS样式和外观属性
>3. 熟练掌握CSS各种选择器
>4. 熟练掌握CSS三种显示模式
>5. 熟练掌握CSS背景属性
>6. 熟练掌握CSS的三大特性
>7. 熟练掌握CSS盒子模型
>8. 熟练掌握CSS浮动
>9. 熟练掌握CSS定位
>10. 熟练掌握CSS高级技巧强化

# CSS 相关

CSS 的最大贡献是：让HTML从样式中解脱出来，实现了HTML专心去做结构呈现；CSS交给样式

CSS的样式做的非常出色，如果JavaScript是网页的魔法师，则CSS则是网页的美容师

![](../media/CSS/baby.jpeg)

# CSS样式表引入（书写位置）

## 内部样式表

书写位置：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>内部样式表</title>
	<style>
		h3 {
			color: skyblue;
			font-size: 50px;
		}
	</style>
</head>
<body>
	<h3>内部样式表</h3>
</body>
</html>
```

书写格式：

```html
<style>
	标签名称 {
		属性：值；
		属性：值；	
	}
</style>
```

![](../media/CSS/内部样式表.png)

## 行内式（内联样式）

书写位置：

```html
<h3 style="colcor:pinl; font-size:30px">
```

![](../media/CSS/行内式样式表.png)



## 外部样式表（外链式）

书写位置：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>外部样式表</title>
	<link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
	<h3>外部样式表</h3>
</body>
</html>
```

书写格式：

```html
<head>
	<link href="CSS文件路径" rel="stylesheet" />
</head>
```

注意：

`link`是一个单标签！！！

link放在head头部标签中，并且指定link标签的三个属性，具体如下：

```
href:CSS文件的放置位置
rel：定义当前文档和被连接文档之间的关系，这里是'stylesheet'
type:定义所链接文档的类型，在这里指定为“text/CSS” 表示链接的外部文件为CSS样式表
```



![](../media/CSS/外部样式表.png)

## 三种样式表的总结

![](../media/CSS/样式表总结.png)

# CSS样式规则

CSS样式规则：

![](../media/CSS/gz.png)

```
在上面的样式规则中：

1. 选择器用于指定CSS样式作用的HTML对象，{}为具体的属性和值
2. 属性和值是以键值对的形式出现的
3. 属性是指对象样式的属性
4. 属性和值之间使用英文符号的":"来进行连接
5.多个键值对之间使用“;”来进行连接
```

# 选择器

## 标签选择器

标签选择器是指使用HTML的标签名称做选择器，按照标签名称进行分类，其基本格式如下：

```
标签名 {属性：值；属性：值;}
元素名称{属性：值； 属性:值;}
```

- 优点：快速的为页面的中同一类型的标签统一样式
- 缺点：不能设计差异化

## 类选择器

类选择器使用"."进行标识，后面紧跟类名，其语法格式如下：

```
.类名{属性：值； 属性：值；}
```

类名的定义：

```
class="类名"
```

- 优点：为元素对象定义单独或者相同的样式，可以选择一个或者多个标签

![](../media/CSS/good.png)小技巧：

```
1.长名称推荐使用中横线来为选择器命名
2.不建议使用_来命名CSS选择器
3.不要用纯数字、中文等命名，尽量使用英文字母来表示
```

例子：

![](../media/CSS/go.png)

![](../media/CSS/Google图标.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Google图标</title>
	<style type="text/css">
		span {
			font-size: 100px;
		}
		.G {
			color:skyblue;
		}
		.o {
			color: red;
		}
		.o2 {
			color: orange;
		}
		.l {
			color: green;
		}
		.e {
			color: red;
		}
	</style>
</head>
<body>
	<span class="G">G</span>
	<span class="o">o</span>
	<span class="o2">o</span>
	<span class="G">g</span>
	<span class="l">l</span>
	<span class="e">e</span>
</body>
</html>
```



## 多类选择器

我们可以给标签指定多个类名，从而达到更多选择的目的

注意：

```
1. 样式显示效果根HTML元素中类名的先后顺序没有关系，受CSS样式书写的上下顺序有关系
2. 各个类名中间使用空格间隔
```

```html
<div class="pink fontWeight font20"> 亚索 </div>
<!--多样式重叠-->
```

![](../media/CSS/多类选择器.png)

## id选择器

id选择器使用“#”来进行标识，后面紧跟id名称，其基本语法格式如下：

```
#id {属性：值；属性：值；}
```

该语法中，id名即为HTML元素的id值，大多数的HTML元素都可以定义id属性，元素的id值是唯一的

## 通配符选择器

通配符选择器使用“*”来表示，它是所有选择器中作用范围最广的，能匹配页面中所有元素，其基本语法格式如下：

```
* {属性1：值；属性2：值}
```

## id选择器 和类选择器之间的区分

W3C规定，在同一个页面中，不允许有相同名字的id的对象出现，但是允许相同名字的calss出现

calss选择器比作名字，可以重名

id选择器比作人的身份证，全中国唯一，不得重复，只能使用一次

# CSS样式属性

## `font-size` 字体大小

## `font-family` 字体

## `CSS Unicode `字体

## `font-weight` 字体粗细

## `font-style` 字体风格

## `font` 综合设置字体样式

