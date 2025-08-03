---
title: Embedding of compact complex manifolds - 2
date: 2025-08-02 11:50:00
tags:
	- complex geometry
	- math
mathjax: true
---

Recall that a holomorphic map from a complex manifold $M$ to the projective space $\mathbb{P}^n$ can be realized by some holomorphic sections of a line bundle on $M$ satisfying some conditions. Thus the line bundles on a compllex manifold are important in the study of embedding into the projective spaces. Since divisors are closely related to line bundles, they are also frequently considered. In this setion we introduce a fundamental technique in complex geometry called *blowing up*, which can reduce singularities of sections and induce divisors from points on complex manifolds. 

## Construction of blow-ups

<!-- the blow-up of a polydisc at the origin -->

Suppose $U = D(0,r) \subset \mathbb{C}^n$ is a polydisc centered at the origin in $\mathbb{C}^n$, with the Euclidean coordinates $z = (z^1, \cdots, z^n)$. Consider the submanifold of $U \times \mathbb{P}^{n-1}$ given by $$\tilde{U} = \\\{(z, [w^1, : \cdots : w^n]) \in U \times \mathbb{P}^{n-1} \mid z^iw^j = z^jw^i, \\\; 1 \leq i, j \leq n\\\}.$$ It is clear that $\tilde{U}$ can also expressed as $$\tilde{U} = \\\{(z, l) \in U \times \mathbb{P}^{n-1} \mid z \in l\\\},$$ which shows that $\tilde{U}$ is a submanifold of the universal bundle $J$ on $\mathbb{P}^{n-1}$. Let $\pi : \tilde{U} \to U$ be the natural projection. Then $\pi$ gives a bijective map $$\pi : \tilde{U} \setminus \pi^{-1}(0) \to U \setminus \\\{0\\\},$$ and $\pi^{-1}(0)$ is naturally identified with $\mathbb{P}^{n-1}$. The manifold $\tilde{U}$, together with the projection $\pi$, is called the **blow-up** of $U$ at the origin. 

**Proposition.** $\tilde{U}$ is an $n$-dimensional complex submanifold of $U \times \mathbb{P}^{n-1}$. With respect to this complex structure, $\pi : \tilde{U} \setminus \pi^{-1}(0) \to U \setminus \\\{0\\\}$ is a holomorphic homeomorphism. 

> *Proof:* Let $U_k$ be the open subset of $U \times \mathbb{P}^{n-1}$ given by $$U_k = \\\{(z, [w^1 : \cdots : w^n]) \mid w^k \neq 0\\\}, \quad k = 1, \cdots, n.$$ Consider the holomorphic coordinates $\varphi_k : U_k \to \mathbb{C}^{2n-1}$ of $U \times \mathbb{P}^{n-1}$ on $U_k$ given by $$\varphi_k(z, [w^1 : \cdots : w^n]) = \left(\frac{w^1}{w^k}, \cdots, \frac{w^{k-1}}{w^k}, z^k, \frac{w^{k+1}}{w^k}, \cdots, \frac{w^n}{w^k}, z^1 - \frac{w^1}{w^k}z^k, \cdots, \widehat{z^k - \frac{w^k}{w^k}z^k} \cdots, z^n - \frac{w^n}{w^k}z^k\right), \quad w^k \neq 0.$$ Then it is direct to see that $\tilde{U}_k = \tilde{U} \cap U_k$ is determined by $$\varphi_k(\tilde{U}_k) = \varphi_k(U_k) \cap (\mathbb{C}^n \times \\\{0\\\}), \quad k = 1, \cdots, n,$$ showing that $\tilde{U}$ is an $n$-dimensional complex submanifold of $U \times \mathbb{P}^{n-1}$. The corresponding coordinates on $\tilde{U}$ are given by $$\varphi_k : \tilde{U}_k \to \mathbb{C}^n, \quad (z, [w^1 : \cdots : w^n]) \mapsto \left(\frac{w^1}{w^k}, \cdots, \frac{w^{k-1}}{w^k}, z^k, \frac{w^{k+1}}{w^k}, \cdots, \frac{w^n}{w^k}\right).$$
>
> With respect to this complex structure, it is not hard to see that $\pi : \tilde{U} \setminus \pi^{-1}(0) \to U \setminus \\\{0\\\}$ and its inverse $$\pi^{-1} : U \setminus \\\{0\\\} \to \tilde{U} \setminus \pi^{-1}(0), \quad z \mapsto (z, [z^1 : \cdots : z^n])$$ are both holomorphic maps, implying that $\pi$ is a holomorphic homeomorphism. 

