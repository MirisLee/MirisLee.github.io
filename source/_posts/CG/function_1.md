---
title: Holomorphic functions of several variables - 1
date: 2025-06-14 14:06:00
tags:
	- complex geometry
	- math
mathjax: true
---

The theory of holomorphic functions of several variables is the foundation of complex geometry, which uses $\mathbb{C}^n$ as its local model. We try to generalize some results from the one variable case, and explore some different phenomena in the several variables case. 

Suppose $z_0 = (z_0^1, \cdots, z_0^n)$ is a point in $\mathbb{C}^n$ and $r = (r_1, \cdots, r_n)$ satisfies $r_k > 0$ for each $k$. Then we define the **polydisc** $D(z_0, r)$ to be the set consisting of the points $(z^1, \cdots,  z^n) \in \mathbb{C}^n$ such that $$|z^k - z_0^k| < r_k, \quad k = 1, \cdots, n.$$ 

For a continuous function $f : D \to \mathbb{C}$ defined on a connected open subset $D \subset \mathbb{C}^n$, we say $f$ is **holomorphic** on $D$ if $$\frac{\partial f}{\partial \bar{z}^k} := \frac{1}{2}\left(\frac{\partial f}{\partial x^k} + i\frac{\partial f}{\partial y^k}\right) = 0, \quad k = 1, \cdots, n,$$ holds on $D$. Meanwhile, we can define $$\frac{\partial f}{\partial z^k} = \frac{1}{2}\left(\frac{\partial f}{\partial x^k} - i\frac{\partial f}{\partial y^k}\right)$$ for each $k$, called the *partial derivative* of $f$ with respect to $z^k$. 

Applying the result of the one variable case, we obtain the following formula.

**Theorem (Cauchy integral formula).** Suppoose $f : \overline{D(z_0, r)} \to \mathbb{C}$ is a continuous function such that $f$ is holomorphic with respect to each single component $z^i$ at each point in $D(z_0, r)$. Then for each $z \in D(z_0, r)$ the following holds $$f(z) = \frac{1}{(2 \pi i)^n} \int_{|\zeta^i - z_0^i| = r_i} \frac{f(\zeta^1, \cdots, \zeta^n)}{(\zeta^1 - z^1)\cdots(\zeta^n - z^n)} \mathrm{d}\zeta^1 \cdots \mathrm{d}\zeta^n.$$

The above formula can be used to obtain the the power series expansion of a holomorphic function. Suppose $D \subset \mathbb{C}^n$ is a connected open subset and $f : D \to \mathbb{C}$ is holomorphic. Then for each $z_0 \in D$, there is a polydisc $D(z_0, r) \subset D$ such that $$f(z) = \sum_{i_1, \cdots, i_n \geq 0} a_{i_1 \cdots i_n} (z^1 - z_0^1)^{i_1} \cdots (z^n - z_0^n)^{i_n}, \quad z \in D(z_0, r),$$ where $$a_{i_1 \cdots i_n} = \frac{1}{i_1! \cdots i_n!}\frac{\partial^{i_1 + \cdots + i_n}f}{\partial z_1^{i_1} \cdots \partial z_n^{i_n}}(z_0).$$

The preceding results enable us to generalize the identity theorem, the maximal module principle and the Schwarz lemma to the several variables case. 

**Theorem (Identity theorem).** Suppose $D$ is a connected open subset in $\mathbb{C}^n$ and $f : D \to \mathbb{C}$ is holomorphic. If $f$ vanishes on a neighborhood of some $z_0 \in D$, then $f$ equals zero on the entire $D$.

> *Proof:* Let $U$ be the subset of $D$ consisting of the points on a neighborhood of which $f$ vanishes. Then $U$ is nonempty and open. By the local power series expansion of holomorphic functions, we see that $z \in U$ if and only if all derivatives of $f$ vanish at $z$, implying that $U$ is also closed in $D$. It follows that $U$ is exactly the entire $D$.

**Theorem (Maximal module principle).** Suppose $D$ is a connected open subset in $\mathbb{C}^n$ and $f : D \to \mathbb{C}$ is holomorphic. If $|f|$ attains a maximal value at $z_0 \in D$, then $f$ is constant on $D$.

