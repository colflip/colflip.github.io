---
title: Markdown常用数学公式及符号
mathjax: true
tags:
  - 知识
  - Markdown
categories: 编程开发
date: 2019-02-23 11:42:31
---
<!-- more -->
## 基本符号

### 括号

() [] 直接写就行，而 {} 则需要转义“\ { ” “\ }”。 （\和{}之间无空格)

### 上下标

a_下标，b^上标：$$a_b$$， $$a^c$$。

### 分数

 \frac {分子} {分母} ：$$ \frac {分子} {分母} $$。

### 求和符号及其上下限位置

#### 默认情况下：

默认行间公式\sum_{k=1}^n{x_k}上下限标注在上下：
$$\sum_{k=1}^n{x_k}$$

#### 可强制修改：

强制行间公式\sum\nolimits_{k=1}^n{x_k}上下限标注在右侧：

$$\sum\nolimits_{k=1}^n{x_k}$$

### 数学符号

± ：\pm
× ：\times
÷：\div
∣：\mid

⋅：\cdot
∘：\circ
∗: \ast
⨀：\bigodot
⨂：\bigotimes
⨁：\bigoplus
≤：\leq
≥：\geq
≠：\neq
≈：\approx
≡：\equiv
∑：\sum
∏：\prod
∐：\coprod

### 集合运算符：

∅：\emptyset
∈：\in
∉：\notin
⊂：\subset
⊃ ：\supset
⊆ ：\subseteq
⊇ ：\supseteq
⋂ ：\bigcap
⋃ ：\bigcup
⋁ ：\bigvee
⋀ ：\bigwedge
⨄ ：\biguplus
⨆：\bigsqcup

### 对数运算符：

log ：\log
lg ：\lg
ln ：\ln

### 三角运算符：

⊥：\bot
∠：\angle
30∘：30^\circ
sin ：\sin
cos ：\cos
tan ：\tan
cot ：\cot
sec ：\sec
csc ：\csc

### 微积分运算符：

y′x：\prime
∫：\int
∬ ：\iint
∭ ：\iiint
∬∬：\iiiint
∮ ：\oint
lim ：\lim
∞ ：\infty
∇：\nabla

### 逻辑运算符：

∵：\because
∴ ：\therefore
∀ ：\forall
∃ ：\exists
≠ ：\not=
≯：\not>
⊄：\not\subset

### 戴帽符号：

y^ ：\hat{y}
\check{y} ：\check{y}
y˘ ：\breve{y}

### 连线符号：

a+b+c+d¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯：\overline{a+b+c+d}
a+b+c+d−−−−−−−−−− ：\underline{a+b+c+d}
a+b+c1.0+d2.0：\overbrace{a+\underbrace{b+c}_{1.0}+d}^{2.0}

### 箭头符号：

↑：\uparrow
↓：\downarrow
⇑ ：\Uparrow
⇓：\Downarrow
→：\rightarrow
← ：\leftarrow
⇒ ：\Rightarrow
⇐ ：\Leftarrow
⟶ ：\longrightarrow
⟵ ：\longleftarrow
⟹：\Longrightarrow
⟸ ：\Longleftarrow

### 表达(向量,平均值,(线性回归，直线方程) y尖,无穷小,一阶导,二阶导)

$$ \vec{a} $$  向量
$\overline{a}$ 平均值
$\widehat{a}$ (线性回归，直线方程) y尖
$\widetilde{a}$ 颚化符号  等价无穷小
$\dot{a}$   一阶导数
$\ddot{a}$  二阶导数
a

a¯ \overline{a}
a

aˆ \widehat{a}
a

a˜ \widetilde{a}
a

a˙ \dot{a}
a
˙

a¨ \ddot{a}
a
¨
---------------------

## 参考链接：

https://blog.csdn.net/xingxinmanong/article/details/78528791
https://www.cnblogs.com/q735613050/p/7253073.html
https://blog.csdn.net/thither_shore/article/details/52260742
https://blog.csdn.net/qq_38228254/article/details/78515800
https://blog.csdn.net/u013163834/article/details/87904444
