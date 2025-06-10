---
title: Review of holomorphic functions of one variable - 1
date: 2025-05-27 09:00:00
tags: 
    - complex geometry
    - math
mathjax: true
---

We will focus on complex geometry for quite a long time from now on. Before we step into the world of complex manifolds and related structure, a review of holomorphic functions of one variable is of great help. The first part will focus on some conclusions which are useful in the theory of holomorphic functions of several variables, and the second part will devote to the Riemann mapping theorem.

Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is a function. Then $f$ is called **holomorphic** if for each $z \in D$, the limit $$\lim_{h \to 0} \frac{f(z + h) - f(z)}{h} = f'(z)$$ exists. Viewing $D$ as a subset of $\mathbb{R}^2$, we have the partial derivatives of $f$ with respect to $x$ and $y$. It can be seen that $f$ is holomorphic on $D$ if and only if the Cauchy-Riemann equation $$\frac{\partial f}{\partial x} + i \frac{\partial f}{\partial y} = 0$$ holds on $D$, with the derivative $$f'(z) = \frac{1}{2}\left(\frac{\partial f}{\partial x} - i \frac{\partial f}{\partial y}\right).$$ Let $$\frac{\partial}{\partial z} = \frac{1}{2}\left(\frac{\partial}{\partial x} - i \frac{\partial}{\partial y}\right), \quad \frac{\partial}{\partial \bar{z}} = \frac{1}{2}\left(\frac{\partial}{\partial x} + i \frac{\partial}{\partial y}\right),$$ then the above conditions become $$\frac{\partial f}{\partial \bar{z}} = 0, \quad \frac{\partial f}{\partial z} = f'(z).$$

An important part of the complex analysis is concerned with the integral of a function along a contour (piecewise differentiable path). 

**Theorem (Cauchy-Goursat).** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is a holomorphic function. Then for each contour $C$ that is contractible in $D$, $$\oint_{C} f(z) \mathrm{d}z = 0.$$

Using Cauchy-Goursat theorem, we can consider contours of simpler shapes without changing the value of the integral. An important fact about the holomorphic functions is that they are actually smooth and analytic, shown by the following theorems.

**Theorem (Cauchy integral formula).** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is holomorphic. Then $f^{(n)}(z)$ exists and is holomorphic on $D$ for each $n \geq 0$, with $$f^{(n)}(z) = \frac{n!}{2 \pi i} \oint_{C} \frac{f(\zeta)}{(\zeta - z)^{n+1}} \mathrm{d}\zeta,$$ where $C$ is a simple contour that can be contracted to $z$ in $D$. 

**Theorem (Taylor series).** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is holomorphic. Then for each $z_0 \in D$, the Taylor expasion $$f(z) = \sum_{n=0}^{\infty} \frac{f^{(n)}(z_0)}{n!} (z - z_0)^n$$ holds in a neighborhood $D(z_0, r) \subset D$. 

**Corollary.** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is holomorphic. If $z_0 \in D$ is a zero of $f$ with order $m$, i.e., $$ f(z_0) = \cdots = f^{(m-1)}(z_0) = 0, f^{(m)}(z_0) \neq 0,$$ then there is a holomorphic function $g : D \to \mathbb{C}$ such that $g(z_0) \neq 0$ and $$f(z) = (z - z_0)^m g(z).$$

By this corollary, we may consider a contour $C$ contracted to $z_0$ such that there are no other zeros of $f$ inside $C$, since $g(z)$ is nozero in a neighborhood of $z_0$. Noting that $$f'(z) = m (z - z_0)^{m-1} g(z) + (z - z^0)^m g'(z),$$ we have $$\frac{f'(z)}{f(z)} = \frac{m}{z - z_0} + \frac{g'(z)}{g(z)},$$ implying that $$\oint_{C} \frac{f'(z)}{f(z)} \mathrm{d}z = \oint_{C} \frac{m}{z - z_0} \mathrm{d}z + \oint_{C} \frac{g'(z)}{g(z)} \mathrm{d}z = m + 0 = m,$$ where the last equality holds from the Cauchy integral formula and the Cauchy-Goursat theorem as $g'(z)/g(z)$ is holomorphic inside $C$. This extends to the *argument principle*. 

