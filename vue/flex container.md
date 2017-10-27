Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。
任何一个容器都可以指定为 Flex 布局。
```html
<div class="dflex"></div>
.dflex{
    display:flex;
}
行内元素也可使用 line-flex
<span>
</span>
span{
    display:line-flex;
    
}
变成了块元素
```
Webkit 内核的浏览器，必须加上 -webkit 前缀。

注意，设为 Flex 布局以后，子元素的 float 、 clear 和 vertical-align 属性将失效。 

### 基本概念

采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目
（flex item），简称"项目"  
![flex](d:/笔记/book/flex.png)  

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做
main start ，结束位置叫做 main end ；交叉轴的开始位置叫做 cross start ，结束位置叫做 cross end 。   

项目默认沿主轴排列。单个项目占据的主轴空间叫做 main size ，占据的交叉轴空间叫做 cross size 。
  

---

 ### flex 属性
 
 * flex-direction:主轴的方向
 ```
 .box{
     flex-direction:row|row-reverse|column|column-reverse
 }
 ```
 ![direction](d:/work/b.png)
 
 * row（默认值）：主轴为水平方向，起点在左端
 * row-reverse :起点在右
 * column 主轴为纵向，起在上
 * colum 起点在下
 * 
 
### flex-wrap
默认情况下，项目都排在一条线（又称"轴线"）上。 flex-wrap 属性定义，如果一条轴线排不下，如何换行。
```css
.box{
    flex-wrap:no-wrap|wrap|wrap-reverse
}
```
wrap-reverse ：换行，第一行在下方。

---
### flex-flow
flex-flow 属性是 flex-direction 属性和 flex-wrap 属性的简写形式，默认值为 row nowrap 。
```
flex-flow:flex-direction|flex-wrap;
```
----
### justify-content属性
justify-content:定项目在主轴对齐的方式
```
.box {
justify-content: flex-start | flex-end | center | space-between | space-around;
}
```

* flex-start（默认值）：左对齐
* flex-end：右对齐
* center： 居中
* space-between：两端对齐，项目之间的间隔都相等。
* space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍
flex-flow:row no-wrap
![flex](d:/work/justify.png)

---

### align-items属性
align-items定义项目在交叉轴对方齐方式
>flex-flow:row nowrap;
```
.box {
align-items: flex-start | flex-end | center | baseline | stretch;
}
```
1.flex-start：交叉轴的起点对齐。  
2.flex-end：交叉轴的终点对齐。  
3.center：交叉轴的中点对齐。    
4.baseline: 项目的第一行文字的基线对齐。  
5.stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度

![item](d:/work/item.png)
---
### align-content属性
aliign-content设定多个轴对齐方式
```
.box{
    align-content:flex-end|flex-start|center|space-between|space-around|stretch
    
}
```  
* flex-start：与交叉轴的起点对齐。
* flex-end：与交叉轴的终点对齐。
* center：与交叉轴的中点对齐。
space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
* space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
* stretch（默认值）：轴线占满整个交叉轴
![content](d:/work/content.png)