---

<!-- the blow-up of a complex manifold at some point -->

Now suppose $M$ is a complex manifold and $p$ is a point on $M$. Suppose $U$ is a neighborhood of $p$ such that under a coordinate map, $p$ corresponds to the origin and $U$ corresponds to a polydisc centered at the origin. We can consider the blow-up $\tilde{U}$ of $U$ at $p$, together with the projection $\pi : \tilde{U} \to U$. 

Let $\tilde{M}$ be the manifold obtained by sticking $\tilde{U}$ to $M \setminus \\\{p\\\}$ by $\pi : \tilde{U} \setminus \pi^{-1}(p) \xrightarrow{\sim} U \setminus \\\{p\\\}$, i.e, $$\tilde{M} = \left(M \setminus \\\{p\\\}\right) \cup_\pi \tilde{U} = \frac{(M \setminus \\\{p\\\}) \sqcup \tilde{U}}{x \sim \pi(x), \quad x \in \tilde{U} \setminus \pi^{-1}(p)}.$$ We see that 
+ $\pi$ extends to a projection $\pi : \tilde{M} \to M$, 
+ $\tilde{M}$ has a complex structure obtained from that of $M$ and $\tilde{U}$, 
+ $\pi^{-1}(p)$ is naturally identified with $\mathbb{P}^{n-1}$, and 
+ $\pi : \tilde{M} \setminus \pi^{-1}(p) \to M \setminus \\\{p\\\}$ is a holomorphic homeomorphism. 

The complex manifold $\tilde{M}$, together with $\pi : \tilde{M} \to M$, is called the **blow-up** of $M$ at the point $p$. 

<!-- the independence of the coordinates -->

Although the above construction of the blow-up needs the local coordinates near $p$, the result manifold is actually independent of the choice of the coordinates. First note that if $V \subset U$ is another open neighborhood of $p$ with the induced coordinates, then the blow-ups of $M$ at $p$ constructed from $\tilde{V}$ and $\tilde{U}$ are naturally holomorphicly homeomorphic to each other. Now suppose $u^j$ is another coordinate system on $U$ centered at $p$. Then there are holomorphic functions $f^1, \cdots, f^n$ such that $$u^j = f^j(z^1, \cdots, z^n), \quad j = 1, \cdots, n.$$ Denote by $\tilde{U}'$ the blow-up of $U$ at $p$ given by $u^j$, together with the projection $\pi' : \tilde{U}' \to U$. We see that there is a holomorphic homeomorphism $\tilde{f} : \tilde{U} \to \tilde{U}'$ expressed as $$\tilde{f}(z^1, \cdots, z^n, [z^1 : \cdots : z^n]) = (u^1, \cdots, u^n, [u^1 : \cdots : u^n]), \quad (z^1, \cdots, z^n) \neq 0,$$ and $$\tilde{f}(0, [w^1 : \cdots : w^n]) = (0, [v^1 : \cdots : v^n]), \quad [w^1 : \cdots : w^n] \in \mathbb{P}^{n-1},$$ where $$v^j = \sum_{k=1}^n \frac{\partial f^j}{\partial z^k}(0) \cdot w^k, \quad j = 1, \cdots, n.$$ It is clear that $\pi = \pi' \circ \tilde{f}$, implying that $\tilde{f}$ extends a holomorphic homeomophism $$\tilde{f} : (M \setminus \\\{p\\\}) \cup_\pi \tilde{U} \to (M \setminus \\\{p\\\}) \cup_{\pi'} \tilde{U}'.$$ 

