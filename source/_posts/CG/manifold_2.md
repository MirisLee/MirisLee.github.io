---
title: Complex manifolds - 2
date: 2025-06-22 10:14:00
tags:
	- complex geometry
	- math
mathjax: true
---

In this post we first study some properties of a holomorphic map from its Jacobian, and then introduce the concept of submanifolds and subvarieties. After that we disuss a bit about differential forms, which is a preparation for calculus on a complex manifold. 

## Inverse function thorem and implicit function theorem

In analogy to the real case, we have the following two standard results. 

**Theorem (Inverse function theorem).** Suppose $U \subset \mathbb{C}^n$ is an open subset and $f : U \to mathbb{C}^n$ is holomorphic. If $J(f)$ is nonsingular at $z_0 \in U$, then there exists a neighborhood $U'$ containing $z_0$ and a neighborhood $V'$ containing $f(z_0)$ such that $f : U' \to V'$ is a holomorphic homeomorphism. 

> *Proof:* Since $\det J_\mathbb{R}(f) = |\det J(f)|^2 \neq 0$ at $z_0$, the real inverse function theorem yields a smooth inverse $g$ of $f$ near $f(z_0)$. It remains to show the holomorphic property of $g$. As $z = g(f(z))$, we have $$0 = \frac{\partial (g \circ f)^\alpha}{\partial \bar{z}^j} = \sum_{k=1}^n \left(\frac{\partial g^\alpha}{\partial w^k}\frac{\partial f^k}{\partial \bar{z}^j} + \frac{\partial g^\alpha}{\partial \bar{w}^k}\frac{\partial \bar{f}^k}{\partial \bar{z}^j}\right) = \sum_{k=1}^n \frac{\partial g^\alpha}{\partial \bar{w}^k}\overline{\frac{\partial f^k}{\partial z^j}},$$ for any $1 \leq \alpha, k \leq n$. It follows from the nonsingularity of $J(f)$ that $\partial g^\alpha / \partial \bar{w}^k = 0$ for each $\alpha$ and $k$, implying that $g$ is holomorphic.  

**Theorem (Implicit function theorem).** Suppose $U \subset mathbb{C}^m$ is an open subset, $n \leq m$ and $f : U \to \mathbb{C}^n$ is holomorphic. If $z_0 \in U$ satisfies that $$\det\left(\frac{\partial f^\alpha}{\partial z^j}(z_0)\right)_{1 leq \alpha, j \leq n} \neq 0,$$ then there exist open subset $U_1 \subset \mathbb{C}^{m-n}, U_2 \subset \mathbb{C}^n$ and a holomorphic map $g : U_1 \to U_2$ such that $U_1 \times U_2 \subset U$ and $$f(z) = f(z_0) \iff (z^1, \cdots, z^n) = g(z^{n+1}, \cdots, z^m).$$

> *Proof:* Again the real implicit function theorem yields a smooth function $g : U_1 \to U_2$ satisfying the required property. To show the holomorphic property, note that $$0 = \frac{\partial f^\alpha(g(w), w)}{\partial \bar{w}^j} = \sum_{k=1}^n \left(\frac{\partial f^\alpha}{\partial z^k}\frac{\partial g^k}{\partial \bar{w}^j} + \frac{\partial f^\alpha}{\partial \bar{z}^k}\frac{\partial \bar{g}^k}{\partial \bar{w}^j}\right) + \frac{\partial f^\alpha}{\partial \bar{z}^j} = \sum_{k=1}^n \frac{\partial f^\alpha}{\partial z^k}\frac{\partial g^k}{\partial \bar{w}^j}$$ for $1 \leq \alpha \leq n, n + 1 \leq j \leq m$, which implies $\partial g^k / \partial \bar{w}^j = 0$ for any $k$ and $j$. 

However, we also have some special features of the complex case. 

**Theorem.** Suppose $f : U \to V$ is a bijective holomorphic map between two open subsets $U, V \subset \mathbb{C}^n$. Then $\det J(f)$ is nonvanishing. In particular, $f$ is a holomorphic homeomorphism. 