**Theorem (Argument principle for zeros).** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is holomorphic. If $z_1, \cdots, z_k$ are the zeros of $f$ inside a simple contour $C$, with orders $m_1, \cdots, m_k$, then $$\oint_{C} \frac{f'(z)}{f(z)} \mathrm{d}z = m_1 + \cdots + m_k.$$

**Theorem (Extension theorem).** Suppose $D$ is a connected open set in $\mathbb{C}$, $z_0 \in D$ and $f : D \setminus \{z_0\} \to \mathbb{C}$ is bounded and holomorphic. Then $f$ can be extended to a holomorphic function $\tilde{f} : D \to \mathbb{C}$. 

> *Proof:* Define $\tilde{f}$ by $\tilde{f}(z)  = f(z)$ for $z \neq z_0$ and $$\tilde{f}(z_0) = \frac{1}{2 \pi i}\oint_{C} \frac{f(\zeta)}{\zeta - z_0}\mathrm{d}z,$$ where $C$ is a sufficiently small contour aorund $z_0$ contained in $D$. The bounded of $f$ can imply the holomorphic property of $\tilde{f}$ at $z_0$. 

Another important corollary of the Cauchy integral formula is the *maximal module principle*.

**Theorem (Maximal module principle).** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is holomorphic. If $|f(z)|$ attains a maximal value $z_0 \in D$, then $f$ is constant on $D$. 

> *Proof:* Consider the inequality $$|f(z_0)| = \left|\frac{1}{2 \pi i}\oint_{|z - z_0| = r} \frac{f(z)}{z - z_0}\mathrm{d}z\right| = \frac{1}{2\pi} \left|\int_{0}^{2\pi} f(z_0 + re^{it})\mathrm{d}t\right| \leq \frac{1}{2\pi} \int_0^{2\pi} |f(z_0 + re^{it})| \mathrm{d}t \leq |f(z_0)|,$$ which holds for sufficiently small $r$ and implies that $|f(z)|$ is constant aroud $z_0$. The Cauchy-Riemann equations then implies that $f$ is constant near $z_0$, and an application of the Taylor series and the path-connectedness of $D$ shows that $f$ is constant on the whole $D$. 

Next we come across the theorem which decribes the topological property of a holomorphic function.

**Theorem (Open mapping theorem).** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is a non-constant holomorphic function. Then $f$ is an open mapping.

> *Proof:* It suffices to show that $f(D) \subset \mathbb{C}$ is an open set. Take any $z_0 \in D$ and let $w_0 = f(z_0)$. There is $\delta > 0$ such that $z_0$ is the unique zero of $f(z) - w_0$ in $\overline{D(z_0, \delta)}$. Let $C : |z - z_0| = \delta$ and take $0 < \varepsilon < \min_{C} |f(z) - w_0|$. We claim that $D(w_0, \varepsilon) \subset f(D)$. Consider any $w \in D(w_0, \varepsilon)$ and let $\Gamma = f(C)$. We have $$\oint_{C} \frac{f'(z)}{f(z) - w}\mathrm{d}z = \oint_{\Gamma} \frac{\mathrm{d}\zeta}{\zeta - w} = 2 \pi i n(\Gamma, w),$$ and $n(\Gamma, w) = n(\Gamma, w_0)$. Thus $$\oint_{C} \frac{f'(z)}{f(z) - w}\mathrm{d}z = \oint_{C} \frac{f'(z)}{f(z) - w_0} \mathrm{d} z = 1,$$ where the last equality holds for the argument principle. We then see that $f(z) - w$ has a zero in $D(z_0, \delta)$. 