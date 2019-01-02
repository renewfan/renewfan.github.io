---
title: 基础CSS
date: 2018-12-18
tags:
    - css
categories: css
copyright: true
---
# CSS
<!-- toc -->

## css选择器：

标签选择器：html标签选择，

```
span{
    
}
```

id选择器：

```
#id{
    
}
```

class类选择器：

```
.class{
    
}
```

关联选择器：

```
.class h1{
    color:red;
}
```

伪元素选择器：（ie）

```
 a:link{
    color:red;
    font-size:2em
 } 
 //默认  active点击  
 visited点击完  hove
```

组合选择器：多个选择器逗号连接一起使用

## 字体

```
font-famliy:字体名;  //字体样式 
font-size:20px;     //字体大小
color:red;          //颜色
font-weight:bold;   //字体粗细 
```

```
normal：正常的字体。相当于数字值400
bold：粗体。相当于数字值700。
bolder：定义比继承值更重的值
lighter：定义比继承值更轻的值
用数字表示文本字体粗细。
    取值范围：100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900
```

```
font-size:normal; 
normal：指定文本字体样式为正常的字体
italic：指定文本字体样式为斜体。
        对于没有设计斜体的特殊字体，如果要使用斜体外观将应用oblique
oblique：指定文本字体样式为倾斜的字体。
        人为的使文字倾斜，而不是去选取字体中的斜体字
```

## **背景**

**body、h1、p等标签本身含有边距，用全局清除页边距**

```
*{margin:0px;padding:0px}
```

背景色\背景图

```
backgroung-color:red;
background-image:url('图片路径'); //none：无背景图。
//当同时定义了背景颜色和背景图像时，背景图像覆盖在背景颜色之上。
background-repeat:repeat; //是否平铺
background-position:left top; 
```

多组背景图，且背景图之间有重叠，写在前面的将会盖在写在后面的图像之上

### 背景位置

一个参数时用于横向和纵向

如果提供全部2个参数，第1个用于横向，第二个用于纵向

```
repeat-x：背景图像在横向上平铺
repeat-y：背景图像在纵向上平铺
repeat：背景图像在横向和纵向平铺
no-repeat：背景图像不平铺（不平埔时其他区域用背景色填充）
round：背景图像自动缩放直到适应且填充满整个容器。（CSS3）
space：背景图像以相同的间距平铺且填充满整个容器或某个方向。（CSS3）
```

```
background-position:left top;    （左上角为0，0），所以位置上移时为负值

该属性提供2个参数值（CSS3中已允许提供3，4个值）。
设置3个或4个值，偏移量前必须有关键字
如果提供两个，第一个用于横坐标，第二个用于纵坐标
如果只提供一个，该值将用于横坐标；纵坐标将默认为50%（即center）。
```

###   

```
- 背景图像在容器中右下方，并且距离右边和底部各有20px

background:url(test1.jpg) no-repeat right 20px bottom 20px;

enter：背景图像横向和纵向居中。
left：背景图像在横向上填充从左边开始。
right：背景图像在横向上填充从右边开始。
top：背景图像在纵向上填充从顶部开始。
bottom：背景图像在纵向上填充从底部开始。
```

### 背景滚动      

```
background-attachment:scroll;

设置或检索背景图像是随对象内容滚动还是固定的。必须先指定 background-image 属性。

fixed：背景图像相对于窗体固定。
scroll：背景图像相对于元素固定，
    当元素内容滚动时背景图像不会跟着滚动，但会随元素的祖先元素或窗体一起滚动。
local：
    背景图像相对于元素内容固定，
    当元素随元素滚动时背景图像也会跟着滚动，因为背景图像总是要跟着内容。（CSS3）
```

## 文本

### 文本下划线

```
text-decoration:none;(文本装饰的种类，如a标签去除下划线)
                none | underline | overline | line-through | blink（带闪烁文字）
```

文本位置

```
text-align:start;

left：内容左对齐。
center：内容居中对齐。
right：内容右对齐
```

**文字在容器中因为容器高度只使用text-align无法居中时使用line-height将文字所在位置高度设置为容器高度行高，设置文字居中**

设置对象的行高。

即字体最底端与字体内部顶端之间的距离

```
line-height:normal;
line-height:20px;
```

### 首行缩进

```
text-index:0px;
    length：用长度值指定文本的缩进。可以为负值。
    each-line：
        定义缩进作用在块容器的第一行或者内部的每个强制换行的首行，软换行不受影响。（CSS3）
    hanging：
        反向所有被缩进作用的行。（CSS3）
```

###  文本换行

```
word-break：normal；（碰到容器边界进行折行）

normal：依照亚洲语言和非亚洲语言的文本规则，允许在字内换行。
keep-all：
    与所有非亚洲语言的normal相同。对于中文，韩文，日文，不允许字断开。适合包含少量亚洲文本的非亚洲文本。
break-all：
    该行为与亚洲语言的normal相同。也允许非亚洲语言文本行的任意字内断开。该值适合包含一些非亚洲文本的亚洲文本，比如使连续的英文字母间断行
```

