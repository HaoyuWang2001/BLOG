---
title: HTML
date: 2023-04-28
tags:
---



# HTML

*hyper text markup language*

**后缀名: ** `html`, `htm`

## 骨架

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

注释：

```html
 <!--  -->
```





## 基础标签

**双标签：**

+ 标题：h1-h6

+ 段落：p
+ 链接：a：href（=“#”）

**单标签：**

+ 换行：br；水平线：hr

+ 图像：img：src，alt，title；width，height
+ 音频：audio：src，controls，autoplay（部分浏览器不支持），loop
+ 视频：video：src，controls，autoplay，muted，loop



## 属性

+ class
+ id
+ style
+ title



## 文本格式化

+ 加粗：b，strong
+ 下划线：u，ins
+ 倾斜：i，em
+ 删除线：s，del
+ 



## 列表

+ 无序

  ```html
  <ul>
      <li></li>
      <li></li>
  </ul>
  ```

  

+ 有序

  ```html
  <ol>
      <li></li>
      <li></li>
  </ol>
  ```

  

+ 自定义列表

  ```html
  <dl>
      <dt></dt>
      <dd></dd>
      <!-- dd默认缩进-->>
  </dl>
  ```

  

## 表格

**基础表格：**

```html
<table border="1">
    <tr>
        <th></th>
        <th></th>
    </tr>
    <tr>
        <td></td>
        <td></td>
    </tr>
</table>
```

**结构标签：**

```html
<table border="1">
    <caption></caption>
    <thead>
        <tr>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td></td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td></td>
        </tr>
    </tfoot>
</table>
```

**合并单元格：**

向右，向下合并；不能跨结构标签

+ rowspan
+ colspan



## 表单

### input

type属性：

+ text：placeholder
+ password：placeholder
+ radio：name，checked
+ checkbox
+ file：multiple
+ submit
+ reset
+ button：value

### button

type属性：submit，reset，button

### select

```html
<select name="" id="">
    <option value="" selected></option>
    <option value=""></option>
</select>
```

### textarea

cols，rows

### label

两种方法：

```html
<input type="radio" name="radio" id="id1"> <label for="id1">1</label>
<label><input type="radio" name="radio"> 2 </label>
```



## 语义化标签

### 无语义标签

div：独占一行

span：同行多个

### 有语义标签

用于Android

header，nav，footer，aside，section，article



## 字符实体

`&nbsp;`