The independence can also be interpreted as that the way we attach $\mathbb{P}^{n-1}$ to the point $p$ is somehow independent of the coordinates. 

Suppose $V$ is a finite-dimensional complex vector space. We define the associated projective space $\mathbb{P}(V)$ of $V$ to be the set of $1$-dimensional subspace of $V$. $\mathbb{P}(V)$ admits a structure of complex manifold natually as the complex structure on $\mathbb{P}^m$. If $\dim V = d > 0$, then any basis of $V$ gives a holomorphic homeomorphism from $\mathbb{P}(V)$ to $\mathbb{P}^{d-1}$.

Now $\mathbb{P}(T^{1,0}\_p(M))$ is a complex manifold holomorphicly homeomorphic to $\mathbb{P}^{n-1}$. The blow-up $\tilde{M}$ of $M$ at $p$ can be identified with the disjoint union of $M \setminus \\\{p\\\}$ and $\mathbb{P}(T^{1,0}\_p(M))$. The complex stucture of $\tilde{M}$ can be determined by specifying that for each $D(0,r) \subset \mathbb{C}$ and each holomorphic map $F : D(0,r) \to M$ such that $F^{-1}(p) = \\\{0\\\}$ and the tangent map of $F$ at $0$ is nonzero, the induced map $\tilde{F} : D(0,r) \to \tilde{M}$ given by $$\tilde{F}(0) = \left[F_\*\left(\frac{\partial}{\partial z}\right)\right] \in \mathbb{P}(T^{1,0}\_p(M)); \quad \tilde{F}(z) = F(z), \quad z \in D(0,r) \setminus \\\{0\\\},$$ is holomorphic. 

It is not hard to see that if $M$ is a compact complex manifold and $p$ is a point in $M$, then the blow-up $\tilde{M}$ of $M$ at $p$ is also compact. 

## Exceptional divisors

For the blow-up $\pi : \tilde{M} \to M$ of a complex manifold $M$ at a fixed point $p \in M$, we define the **exceptional divisor** $E_p$ (or $E$ for short) to be the inverse image $\pi^{-1}(p) \subset \tilde{M}$. We have seen that $E$ is holomorphicly homeomorphic to $\mathbb{P}^{n-1}$. 

**Proposition.** $E$ is indeed a divisor on $\tilde{M}$.

> *Proof:* Consider the open cover $\\\{\tilde{U}_0, \tilde{U}_1, \cdots, \tilde{U}_n\\\}$ of $\tilde{M}$, where $\tilde{U}_0 = \tilde{M} \setminus E = M \setminus \\\{p\\\}$. On each $\tilde{U}_k$, we have the coordinate system $$(z^1, \cdots, z^n, [w^1 : \cdots : w^n]) \mapsto \left(\frac{w^1}{w^k}, \cdots, \frac{w^{k-1}}{w^k}, z^k, \frac{w^{k+1}}{w^k}, \cdots, \frac{w^n}{w^k}\right),$$ and it is clear that $$E \cap \tilde{U}_k = Z(z^k), \quad k = 1, \cdots, n.$$ It follows that $E$ is a divisor on $\tilde{M}$ given by $$\\\{(U_0, 1); \\\; (U_k, z^k), \\\; 1 \leq k \leq n\\\} \in H^0\left(\tilde{M}; \mathcal{O}^\*\_{\tilde{M}}\right).$$

As a divisor, $E$ induces a line bundle $[E]$ on $\tilde{M}$. Considering the transition functions of $[E]$, it is not hard to see the following proposition:

<!-- $[E]|_E \cong J$ -->

**Proposition.** Under the identification $E \xrightarrow{\sim} \mathbb{P}(T^{1,0}\_p(M))$, the line bundle $[E]|\_E$ on $E$ is isomorphic to the universal bundle $J$ on $\mathbb{P}(T^{1,0}\_p(M))$. 

