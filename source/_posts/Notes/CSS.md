---
title: CSS
date: 2023-03-17
tags:
---



# CSS

*Cascading Style Sheets*

## 引入方式

1. 内嵌式：小案例

   写在style标签中，style标签一般写在head标签内，title标签下

   ```html
   <style>
       /* 注释 */
       选择器 {
           属性名: 属性值；
       }
   </style>
   ```

   

2. 外联式：单独.css文件，项目中常用

   通过link标签在html中引入

   ```html
    <!-- 关系：样式表 -->
    <link rel="stylesheet" href="">
   ```

   

3. 行内式：配合js使用

   ```html
   <div style="color: green; xxx: xxx">
       xxx
   </div>
   ```

   

## CSS选择器

### 基础

#### 标签选择器

+ 同时设置所有同种标签
+ 不受嵌套关系影响

#### 类选择器

类名：由数字，字母，下划线，中划线组成，不能以数字或中划线开头

结构：

```html
<style>
    .类名 {
        属性名: 属性值；
    }
</style>

<p class="类名1 类名2">
    xxx
</p>
```



#### id选择器

id：一个html文件内唯一；一般用来加动画效果

  结构：

```html
<style>
    #id属性值 {
        属性名: 属性值；
    }
</style>

<p class="类名1 类名2">
    xxx
</p>
```



#### 通配符选择器

`*` 少用

```css
/*清楚默认格式*/
* {
	margin: 0;
	padding: 0;
}
```



### 进阶

#### 后代选择器：空格

```html
选择器1 选择器2 {css}
```

#### 子代选择器：“>”

```html
 选择器1>选择器2 {css}
```

#### 并集：“，”

```
选择器1，选择器2，...{css}
```

#### 交集：

```
eg：
p.class名{css}
```

#### 伪类：hover，鼠标选中元素时触发

```
选择器:hover{css}
```



## CSS特性

### 规范

1. 块级元素一般作为大容器，可以嵌套：文本、块级元素、行内元素、行内块元素等

   **但是：** p标签不要嵌套div、p、h等块级元素

2. a标签内部可以嵌套任何元素

   **但是：** a标签不能嵌套a标签

### 三大属性

#### 继承性

子元素继承父元素样式特点

1. color
2. font-style, font-weight, font-size, font-family
3. text-indent, text-align
4. line-height
5. ...

可通过调试工具判断样式是否可以继承

#### 层叠性

#### 优先级

!important>行内样式>id选择器>类选择器>标签选择器>通配符选择器>继承





## 字体与文本样式

### 字体样式

+ font-size： chrome默认16px
+ font-weight： normal==400；bold==700；100~900的整百数
+ font-style： normal，italic
+ font-family： 微软雅黑，黑体，sans-serif
+ font（复合属性）： style weight size family；前两个可省略

### 文本样式

+ 文本缩进：text-indent：数字px or 数字em（1em=当前标签font-size）
+ 文本水平对齐方式：text-align： left，center，right
+ 文本修饰：text-decoration： underline, line-through, overline, none (none可清楚a标签默认的下划线)

### line-height行高

+ 取值：
  + 数字+px
  + 倍数（当前标签font-size的倍数）
+ 应用
  + 单行文本垂直居中可设置line-height：文字父元素高度
  + 网页精准布局时，会设置line-height：1 可以取消上下间距
+ font复合属性

```css
font: style weight size/line-height family;
```

### 颜色

+ 关键词：red，green，blue，yellow等
+ rgb：0-255
+ rgba：a 0-1，表示透明度
+ 十六进制表示法：#000000，#ff0000等，简写#000，#f00



## 背景

+ background-color: (bgc)
+ background-image: (bgi)
  + url('path')
  + 背景图片默认在水平和垂直方向平铺的
  + url可以省略引号
+ background-repeat: (bgr)
  + repeat
  + no-repeat
  + repeat-x
  + repeat-y
+ background-position: (bgp)
  + 水平方向位置: left, center, right, 数字+px
  + 垂直方向位置: top, center, bottom，数字+px
+ background（bg）复合属性
  + 推荐顺序：color image repeat position
  + 可以按需求省略
  + 特殊情况：在pc端，若盒子大小和背景图片大小一样，可写：`background: url()`





## 元素的显示模式

尖括号`<>`表示元素，又名：标签，标记

+ 块级元素
  + 特点：
    + 独占一行，一行只显示一个
    + 宽度默认时父元素宽度，高度默认由内容撑开
    + 可以设置宽高
  + 代表标签：div，p，h系列；ul,li,dl,dt,dd,form,header,nav,footer...
+ 行内元素
  + 特点：
    + 一行可显示多个
    + 宽度高度默认由内容撑开
    + 不可以设置宽高
  + 代表标签：a,span,b,u,i,s,strong,ins,em,del...
+ 行内块元素
  + 特点：
    + 一行可以显示多个
    + 可以设置宽高
  + 代表标签：
    + input，textarea，button，select
    + 特殊情况：img标签由行内块元素特点，但是Chrome调试工具显示为inline

+ display：
  + block
  + inline-block
  + inline





## 盒子模型

### 模型

+ 内容 content（ width，height）

+ 内边距 padding

  + ```css
    padding: 10px /*上下左右均为10px*/
    padding: 10px 20px 30px 40px /*按照上、右、下、左顺序赋值*/
    ```

  + ```css
    padding-top
    padding-bottom
    padding-left
    padding-right
    ```

    

+ 边框 border

  + ```css
    border: 1px solid black;
    border: 1px dashed black;
    border: 1px dotted black;
    ```

  + ```css
    border-top
    border-bottom
    border-left
    border-right
    ```

    