光标

```
cursor:auto;    
    help | pointer |  wait
```

### 边框

```
border:2px solid red;
border：<line-width> || <line-style> || <color> 
        <line-style>= none | hidden | dotted | dashed | solid | double | inset | outset
```

列表

```
list-style：< list-style-type > || < list-style-position> || < list-style-image >

<list-style-type>：设置或检索对象的列表项所使用的预设标记
    默认值：disc
        disc：实心圆
        circle：空心圆
        square：实心方块
        decimal：阿拉伯数字
        none：不使用项目符号
<list-style-position>：设置或检索作为对象的列表项标记如何根据文本排列
    默认值：outside   inside
<list-style-image>：设置或检索作为对象的列表项标记的图像
```

文本域

​    textarea标签     设置文本框不可拖动   `resize:none;`

表格

```
border-collapse：separate；
    设置表格的行和单元格的边是合并还是独立
        separate：边框独立
        collapse：相邻边被合并

border-spacing：0；
    设置当表格边框独立时，行和单元格的边框在横向和纵向上的间距
    该属性作用等同于标签属性cellspacing(单元格边距)。

border-spacing:0等同于cellspacing="0"
    只有当表格边框独立（即border-collapse:separate）此属性才起作用

empty-cells:show;
    hide：指定当表格的单元格无内容时，隐藏该单元格的边框。
    show：指定当表格的单元格无内容时，显示该单元格的边框
    只有当表格边框独立（即border-collapse:separate）此属性才起作用
```

### 外边距

```
margin  设置对象四边的外延边距。
```

- 如果提供全部四个参数值，将按上、右、下、左的顺序作用于四边。
- 如果只提供一个，将用于全部的四边。
- 如果提供两个，第一个用于上、下，第二个用于左、右。
- 如果提供三个，第一个用于上，第二个用于左、右，第三个用于下。
- 非替代(non-Replaced)行内元素可以使用该属性设置左、右两边的外补丁；若要设置上、下两边的外补丁，必须先使该对象表现为块级或内联块级。
- 外延边距始终透明。

### 内边距

```
padding
```

使用padding会增加块的宽高，所以在使用padding时对应的将块的宽高进行增减

设置对象四边的内部边距。

- 如果提供全部四个参数值，将按上、右、下、左的顺序作用于四边。
- 如果只提供一个，将用于全部的四边。
- 如果提供两个，第一个用于上、下，第二个用于左、右。
- 如果提供三个，第一个用于上，第二个用于左、右，第三个用于下。

### 定位

```
position：static
```

static：对象遵循常规流。此时4个定位偏移属性不会被应用。

absolute：

- 对象脱离常规流，此时偏移属性参照的是离自身最近的定位祖先元素，如果没有定位的祖先元素，则一直回溯到body元素。盒子的偏移位置不影响常规流中的任何元素，其margin不与其他任何margin折叠。

relative：

- 对象遵循常规流，并且参照自身在常规流中的位置通过top，right，bottom，left这4个定位偏移属性进行偏移时不会影响常规流中的任何元素。

相对上级元素的位置进行定位

- fixed：与absolute一致，但偏移定位是以窗口为参考。当出现滚动条时，对象不会随着滚动。

- z-index: auto

- auto：元素在当前层叠上下文中的层叠级别是0

  ​      用整数值来定义堆叠级别。可以为负值。

设置对象的层叠顺序。

- z-index用于确定元素在当前层叠上下文中的层叠级别，并确定该元素是否创建新的局部层叠上下文。
- 同一个层叠上下文中，层叠级别大的显示在上面，反之显示在下面。



### block、inline、inline-block

block-level elements (块级元素) 和 inline elements (内联元素)

block

- 使元素变成块级元素，独占一行，在不设置自己的宽度的情况下，块级元素会默认填满父级元素的宽度
- 能够改变元素的height，width的值
- 可以设置padding，margin的各个属性值，top，left，bottom，right都能够产生边距效果
- 常见的块级元素有 div, form, table, p, pre, h1~h6, dl, ol, ul 等

inline

- 使元素变成行内元素，拥有行内元素的特性，即可以与其他行内元素共享一行，不会独占一行
- 元素前后不会产生换行，一系列inline元素都在一行内显示，直到该行排满
- 不能更改元素的height，width的值，大小由内容撑开
- 可以使用padding，margin的left和right产生边距效果，但是top和bottom就不行
- 常见的内联元素有 span, a, stong, en, label, input, select, textarea, img, br 等

inline-block:不独占一行的块级元素

- 使元素变成行内元素，拥有行内元素的特性，即可以与其他行内元素共享一行，不会独占一行
- 能够改变元素的height，width的值
- 可以设置padding，margin的各个属性值，top，left，bottom，right都能够产生边距效果

block元素可以包含block元素和inline元素；但inline元素只能包含inline元素。