---
title: Holomorphic functions of several variables - 2
date: 2025-06-16 14:15:00
tags:
	- complex geometry
	- math
mathjax: true
---

For a holomorphic function $f(z)$ of one variable, we can consider the decomposition $$f(z) = (z - z_0)^m h(z), \quad h(z_0) \neq 0,$$ where $z_0$ is an $m$-order zero of $f$ and $h$ is holomorphic. We want to obtain a similar description of holomorphic functions of several variables near a zero. 

<!-- Weierstrass polynomial -->

To find such decomposition, we need to figure out a special kind of holomorphic functions which share the same zeros with the original holomorphic functions. Consider the **Weierstrass polynomials** (in $z^n$, of degree $k$), which have the form $$g(z) = g(\tilde{z}, z^n) = (z^n)^k + a_1(\tilde{z})(z^n)^{k-1} + \cdots + a_k(\tilde{z}),$$ where $a_1, \cdots, a_k$ are holomorphic functions in $\tilde{z} = (z^1, \cdots, z^{n-1})$ on a neighborhood of $0 \in \mathbb{C}^{n-1}$ such that $$a_1(0) = \cdots = a_k(0) = 0.$$ 

We see that for any fixed $\tilde{z} \in \mathbb{C}^{n-1}$ such that the above Weierstrass polynomial $g(\tilde{z}, z^n)$ is defined, $g(\tilde{z}, z^n)$ has exactly $k$ zeros (with multiplicities) as a holomorphic function in $z^n$. 

<!-- Weierstrass preparation theorem -->

**Lemma.** Suppose $f(z) = f(\tilde{z}, z^n)$ is a holomorphic function on a neighborhood of $0 \in \mathbb{C}^n$, and $z^n = 0$ is a $k$-order zero of the function $f(0, z^n)$ in $z^n$. Then there exists a polydisc $D(0, \tilde{\delta}) \subset \mathbb{C}^{n-1}$ and $\delta_n > 0$ such that for each $\tilde{z} \in D(0, \tilde{\delta})$, $f(z)$ has exactly $k$ zeros (with multiplicities) on $D(0, \delta_n) \subset \mathbb{C}$ as a holomorphic function in $z^n$. 

