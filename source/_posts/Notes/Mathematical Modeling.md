---
title: Mathematical Modeling
date: 2023-05-01
tags:

---

# 数学建模

作者：王浩羽



## 模型学习

### 五大模型

#### 预测模型 / 回归模型

* 神经网络预测模型
* 灰色预测模型：数据非常少：7-15，不超过20
* 拟合插值法（线性回归）
* 时间序列模型：自变量为时间
* 马尔可夫模型（Markov Model）
* 支持向量机模型
* Logistic模型
* 组合预测模型
* 微分方程预测

#### 评价模型

* 模糊综合评价法
* 层次分析法
* 聚类分析法
* 主成分分析评价法：（寻找关键自变量，进一步应用于评价问题、回归问题）
* 灰色综合评价法
* 人工神经网络评价法
* BP神经网络综合评价法
* 组合评价法

#### 优化模型

* 规划模型，其中包括目标规划、线性规划、非线性规划、整数规划、动态规划
* 排队论模型
* 神经网络模型
* 现代优化算法，其中包括遗传算法、模拟退火算法、蚁群算法、禁忌搜索算法
* 图论模型
* 组合优化模型

#### 分类模型

* 决策树
* 逻辑回归
* 随机森林
* 朴素贝叶斯

#### 统计分析模型

* 均值T检验
* 方差分析
* 协方差分析
* 分布检验
* 相关分析
* 卡方检验
* 秩和检验
* 回归分析
* Logistic回归
* 聚类分析
* 判别分析
* 关联分析

### 十大算法

1. 蒙特卡罗算法
2. 数据拟合、参数估计、插值等数据处理算法
3. 线性规划、整数规划、多元规划、二次规划等规划类问题
4. 图论算法
5. 动态规划、回溯搜索、分治算法、分支定界等计算机算法
6. 最优化理论的三大非经典算法：模拟退火法、神经网络、遗传算法
7. 网格算法和穷举法
8. 一些连续离散化方法
9. 数值分析算法
10. 图象处理算法

---




## 代码编写

### MATLAB

+ 数据处理
+ 信号处理
+ 函数拟合
+ 图像绘制

### Python

**NumPy, Pandas**

+ 数据处理及分析
+ 不同点:
  + Pandas 处理表格和混杂数据, 比较契合统计分析中的表结构;
  + NumPy 更适合处理统一的数值数组数据.

**Matplotlib**

+ 图像绘制

**PyTorch**

+ 机器学习/神经网络

**SciPy**
SciPy 包含用于科学计算中常见问题的工具箱:

+ 文件输入/输出 `scipy.io`
+ 特殊函数 `scipy.special`
+ 线性代数运算 `scipy.linalg`
+ 插值 `scipy.interpolate`
+ 优化(含数学规划), 拟合 `scipy.optimize`
+ 统计和随机数 `scipy.stats`
+ 数值积分 `scipy.integrate`
+ 快速傅里叶变换 `scipy.fftpack`
+ 信号处理 `scipy.signal`
+ 图像处理 `scipy.ndimage`

---

## 软件准备

### 翻译
+ 知云文献翻译
+ 有道文档翻译

### 论文
Word
LaTex
+ [Overleaf](https://www.overleaf.com/): 线上多人共享LaTex撰写平台
+ Tex Live + VsCode: 本地, 推荐(因VsCode比TeXstudio好看)
+ Tex Live + TeXstudio: 本地

### 绘图
 [drawio](https://app.diagrams.net/)：用于结构图、树状图等逻辑图示的绘制

### Python 环境
+ Anaconda + VsCode
+ Jupyter Notebook

#### 数学公式
+ MathType：输入数学公式
+ Mathpix：识别数学公式

### 其他
+ Excel：用于简单计算
+ SPSS（Statistical Product and Service Solutions）：统计分析
+ Lindo/Lingo：解决数学规划问题
+ MATLAB

---

## 学习内容

### 论文写作
视频：[论文撰写参考视频](https://www.bilibili.com/video/BV1Na411w7c2)

### LaTeX
a. 文档+视频：[LaTex基础](https://blog.csdn.net/qq1198768105/article/details/120615302)
b. 模板：（easyMCM）
c. 备注：出现电脑用户名（User）为中文而安装失败的问题，参考：[该博客](https://blog.csdn.net/wuyanxiushi/article/details/118864082)

### 建模学习
天津工业大学数学建模课程视频（使用软件：MATLAB、Lingo）：[该视频](https://www.bilibili.com/video/BV1iU4y1M7t9)

### 机器学习
参考书籍: 机器学习, 周志华 (西瓜书)
参考课程: [李宏毅机器学习课程](https://www.bilibili.com/video/BV1Wv411h7kN ) (对应github：[Lhy_Machine_Learning](https://github.com/Fafa-DL/Lhy_Machine_Learning))
sklearn 入门课程：https://www.bilibili.com/video/BV1aV411e7CJ
PyTorch 参考书籍(于GitHub上): [深度学习框架PyTorch 入门与实战](https://github.com/chenyuntc/pytorch-book)

---

## 论文大纲

### 美赛

1. Title + Summary(需准备) + Keywords
2. Introduction
3. Assumption and Justifications
4. Notations (and Glossary)
5. Model Ⅰ Ⅱ Ⅲ
6. (Data Description)
7. Sensitivity Analysis
8. Model Evaluation and Further Discussion
9. Conclusion
10. References
11. Appendices
12. (Memo or Letter or Article)

---

## 文档

MATLAB中文文档: https://ww2.mathworks.cn/help/matlab

Lingo英文文档: https://www.lindo.com/downloads/PDF/LINGO.pdf

sklearn 中文文档: https://www.sklearncn.cn/

sklearn Map: https://scikit-learn.org/stable/tutorial/machine_learning_map/


