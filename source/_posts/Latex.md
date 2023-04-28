---
title: Latex
date: 2023-03-17
tags:
---

# Latex

+  设置字体大小

```latex
\documentclass[12pt]{article}

\fontsize{字体大小}{行间距}\selectfont
\fontsize{12pt}{\baselineskip}\selectfont
----------
字体大小：
\tiny
\scriptsize
\footnotesize
\small
\normalsize
\large
\Large
\LARGE
\huge
\Huge

使用方式：
\tiny xxxxxxxx
```



+ 页脚页眉设置（及在页脚页眉中插入图片）
  
  1. 无图片：
  
  ```latex
  \usepackage{fancyhdr}%导入fancyhdr包
  \pagenumbering{xxx}%设置页码格式
  \fancyhead[L]{左页眉}
  \fancyhead[R]{右页眉}
  \fancyhead[C]{中间页眉}
  \fancyfoot[L]{左页脚}
  \fancyfoot[C]{\thepage}
  \fancyfoot[R]{右页
  \renewcommand{\headrulewidth}{4pt}%分隔线宽度4磅
  \renewcommand{\footrulewidth}{4pt}脚}
  ```
  
  2. 有图片：
  
  ```latex
  方法一：
  \usepackage{fancyhdr}
  \pagestyle{fancy}
  \lhead{\includegraphics[scale=0.1]{logo.pdf}}
  
  方法二：
  \newsavebox{\mygraphic}
  \sbox{\mygraphic}{\includegraphics[totalheight=0.5in]{file.ps}}
  \pagestyle{fancy}
  \fancyhead{} % clear all header fields
  \fancyhead[L]{\usebox{\mygraphic}}
  
  ```
  
  3. 设置页眉页脚到正文的距离；
  
  ```latex
  \setlength{\headsep}{40pt}
  \setlength{\footskip}{40pt}
  ```
  
  