**Theorem (Schwarz lemma).** Suppose $r_0 > 0$ and let $r = (r_0, \cdots, r_0)$. Suppose $f : D(0, r) \to \mathbb{C}$ is holomorphic with $f(0) = 0$, and $|f(z)| \leq M$ for each $z \in D(0, r)$. Then for each $z \in D(0, r)$, we have $$|f(z)| \leq \frac{M}{r_0}|z|,$$ where $$|z| = \sqrt{(z^1)^2 + \cdots, (z^n)^2}, \quad z = (z^1, \cdots, z^n).$$

> *Proof:* For a fixed $z = (z^1, \cdots, z^n)$, let $$d = \max_{1 \leq k \leq n} |z^k| \leq |z|.$$ Applying the one-variable Schwarz lemma to the function $g : D(0, 1) \to \mathbb{C}$ given by $$g(t) = \frac{1}{M}f\left(\frac{t \cdot r_0}{d}z\right),$$ we obtain that $$|f(z)| = M\left|g\left(\frac{d}{r_0}\right)\right| \leq \frac{Md}{r_0} \leq \frac{M}{r_0}|z|.$$

An interesting phenomenon which is not expected for the one variable case is the following theorem.

**Theorem (Hartogs' theorem).** Suppose $n \geq 2$ and $r = (r_1, \cdots, r_n)$ and $r' = (r'_1, \cdots, r'_n)$ satisfy that $r'_k < r_k$ for each $k$. Then any holomorphic function $f : D(0, r) \setminus \overline{D(0, r')} \to \mathbb{C}$ can be uniquely extended to a holomorphic map $\tilde{f} : D(0, r) \to \mathbb{C}$. 

We refer to the proof of this theorem in *Huybrechts'* book. 

**Lemma.** Suppose $U$ is an open subset of $\mathbb{C}^n$, $V$ is a neighborhood of $\partial D(0, \delta) \subset \mathbb{C}$ for some $\delta > 0$, and $f : V \times U \to \mathbb{C}$ is a holomorphic function. Then the function $g : U \to \mathbb{C}$ given by $$g(z) = \oint_{\partial D(0, \delta)} f(\zeta, z) \mathrm{d}\zeta$$ is holomorphic.

> *Proof:* Since $\partial D(0, \delta)$ is compact, we can cover it with finitely many neighborhoods $D(\zeta_k, \delta_k)$ with $|\zeta_k| = \delta$ such that on each neighborhood the power series expansion of $f$ converges uniformly, and hence commutes with the integral. This yields a power series expansion of $g$ locally.

Now we turn to the proof of Hartogs' theorem.

> *Proof of Hartogs' theorem:* For any $z^2, \cdots, z^n \in \mathbb{C}$ such that $|z^k| < r_k$ for each $k$, $z^1 \mapsto f(z^1, \cdots, z^n)$ gives a holomorphic function on the annulus $r'_1 < |z^1| < r_1$.
> 
> Consider the Laurent expansion $$f(z^1, \cdots, z^n) = \sum_{m=-\infty}^{+\infty} a_m(z^2, \cdots, z^n)(z^1)^m, \quad r'_1 < |z^1| < r_1.$$  
> 
> Then since $$a_m(z^2, \cdots, z^n) = \frac{1}{2 \pi i}\oint_{|\zeta| = (r'_1 + r_1)/2} \frac{f(\zeta, z^2, \cdots, z^n)}{\zeta^{m+1}}\mathrm{d}\zeta, \quad m \in \mathbb{Z},$$ the lemma implies that $a_m(z^2, \cdots, z^n)$ is holomorphic for $|z^k| < r_k, 2 \leq k \leq n$. 
> 
> Meanwhile, the function $z^1 \mapsto f(z^1, \cdots, z^n)$ is holomorphic for any $|z^1| < r_1$ when $r'_2 < |z^2| < r_2$, which suggests that $a_m(z^2, \cdots, z^n) = 0$ when $m < 0$ and $r'_2 < |z^2| < r_2$. It follows from the identity theorem that $a_m(z^2, \cdots, z^n) = 0$ holds whenever $m < 0$. (This is where we need $n \geq 2$)
> 
> Define $$\tilde{f}(z^1, \cdots, z^n) = \sum_{m=0}^\infty a_m(z^2, \cdots, z^n)(z^1)^m, \quad (z^1, \cdots, z^n) \in D(0, r).$$ This power series converges uniformly on the disc $|z^1| < r_1$, as the maximal module of each $a_m$ can only be attained on the boundary, and that the power series converges on the annulus. 