> *Proof:* There exists $\delta_n > 0$ such that $z^n = 0$ is the only zero of $f(0, -)$ on $D(0, \delta_n)$. Then there exists $D(0, \tilde{\delta}) \subset \mathbb{C}^{n-1}$ such that $f(\tilde{z}, z^n) \neq 0$ for any $\tilde{z} \in D(0, \tilde{\delta}$ and $|z^n| = \deta_n$. 
> 
> Let $N(\tilde{z})$ be the number of zeros (with multipicities) of $f(\tilde{z}, -)$ on $D(0, \delta_n) \subset \mathbb{C}$. The argument principle implies that $$N(\tilde{z}) = \frac{1}{2 \pi i}\oint_{|\zeta| = \delta_n} \frac{1}{f(\tilde{z}, \zeta)}\frac{\partial f}{\partil z^n}(\tilde{z}, \zeta)\mathrm{d}\zeta,$$ and hence $N(\tilde{z})$ is holomorphic in $z^n$ on $D(0, \tilde{\delta})$ by a lemma from the previous post. Thus $N(\tilde{z})$ must be constant, i.e., $$N(\tilde{z}) = N(0) = k, \quad \tilde{z} \in D(0, \tilde{\delta}).$$

**Theorem (Weierstrass preparation theorem).** Suppose $f(z) = f(\tilde{z}, z^n)$ is a holomorphic function on a neighborhood of $0 \in \mathbb{C}^n$, such that $f(0) = 0$ and $f(0, z^n)$ is a nonzero holomorphic function in $z^n$. Then there exists a polydisc $D(0, r) \subset \mathbb{C}^n$ around $0$, a unique Weierstrass polynomial $g(z) = g(\tilde{z}, z^n)$ in $z^n$ and a holomorphic function $h(z)$ on $D(0, r)$ such that $$f(z) = g(z)h(z), \quad h(0) \neq 0.$$

> *Proof:* Take the same polydisc $D(0, \tilde{\delta})$ and the same $\delta_n > 0$ as the proof of the lemma. Suppose $z^n = 0$ is a $k$-order zero of $f(0, z^n)$. By the lemma, we can let $w_1(\tilde{z}), \cdots, w_k(\tilde{z})$ be the zeros of $f(\tilde{z}, -)$ on $D(0, \delta_n)$ for each $\tilde{z} \in D(0, \tilde{\delta}) \subset \mathbb{C}^{n-1}$. 
> 
> By residue theorem we have $$\sum_{j=1}^k w_j^d(\tilde{z}) = \frac{1}{2 \pi i} \oint_{|\zeta| = \delta_n} \frac{\zeta^d}{f(\tilde{z}, \zeta)}\frac{\partial f}{\partil z^n}(\tilde{z}, \zeta)\mathrm{d}\zeta, \quad d = 0, \cdots, k,$$ and hence the left hand side is holomorphic in $\tilde{z}$. It follows that the function defined by $$g(z) = g(\tilde{z}, z^n) = (z^n - w_1(\tilde{z})) \cdots (z^n - w_k(\tilde{z}))$$ is a Weierstrass polynomial in a neighborhood of $0$, such that $g$ and $f$ have exactly the same zeros on this neighborhood. 
> 
> For each $\tilde{z} \in D(0, \tilde{\delta})$, there is a unique $h(\tilde{z}, z^n)$ such that $h$ is holomorphic in $z^n$ on $D(0, \delta_n)$ and that $f(\tilde{z}, z^n) = g(\tilde{z}, z^n)h(\tilde{z}, z^n)$. We can see from the Cauchy integral formula in $z^n$ and a lemma from the previous post that $h$ is also holomorphic in $\tilde{z}$, and hence holomorphic in $z = (\tilde{z}, z^n)$.
> 
> The uniqueness of $g$ is clear from the fact that $f$ and $g$ must have the same zeros. The uniqueness of $h$ then follows from the identity theorem.

<!-- Riemann extension theorem -->

For each holomorphic function $f$ on an open subset $U \subset \mathbb{C}^n$, we denote the zero set of $f$ by $Z(f)$. The Weierstrass preparation actually gives a description of $Z(f)$ in a neighborhood of a zero. The construction of the holomorphic $h$ in the theorem can be modified to a proof of the following Riemann extension theorem. 

**Theorem (Riemann extension theorem).** Suppose $f$ is a nonzero holomorphic function on a connected open set $U \subset \mathbb{C}^n$ and $g : U \setminus Z(f) \to \mathbb{C}$ is holomorphic and bounded. Then $g$ can be extended to a holomorphic function $\tilde{g} : U \to \mathbb{C}$. 

<!-- Weierstrass division theorem -->

Another Weierstrass theorem is concerned with the Euclid algorithm of holomorphic functions.

**Theorem (Weierstrass division theorem).** Suppose $f$ is a holomorphic function on a neighborhood of $0 \in \mathbb{C}^n$ and $g$ is a Weierstrass polynomial in $z^n$ of degree $k$ defined around $0$. Then there exists a sufficiently small neighborhood $U \subset \mathbb{C}^n$ of $0$, a uniquely determined holomorphic function $q$ on $U$ and a uniquely determined Weierstrass polynomial $r$ in $z^n$ of degree less than $k$, such that $$f(z) = g(z)q(z) + r(z), \quad z \in U.$$

> *Proof:* The unique statement can be proved in a similar way to the unique statement of an ordinary Euclid algorithm. Now we show the existence. Taking a sufficient small neighborhood $D(0, \tilde{\delta}) \times D(0, \delta_n)$ we may define $$q(z) = h(\tilde{z}, z^n) = \frac{1}{2 \pi i} \oint_{|\zeta| = \delta_n} \frac{f(\tilde{z}, \zeta)}{g(\tilde{z}, \zeta)(\zeta - z^n)} \mathrm{d}\zeta$$ such that $q$ is holomorphic for $\tilde{z} \in D(0, \tilde{\delta})$ and $|z^n| < \delta_n$. It remains to show that $r = f - g \cdot q$ is a Weierstrass polynomial with degree less than the degree of $g$. 
> 
> Suppose $$g(z) = g(\tilde{z}, z^n) = (z^n)^k + a_1(\tilde{z})(z^n)^{k-1} + \cdots + a_k(\tilde{z}).$$ Then we can write $$\frac{g(\tilde{z}, \zeta) - g(\tilde{z}, z^n)}{\zeta - z^n} = \sum_{j=1}^k b_j(\tilde{z}, \zeta)(z^n)^{k-j},$$ where $b_j(\tilde{z}, \zeta)$ are determined by $a_j(\tilde{z})$ and holomorphic in $\tilde{z}$ and $\zeta$. It follows that $$r(\tilde{z}, z^n) = \frac{1}{2 \pi i} \oint_{|\zeta| = \delta_n} \frac{f(\tilde{z}, \zeta)}{g(\tilde{z}, \zeta)}\frac{g(\tilde{z}, \zeta) - g(\tilde{z}, z^n)}{\zeta - z^n}\mathrm{d}\zeta = \sum_{j=1}^k c_j(\tilde{z})(z^n)^{k-j},$$ where $$c_j(\tilde{z}) = \frac{1}{2 \pi i}\oint_{|\zeta| = \delta_n} \frac{f(\tilde{z}, \zeta)}{g(\tilde{z}, \zeta)}b_j(\tilde{z}, \zeta)\mathrm{d}\zeta$$ are holomorphic in $\tilde{z}$. 

<!-- Holomorphic function germs -->

For the preceding theorems, we often need to take smaller and smaller neighborhoods. In convenience, we introduce the concept of germs of functions.

Suppose $z \in \mathbb{C}^n$ is a fixed point. Let $H_z$ be the set of holomorphic functions defined in some neighborhood of $z$. Define an equivalence relation $\sim$ on $H_z$ by that $f \sim g$  if and only if $f$ and $g$ agree with each other on a sufficiently small neighborhood of $z$. An equivalence class of $H_z$ with respect to this equivalence relation is called a **germ of holomorphic functions near $z$**, and the collection of all such germs is denoted by $\mathcal{O}_{\mathbb{C}^n,z}$, i.e., $\mathcal{O}_{\mathbb{C}^n,z} = H_z / \sim$. 

We can see that $\mathcal{O}_{\mathbb{C}^n,z}$ has a natural ring structure with identity given by the constant function $1$. It can be verified that the units in $\mathcal{O}_{\mathbb{C}^n,z}$ are the germs given by the functions $f$ such that $f(z) \neq 0$. This imples that $\mathcal{O}_{\mathbb{C}^n,z}$ is a *local ring*, whose unique maximal ideal $\mathfrak{m}$ consisting of the germs given by the functions vanishing at $z$. We may use the same notation for a function and the germ it determines for short.

Now we can formulate Weierstrass theorems using the language of germs.

**Theorem (Weierstrass preparation theorem).** If $f \in \mathcal{O}_{\mathbb{C}^n,0}$ satisfies that $f(0) = 0$ and that $f(0, z^n)$ is nontrivial, then $f$ can be uniquely decomposed as $f = g \cdot h$, where $g \in \mathcal{O}_{\mathbb{C}^{n-1},0}[z^n]$ is a Weierstrass polynomial and $h$ is a unit in $\mathcal{O}_{\mathbb{C}^n,0}$. 

**Theorem (Weierstrass division theorem).** Let $f \in \mathcal{O}_{\mathbb{C}^n,0}$ and let $g \in \mathcal{O}_{\mathcal{C}^{n-1},0}[z^n]$ be a Weierstrass polynomial of degree $k$. Then there exist uniquely determined $q \in \mathcal{O}_{\mathbb{C}^n,0}$ and a Weierstrass polynomial $r \in \mathcal{O}_{\mathcal{C}^{n-1},0}[z^n]$ such that $f = g \cdot q + r$. 