> *Proof:* Prove by induction on $n$. The case when $n = 1$ is proved in the reviewing post of holomorphic functions of one variable. Suppose the assertion is proved for any $k < n$. Consider any $z_0 \in U$ such that $\det J(f)(z_0) = 0$. We claim that $J(f)(z_0) = 0$. Assume that $\mathrm{rank} J(f)(z_0) = k \geq 1$. Then we may suppose that $(\partial f^\alpha / \partial z^j)_{1 \leq \alpha, j \leq k}$ is nonsingular. By the inverse function theorem, $$\tilde{z}^\alpha = f^\alpha(z), \quad 1 \leq \alpha \leq k; \quad \tilde{z}^\beta = z^\beta, \quad k + 1 \leq \beta \leq n,$$ form a local coordinate system around $z_0$. It is clear that $f$ maps $U' = Z(\tilde{z}^1, \cdots, \tilde{z}^k) \cap U$ bijectively to $Z(w^1, \cdots, w^k) \cap V$. However, the Jacobian of the restriction of $f$ to $U'$ is singular at $z_0$, which contradicts the induction hypothesis. We conclude that we must have $J(f)(z_0) = 0$.
>
> By the above discussion, we see that $f$ is constant on each connected component of $Z(\det J(f))$. Since Weierstrass preparation theorem tells us that $Z(\det J(f))$ has positive dimension locally if it is nonempty, the injectivity of $f$ implies that $\det J(f)$ is nonvanishing on $U$.

## Submanifolds and subvarieties

Like the real case, we can consider submanifolds of a compplex manifold. Suppose $M$ is a complex manifold of dimenional $n$. Then a $k$-dimensional **complex submanifold** $N$ is a subset of $M$ satisfying that there is a collection of holomorphic coordinate charts $(U_\alpha, \varphi_\alpha)$ of $M$ covering $N$ such that for each $\alpha$, $$\varphi_\alpha(N \cap U_\alpha) = \varphi_\alpha \cap (\mathbb{C}^k \times 0).$$

By the inverse function theorem, we can see that this is equivalent to that $N$ is given by the zero sets of holomorphic functions $f^1, \cdots, f^{n-k}$ such that $\mathrm{rank} J(f^1, \cdots, f^{n-k}) = n - k$. 

The idea of express a subset as the zero set of some holomorphic functions gives us the concept of *subvarieties*. An **analytic subvariety** $V$ of a complex manifold $M$ is a subset given locally as the zero set of a finite collection of holomorphic functions. A point $p \in V$ is called a **smooth point** or a **regular point** if $V$ is given in a neighborhood of $p$ by holomorphic functions $f^1, \cdots, f^k$ with $\rank J(f^1, \cdots, f^k) = k$. Denote the set of regular points on $V$ by $V_\mathrm{reg}$, and let $V_\mathrm{sing} = V \setminus V_\mathrm{reg}$. The points in $V_\mathrm{sing}$ are called **sigular points** of $V$. An analytic variety $V$ is **irreducible** if it cannot be written as the union of two proper analytic subvarieties. 

We can see that each connected component of $V_\mathrm{reg}$ is a complex submanifold $M$. There is a theorem saying that *an analytic variety $V$ is irreducible if and only if $V_\mathrm{reg}$ is connected*. Thus we can define the dimension of an irreducible variety $V$ to be the dimensional of $V_\mathrm{reg}$. 

## Differential forms on a complex manifold

The last part of this post devotes to some discussion of $(p,q)$-forms on a complex manifold $M$. Viewing $M$ as a smooth manifold, we can consider the space $A_\mathbb{R}^n(M)$ of $n$-forms on $M$. Let $$A_\mathbb{C}^n(M) = A_\mathbb{R}^n(M) \otimes_\mathbb{R} \mathbb{C}.$$ Then the exterior differentiation gives a linear map $$\mathrm{d} : A_\mathbb{C}^n(M) \to A_\mathbb{C}^{n+1}(M).$$ 

For each point $z \in M$, the decomposition $$T^*_{\mathbb{C},z}(M) = T^{*1,0}_z(M) \oplus T^{*0,1}_z(M)$$ gives a decomposition $$\wedge^n T^*{\mathbb{C},z}(M) = \bigoplus_{p+q=n} T^{*p,q}_z(M),$$ where $$T^{*p,q}_z(M) = (\wedge^p T^{*1,0}_z(M)) \wedge (\wedge^q T^{*0,1}_z(M)).$$ Correspondigly, we obtain the decomposition $$A_\mathbb{C}^n(M) = \bigoplus_{p+q=n} A^{p,q}(M),$$ where $A^{p,q}(M)$ consists of $n$-forms $\omega$ satisfying $\omega_z \in T^{*p,q}_z(M)$ for each $z \in M$. A form $\omega \in A^{p,q}(M)$ is said be of **type $(p,q)$**, and is also called a **$(p,q)$-form** on $M$. 

