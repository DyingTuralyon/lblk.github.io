---
title: $u_{tt}=P[u]$的解
date: 2021-04-16 16:29:36
tags:
mathjax: True
---

我们设想如下一个问题：

$\frac{\partialˆ2u}{\partial tˆ2} = P[u]$

$u(0)=a$

$\frac{du}{dt}(0) = b$

其中$P[u]是u的多项式$

首先将其拆分成如下问题

$\frac{\partialˆ2u}{\partial tˆ2} = c_0$

$\frac{\partialˆ2u}{\partial tˆ2} = C_iuˆi$

有如下通解

$u_0 = \frac{C_0}{2}tˆ2$

$u_1 = eˆ{\pm \sqrt{C_1}t}$

$u_2 = \frac{6}{C_2}tˆ{-2}$

$u_3 = \sqrt{\frac{2}{C_3}}tˆ{-1}$
。。。

当P[u]的阶为3时，不难得到如下的待定系数问题：
$\sum u_i(0)+ a'= a $
$\sum u_i'(0)+b'= b$
从以上问题得到a'、b'，就得到u的完整形式。
u = u_0+u_1+u_2+u_3+b't+a'
问题就在于实际上u_1中的正负号尚不确定，那么就无法求解待定系数问题







在一些情况下，我们可能需要求解其他的边界条件，比如：

$u(a) = C_a$

$u(b) = C_b$

甚至是

$u(a) = C_a$

$u'(b) =C_b$