It follows that the line bundle $[-E]|\_E$ on $E$ is isomorphic to the hyperplane bundle $H = J^\*$ on $\mathbb{P}(T^{1,0}\_p(M))$. Noting that the fiber of $H$ on $l \in \mathbb{P}(T^{1,0}\_p(M))$ is naturally identified with the dual space $l^\*$ of $l$, we see that each linear functional on $T^{1,0}\_p(M)$ gives a global section of $H$. Thus there is a natural map $$T^{*1,0}\_p(M) \to H^0(\mathbb{P}(T^{1,0}\_p(M)); \mathcal{O}(H)) \xrightarrow{\sim} H^0(E; \mathcal{O}\_E([-E])).$$ 

<!-- $H^0(E; \mathcal{O}_E([-E])) \cong T^{*1,0}_x(M) -->

**Lemma.** For each nontrivial complex vector space $V$, the canonical map $V^\* \to H^0(\mathbb{P}(V); \mathcal{O}(H))$ is a linear isomorphism. 
> *Proof:* It suffices to show for $V = \mathbb{C}^{m+1}$, that is, to show that the map $$\mathbb{C}^1[z^0 : \cdots : z^m] \to H^0(\mathbb{P}^m; \mathcal{O}(H))$$ is a linear isomorphism, where $\mathbb{C}^1[z^0 : \cdots : z^m]$ is the space of homogeneous linear functions in $z^0, \cdots, z^m$. 
>
> The injectivity and the linearity are both direct. It remains to show the surjectivity. Suppose $f_0$ is a nonzero homogenuous linear function with the corresponding section $s_0 \in H^0(\mathbb{P}^m; \mathcal{O}(H))$. For any nonzero section $s \in H^0(\mathbb{P}^m; \mathcal{O}(H))$, $g = s / s_0$ defines a meromorphic function on $\mathbb{P}^m$. Composing with the projection $\mathbb{C}^{m+1} \setminus \\\{0\\\} \to \mathbb{P}^m$, we obatin a meromorphic $\tilde{g}$ on $\mathbb{C}^{m+1} \setminus \\\{0\\\}$. It is direct to see that $f = g \cdot f_0$ is a holomorphic function on $\mathbb{C}^{m+1} \setminus \\\{0\\\}$, which extends to the whole $\mathbb{C}^{m+1}$ by Hartogs' theorem. The definition of $g$ and $f_0$ implies that $f(\lambda \cdot z) = \lambda \cdot z$ for any $z \in \mathbb{C}^{m+1}$, and hence by considering the Taylor's expansion of $f$ at $0$, we see that $f \in \mathbb{C}^1[z^0 : \cdots : z^m]$. Clearly $f$ corresponds to the section $s$ of $\mathcal{O}(H)$. 

**Corollary.** The canonical map $T^{*1,0}\_p(M) \to H^0(E; \mathcal{O}\_E([-E]))$ is an isomorphism. 

Recall that for a divisor $D$ on a complex manifold, each meromorphic function $g$ with $(g) + D \geq 0$ defines a global holomorphic section of $[D]$. Note that if $f$ is a holomorphic function on a neighborhood $U$ of $p$ such that $f(p) = 0$, then $\pi^\*f = f \circ \pi$ is a holomorphic function on $\tilde{U}$ such that $\pi^\*f$ vanishes on $E$, i.e., $(\pi^\*f) - E \geq 0$. Therefore there is a natural map $$H^0(U; \mathcal{I}_p) \to H^0(\tilde{U}; \mathcal{O}([-E])).$$ It turns out that this can be realized by taking the differetial of the function at $p$, i.e., the following diagram commutes:

<img src="/image/embedding_2.jpg" width=40% />

The difference between the canonical bundle on $\tilde{M}$ and that on $M$ is also described by the exceptional divisor $E$. We see from direct computations of transition functions that the following proposition holds. 

<!-- $K_{\tilde{M}} \cong \pi^*K_M \otimes [(n-1)E] -->

