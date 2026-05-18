---
title: Markdown 常用公式
published: 2022-09-04
description: LaTeX 数学公式在 Markdown 中的使用方法总结
tags: [Markdown, LaTeX, 数学公式]
category: 技术工具
draft: false
---

# Markdown 常用公式

> 本文章的公式应用于LaTeX

## 一.公式形式

- 行内公式：$ f(x) = \int_0^\infty e^{x-1}dx\, $

- 行间公式：

- $$
  f(x) = \int_0^\infty e^{x-1}dx\,
  $$

  > 下面是上式代码
  
  <!--more-->

```latex
$ f(x) = \int_0^\infty e^{x-1}dx\, $

$$
f(x) = \int_0^\infty e^{x-1}dx\,
$$
```

## 二.希腊字母

|  名称   | 大写 |  code   |   小写   |   code   |
| :-----: | :--: | :-----: | :------: | :------: |
|  alpha  |  A   |    A    |    α     |  \alpha  |
|  beta   |  B   |    B    |    β     |  \beta   |
|  gamma  |  Γ   | \Gamma  |    γ     |  \gamma  |
|  delta  |  Δ   | \Delta  |    δ     |  \delta  |
| epsilon |  E   |    E    |    ϵ     | \epsilon |
|  zeta   |  Z   |    Z    |    ζ     |  \zeta   |
|   eta   |  H   |    H    |    η     |   \eta   |
|  theta  |  Θ   | \Theta  |    θ     |  \theta  |
|  iota   |  I   |    I    |    ι     |  \iota   |
|  kappa  |  K   |    K    |    κ     |  \kappa  |
| lambda  |  Λ   | \Lambda |    λ     | \lambda  |
|   mu    |  M   |    M    |    μ     |   \mu    |
|   nu    |  N   |    N    |    ν     |   \nu    |
|   xi    |  Ξ   |   \Xi   |    ξ     |   \xi    |
| omicron |  O   |    O    |    ο     | \omicron |
|   pi    |  Π   |   \Pi   |    π     |   \pi    |
|   rho   |  P   |    P    |    ρ     |   \rho   |
|  sigma  |  Σ   | \Sigma  |    σ     |  \sigma  |
|   tau   |  T   |    T    |    τ     |   \tau   |
| upsilon |  Υ   |    Υ    |    υ     | \upsilon |
|   phi   |  Φ   |  \Phi   |    ϕ     |   \phi   |
|   chi   |  X   |    X    |    χ     |   \chi   |
|   psi   |  Ψ   |  \Psi   |    ψ     |   \psi   |
|  omega  |  Ω   | \Omega  |    ω     |  \omega  |

## 三.上标与下标

上标和下标分别使用`^` 与`_` ，例如`$x_i^2$`表示的是：$ x_i^2$。

上标和下标是一个式子需要用`{}`扩起来，如`$\int_{2x} ^{\sqrt 2e}}xdx$`：$\int_{2x} ^{\sqrt {2e}}xdx$

单字符`$\hat x$`： $\hat x$

多字符`$\widehat{xy}$`：$\widehat{xy}$

上划线`$\overline{xy}$`：$\overline{xy}$

矢量`$\vec x$`：$\vec x$

向量`$\overrightarrow{xy}$`：$\overrightarrow{xy}$

点`$\dot x$`：$\dot x$

## 四.括号

### 1.小括号与方括号

无限制，直接使用即可。

### 2.大括号

由于大括号`{}` 被用于分组，因此需要使用`\{`和`\}`表示大括号，也可以使用`\lbrace` 和`\rbrace`来表示。如`$\{a,b,c\}$` 或`$\lbrace a,b,c\rbrace $` 表示：$\{a,b,c\}$

### 3.尖括号

使用`\langle` 和`\rangle` 表示左尖括号和右尖括号。如`$\langle x \rangle$` 表示：$\langle x \rangle$

### 4.上取整

使用`\lceil` 和 `\rceil` 表示。 如`$\lceil x \rceil$`：$\lceil x \rceil$

### 5.下取整

使用`\lfloor` 和 `\rfloor` 表示。如`$\lfloor x \rfloor$`：$\lfloor x \rfloor$

## 五.求和与积分