+ 外边距 margin



+ 内容溢出的处理方式 `overflow`

  + `visible`：默认值，元素内容超出边框时将继续呈现，可能会溢出父元素。
  + `hidden`：元素内容超出边框时将被裁剪掉，不会被显示出来。
  + `scroll`：元素内容超出边框时会添加滚动条，以便用户可以滚动查看所有内容。
  + `auto`：浏览器自动根据需要添加滚动条。

  另外，`overflow` 属性也可以应用于内联元素，当其内容超出尺寸时，与块级元素不同的是，内联元素的高度是由其内容而非尺寸决定的，因此 `overflow` 属性对于内联元素通常用于控制其宽度，例如，将一个长文本链接设置为 `overflow: hidden` 可以防止其跨越多行显示。

+ 

### 小技巧

+ CSS3盒模式（自动内减）

```css
box-sizing: border-box
```

+ 清除默认格式

```css
* {
    margin: 0;
    padding: 0;
}
```

+ 版心居中

  版心表示有意义的内容所在部分

  ```css
  margin: 0 auto;
  ```



### 外边距折叠现象

+ 合并现象
  + 场景：**垂直布局**的**块级元素**，上下的margin会合并
  + 结果：取大者
+ 塌陷现象
  + 场景：**互相嵌套**的**块级元素**，子元素的margin-top会作用在父级元素上
  + 结果：父级元素向下移动
  + 解决方法：
    + 给父元素设置border-top或padding-top（分割父子元素的margin-top）
    + 给父元素设置`overflow: hidden`（推荐）
    + 子元素转换成行内块元素
    + 设置浮动
+ 行内元素的垂直内外边距设置问题
  + 行内元素的margin-top，margin-bottom，padding-top，padding-bottom设置无效
  + 应使用 `line-height` 设置



## CSS浮动

### 结构伪类选择器

+ 作用与优势：

  + 作用：根据元素在html中的结构关系查找元素
  + 优势：减少类的依赖，代码简洁

  + 场景：常用于查找某父级选择器中的子元素

+ 语法：

  ```css
  E: first-child {}
  E: last-child {}
  E: nth-child(n) {}
  E: nth-last-child(n) {}
  ```

+ 可以在括号中使用n，`n=0,1,2,...` 

  + 偶数：even，2n
  + 奇数：odd，2n-1，2n+1
  + 前五个：-n+5
  + 第五个及之后：n+5



### 伪元素

一般页面的非主体内容可以用伪元素

+ 区别：
  + 元素：html设置的标签
  + 伪元素：css模拟出的装饰性的（不重要的，小图的）标签效果，在不修改HTML标记的情况下为网页添加更多的样式和装饰性元素。
+ 种类
  + `::before` 在父元素内容的最前添加一个伪元素。常用于添加图标、引号或其他装饰性元素。
  + `::after` 在父元素的最后添加一个伪元素。通常用于添加一些额外的样式，比如“清除浮动”等。
  + `::first-letter` 用于选择元素的第一个字母并应用样式。通常用于添加大写字母、下划线等。
  + `::first-line` 用于选择元素的第一行并应用样式。通常用于添加文本样式，比如字体大小、颜色等。
  + `::selection` 用于选择用户选择的文本并应用样式。通常用于更改文本的背景颜色、字体颜色等。

+ 注意：
  + 必须设置content属性才能生效
  + 伪元素默认inline

eg：

```css
.father::before{
	content: 'xxx';
}
```



### 标准流

标准流: 又称文档流, 是浏览器在渲染显示网页内容时默认采用的一套排版规则.

常见规则:

+ 块级元素: 从上往下, 垂直布局, 独占一行
+ 行内元素或行内块元素: 从左往右, 水平布局, 空间不够自动折行



### 浮动

#### 作用

1. 最初的作用: 图文环绕效果
2. 现在的作用: 网页布局
   + 浏览器解析 `inline` 或 `inline-block` 时, 若标签换行, 则视为空格. 使用浮动解决

#### 特点

1. 浮动元素脱离标准流(简称: 脱标). 
2. 一行可以显示多个, 可以设置宽高
3. 不能通过 `text-align: center` 或 `margin: 0 auto` 居中

#### 语法

```css
float: left;
float: right;
```



#### 清除浮动

清除浮动标签对于其它标签的影响

影响: 浮动的子元素不能撑开标准流的块级父元素

解决方式: 

+ 给父元素设置 `height`

+ 额外标签法: 在父元素内容最后添加一块级元素, 并给其设置 `clear: both`

+ 单伪元素清除法: (**常用**)

  ```css
  .clearfix::after{
  	content: '';
      /*要求块元素, 伪元素默认是inline*/
      display: block;
      clear: both;
  }
  
  .clearfix::after{
  	content: '';
      display: block;
      clear: both;
      /*
      补充代码, 在网页中看不到该伪元素, 
      用于解决兼容性问题
      */
      height: 0;
      visibility: hidden;
  }
  ```

  

+ 双伪元素清除法:

  ```css
  /*.clearfix::before 解决外边距塌陷问题*/
  .clearfix::before,
  .clearfix::after {
      content: '';
      display: table;
  }
  /*真正清除浮动的标签*/
  .clearfix::after {
      clear: both;
  }
  ```



+ 父元素设置 `overflow: hidden`

## 备注

1. `$` 数字递增操作

   

# JavaScript

> reference: 
>
> + [b站搬运 Udemy 的 JavaScript 教程](https://www.bilibili.com/video/BV1vA4y197C7)
>
> + https://developer.mozilla.org/zh-CN/docs/Learn/

# xx

```javascript
alert()
console.log()
```





