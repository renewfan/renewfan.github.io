---
title: flex
date: 2018-12-14 15:55:46
tags:
- flex
- 小程序
- css
categories: 
- notes
copyright: 
---
# flex布局
<!-- toc -->
盒子模型；box-sizng

正常增加div默认为content-box   (box-sizing:content-box)

    改变padding、border等属性时，盒子向外扩展，盒子会变大

box-sizing:border-box   

​    改变padding、border等属性时，盒子向内扩展，盒子不会变大

## 弹性盒子

在父级元素添加 display:flex;   (浏览器兼容display:-webkit-flex;)

如果用了弹性布局，子元素不需要float、clear等父级flex的其他属性

### 方向：

**flex-direction:row;**

```
row             横向
row-reverse     横向反转，对齐方式也会进行反转
column          纵向
column-reverse  纵向反转，对齐方式也会进行反转
```

## 子元素水平排列：

**jusitfy-content:flex-start;**

```
flex-start      居左
flex-end        居右
center          居中
space-between   两端对齐，平均分布
space-around    子元素均匀分布，等距分布
```

在父级元素中进行方向反转后，若需要再次按照原来方想对齐则需要将子元素排列方法也反转

```
flex-direction:row;
jusitfy-content:flex-start;
flex-direction:row-reverse;
jusitfy-content:flex-end;
```

### 子元素垂直排列：

定义子元素在交叉轴上如何对齐

**flex-direction设置的主轴，默认为row（水平）在主轴方向居中**

#### 单行

**align-items:flex-start;**

```
stretch     拉伸（父级有高度时默认值，相当于不加；父级没有宽度或者高度会拉伸填充）
flex-start  居顶
flex-end    居底
center      居中
baseline    将子元素中文字基线(底部)对齐，以第一个子元素中文字基线为标准
```

![](https://ws3.sinaimg.cn/large/005BYqpgly1fy6cbr8qf2j306x02kwek.jpg)

#### 多行

**align-content:stretch;**

```
stretch 拉伸（默认值，相当于不加）
flex-start  居左
flex-end    居右
center  居中
```

子元素排列方向：

    flex-direction:row;
            row 横向
            row-reverse 横向反转
            column  纵向
            column-reverse  纵向反转
    //ps:将元素方向改为column纵向时再使元素居中需要垂直水平都居中
            flex-direction:column;
            align-items:center;
            jusitfy-content:center;
### 子元素是否换行：

**​ flex-wrap:no-wrap;**

```
nowrap  不换行
wrap    换行
```

组合写

```
flex-flow：<' flex-direction '> || <' flex-wrap '>
flex-flow:column nowrap;
```

### 子元素属性：

**flex   系数，数字**
复合属性。设置或检索弹性盒模型对象的子元素如何分配空间。

- 如果缩写「flex: 1」, 则其计算值为「1 1 0%」
- 如果缩写「flex: auto」, 则其计算值为「1 1 auto」
- 如果「flex: none」, 则其计算值为「0 0 auto」
- 如果「flex: 0 auto」或者「flex: initial」, 则其计算值为「0 1 auto」，即「flex」初始值
- 子元素在划分父元素宽度，先去除固定宽度
- 弹性盒子布局定位需要在弹性盒子外包裹一层，然后对外边不是弹性盒子的块进行定位

**flex-grow：<number>**

- 设置弹性盒的扩展比率。
-  根据弹性盒子元素所设置的扩展因子作为比率来分配剩余空间。

**align-self：auto；**

- 单独设置子元素y轴对齐方式
- stretch   拉伸
-  flex-start   居左
- flex-end  居右
- center    居中

**order**

​        设置或检索弹性盒模型对象的子元素出现的顺序。

​        order定义将会影响 <' position '> 值为static元素的层叠级别，

​        数值小的会被数值大的盖住。