### 1.求和

`\sum` 用来表示求和符号，其下标表示求和下限，上标表示上限。

如`$\sum_{i=1}^n$`：$\sum_{i=1}^n$

### 2.积分

`\int`用来表示积分符号，同求和。

如`$\int_0^{2x}$`：$\int_0^{2x}$

特别的：

`$\iint_0^x$`：$\iint_0^x$

`$\iiint_0^x$`：$\iiint_0^x$

### 3.连乘

`$\prod_{i=1}^{n} i$`：$\prod_{i=1}^{n} i$

### 4.一些不常用的

`$\bigcup$`：$\bigcup$

`$\bigcap$`：$\bigcap$

`$arg\,\max_{c_k}$`：$arg\,\max_{c_k}$

`$arg\,\min_{c_k}$`：$arg\,\min_{c_k}$

`$\mathop {argmin}_{c_k}$`：$\mathop {argmin}_{c_k}$

`$\mathop {argmax}_{c_k}$`：$\mathop {argmax}_{c_k}$

`$\max_{c_k}$`：$\max_{c_k}$

`$\min_{c_k}$`：$\min_{c_k}$

## 六.分式与根式

### 1.分式

- 方法一：`\frac {a+b+1}{c+d+2}`：$\frac {a+b+1}{c+d+2}$
- 方法二：`${a+b+1 \over c+d+2}$`：${a+b+1 \over c+d+2}$

### 2.连分式

`\frac`和`$\cfrac$`都可，但后者表现更好。

如：`$$x = \frac {a_1 + 1}{\frac {a_2 + 2}{a_3 + \frac{a_4 + 4}{a_5 + 5} + 3} + 6} + 7$$`
$$
x = \frac {a_1 + 1}{\frac {a_2 + 2}{a_3 + \frac{a_4 + 4}{a_5 + 5} + 3} + 6} + 7
$$
和：`$$x = \cfrac {a_1 + 1}{\cfrac {a_2 + 2}{a_3 + \cfrac{a_4 + 4}{a_5 + 5} + 3} + 6} + 7$$`
$$
x = \cfrac {a_1 + 1}{\cfrac {a_2 + 2}{a_3 + \cfrac{a_4 + 4}{a_5 + 5} + 3} + 6} + 7
$$

### 3.根式

根式使用`\sqrt` 来表示。

开平方`$\sqrt{\frac {x+1}{y+2}}$`：$\sqrt{\frac {x+1}{y+2}}$

开3次方`$\sqrt[3]{\frac {x+1}{y+2}}$` ：$\sqrt[3]{\frac {x+1}{y+2}}$

## 七.其他

### 1.方程组

```latex
$$
\left \{ 
\begin{array}{c}
a_1x+b_1y+c_1z=d_1 \\ 
a_2x+b_2y+c_2z=d_2 \\ 
a_3x+b_3y+c_3z=d_3
\end{array}
\right.
$$
```

$$
\left \{ 
\begin{array}{c}
a_1x+b_1y+c_1z=d_1 \\ 
a_2x+b_2y+c_2z=d_2 \\ 
a_3x+b_3y+c_3z=d_3
\end{array}
\right.
$$

### 2.表格

```latex
$$
\begin{array}{c|ccr} //ccr居中对齐 lcr左对齐 rcr右对齐
码农大赛 & \text{1号} & \text{2号} & \text{3号} 
\hline
第1次 & 0.24 & 1 & 125 \\
第2次 & -1 & 189 & -8 \\
第3次 & -20 & 2000 & 11 \\
\end{array}
$$
```

$$
\begin{array}{c|ccr} 
码农大赛 & \text{1号} & \text{2号} & \text{3号} \\
\hline
第1次 & 0.24 & 1 & 125 \\
第2次 & -1 & 189 & -8 \\
第3次 & -20 & 2000 & 11 \\
\end{array}
$$

### 3.矩阵

```latex
$$
\begin{matrix}
1 & x & x^2 \\
1 & y & y^2 \\
1 & z & z^2 \\
\end{matrix}
$$
```

$$
\begin{matrix}
1 & x & x^2 \\
1 & y & y^2 \\
1 & z & z^2 \\
\end{matrix}
$$