**Proposition.** The canonical bundle on $\tilde{M}$ is described as $$K_{\tilde{M}} \cong \pi^\* K_M \otimes [(n-1)E].$$ 

<!-- the curvature of $[E]$; positivity of $\pi^*L^k \otimes [-E]$ -->
The last but not the least important thing is how to lift a positive line bundle on $M$ to a line bundle on $\tilde{M}$. In general, the pullback $\pi^\*L$ of a positive line bundle $L \to M$ is no longer positive because the corresponding curvature $\pi^\*\Omega_L$ vanishes along $T^{1,0}\_x(E)$ for any $x \in E$. The correct construction is as follows:

**Proposition.** Suppose $L \to M$ is a positive line bundle on $M$. Then there exists a positive integer $k_0$ such that the line bundle $\pi^\* L^k \otimes [-E]$ on the blow-up $\tilde{M}$ is positive for any positive integer $k \geq k_0$. 

> *Proof:* Consider an open neighborhood $U$ of $p$ in $M$. Let $$h_k(z,[w^1 : \cdots : w^n]) = \frac{|w^k|^2}{|w^1|^2 + \cdots + |w^k|^2}, \quad (z, [w^1 : \cdots : w^n]) \in \tilde{U}_k,$$ where $k = 1, \cdots, n$. Then $h = \\\{h_k\\\}$ gives a hermitian metric on $[-E]|\_U$, which determines a real $(1,1)$-form expressed locally as $$\omega = -\frac{i}{2\pi}\partial\bar{\partial}\log h_k = \frac{i}{2\pi}\partial\bar{\partial}\log \left(1 + \left|\frac{w^1}{w^k}\right|^2 + \cdots + \widehat{\left|\frac{w^k}{w^k}\right|^2} + \cdots + \left|\frac{w^n}{w^k}\right|^2\right).$$ We see that $\omega$ is nonnegative on $U$, and is positive along $T^{1,0}\_x(E)$ for any $x \in E$. 
>
> Since $[-E]$ is a trivial line bundle outside any neighborhood of $E$, we can take a hermitian metric $h'$ on $[-E]$ such that $h'$ is constant outside a neighborhood $V \subset U$ of $E$. Take a smooth function $\rho$ on $\tilde{M}$ such that $0 \leq \rho \leq 1$, $\rho \equiv 1$ on $V$ and $\rho \equiv 0$ outside $U$. Then $\tilde{h} = \rho h + (1 - \rho) h'$ is a hermitian metric on $[-E]$, with the corresponding $(1,1)$ form $\tilde{\omega}$ satisfying that $\omega$ vanishes outside $\mathrm{supp}\rho$, is nonnegative on $V$, and is positive along $T^{1,0}\_x(E)$ for any $x \in E$. 
>
> Suppose that $h_L$ is a hermitian metric on $L$ such that the corresponding $(1,1)$-form $\omega_L$ is positive definite on $M$. Then $\pi^\*h_L = h_L \circ \pi$ is a hermitian metric on $\pi^\* L$ whose $(1,1)$-form is exactly $\pi^\*\omega_L$. We can see that $\pi^\*\omega_L$ is positive outside the holomorphic tangent space of $E \subset \tilde{M}$, and vanishes along $T^{1,0}\_x(E)$ for any $x \in E$. 
>
> Note that $S = \mathrm{supp}\rho \setminus V$ is a compact subset, $\tilde{\omega}$ is bounded below on $S$. As $\pi^\*\omega_L$ is positive on $S$, there exists $k_0 > 0$ such that $k \cdot \pi^\*\omega_L + \tilde{\omega}$ is positive on $S$ for any $k \geq k_0$. Now $\pi^\* h_L^k \cdot \tilde{h}$ gives a hermitian metric on $\pi^\* L^k \otimes [-E]$ with the corresponding $(1,1)$-form $k \cdot \pi^\*\omega_L + \tilde{\omega}$ positive definite everywhere, showing that $\pi^\* L^k \otimes [-E]$ is a positive line bundle on $M$. 