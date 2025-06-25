---
title: Holomorphic vector bundles - 2
date: 2025-06-25 12:48:00
tags:
	- complex geometry
	- math
mathjax: true
---

In this post we focus on holomorphic line bundles and discuss some relations between divisors and line bundles. 

## Definition of divisors

Suppose $M$ is an $n$-dimensional complex manifold and $V \subset M$ is an analytic subvariety of dimension $n-1$. For each $p \in V$, there is a neighborhood of $p$ such that $V$ is defined as the zero set of a holomorphic function $f$ on this neighborhood. This functions $f$ is called a *local defining function* for $V$ near $p$, and is unique up to multiplication by a function nonzero at $p$.

**Proposition.** Suppose $M$ is a complex manifold and $V$ is an analytic hypersurface on $M$. Then for any connected component $V_k$ of $V_\mathrm{reg}$, the closure $\overline{V}_k$ is an analytic variety.

**Corollary.** An analytic hypersurface $V$ is irreducible if and only if $V_\mathrm{reg}$ is connected.

We see from this proposition that each analytic hypersurface can expressed uniquely as the union of some irreducible analytic hypersurfaces.

Now we define a **divisor** $D$ on $M$ is a locally finite formal linear combination $$D = \sum_k a_k \cdot V_k, \quad a_k \in \mathbb{Z}$$ of irreducible analytic hypersurfaces of $M$. The local finiteness here means that for each $p \in M$ there is a neighborhood of $p$ intersecting with only finitely many $V_k which appear in $D$. The divisors on $M$ form an additive group $\mathrm{Div}(M)$. If $a_k \geq 0$ holds for all $k$, then we call $D$ an **effective** divisor, written as $D \geq 0$. Note that if $V$ is an analytic hypersurface, then we can identified it with the divisor $$\sum_k V_k, \quad V = \bigcup_k V_k.$$ 

Suppose $V$ is an irreducible analytic hypersurface, $p \in V_\mathrm{reg}$ and $f$ is a defining function for $V$ near $p$. For any meromorphic function $g$ defined in a neighborhood of $p$, we can define the **order** $\mathrm{ord}_{V,p}(g)$ of $g$ along $V$ at $p$ to be the unique integer $r$ such that $$g = f^r \cdot h, \quad h \in \mathcal{O}^*_{X,x}.$$ This is independent of the choice of the defining function $f$ and the point $p$. Thus we can simply define the order of $g$ along $V$ to be $$\mathrm{ord}_V(g) = \mathrm{ord}_{V,p}(g).$$ We say $g$ has a zero of order $d$ along $V$ if $\mathrm{ord}_V(g) = d > 0$, and that $g$ has a pole of order $d$ along $V$ if $\mathrm{ord}_V(g) = -d < 0$. We can see that for any two meromorphic functions $g, h$, it holds that $$\mathrm{ord}_V(g \cdot h) = \mathrm{ord}_V(g) + \mathrm{ord}_V(h).$$ 

Now consider a nonzero meromorphic function $f$ on $M$. The divisor associated to $f$ is given by $$(f) = \sum_V \mathrm{\ord}_V(f) \cdot V \in \mathrm{Div}(M).$$ This divisor can be written as the difference of two effective divisor, namely the *zero divisor* $$(f)_Z = \sum_{\mathrm{ord}_V(f) > 0} \mathrm{ord}_V(f) \cdot V,$$ and the *pole divisor* $$(f)_P = -\sum_{\mathrm{ord}_V(f) < 0} \mathrm{ord}_V(f) \cdot V.$$

The divisors can be constructed in sheaf-theoretic terms. We claim that a divisor $D$ on $M$ is equivalent to a global section of the quotient sheaf $\mathcal{M}^*_M / \mathcal{O}^*_M$, and then we have the natural isomorphism $$H^0(M; \mathcal{M}^*_M / \mathcal{O}^*_M) = \mathrm{Div}(M).$$ 

On the one hand, a global section of $\mathcal{M}^*_M / \mathcal{O}^*_M$ is given by an open cover $U_\alpha$ of $M$ and meromorphic functions $f_\alpha$ on $U_\alpha$ that are not identically zero with $$\frac{f_\alpha}{f_\beta} \in \mathcal{O}^*_M(U_\alpha \cap U_\beta).$$ Thus for any analytic hypersurface $V$ we have $$\mathrm{ord}_V(f_\alpha) = \mathrm{ord}_V(f_\beta)$$ if they are defined. The corresponding divisor is then given by $$D = \sum_V \mathrm{ord}_V(f_\alpha) \cdot V,$$ where $f_\alpha$ is chosen such that $V \cap U_\alpha = \varnothing$. 

On the other hand, given a divisor $$D = \sum_k a_k \cdot V_k,$$ thee is an open cover $U_\alpha$ of $M$ such that every $V_k$ has a local defining function $g_{k,\alpha}$ in each $U_\alpha$. We then let $$f_\alpha = \prod_k g_{k,\alpha}^{a_k} \in \mathcal{M}^*_M(U_\alpha)$$ to obtain a global section of $\mathcal{M}^*_M / \mathcal{O}^*_M$. 

We see from the above constructions that the identification $$H^0(M; \mathcal{M}^*_M / \mathcal{O}^*_M) = \mathrm{Div}(M)$$ is actually a homomorphism and hence an isomorphism. 

Suppose $f : M \to N$ is a holomorphic map between complex manifolds. Then for each divisor $D$ on $N$ such that the image of $f$ is not contained in the support of $D$, we may define the *pullback* $f^*D$ of $D$ along $f$. Suppose under the identification of a divisor with a section, $D$ is given by $(U_\alpha, g_\alpha)$, then $f^*D$ is the divisor on $M$ given by $(f^{-1}(U_\alpha), g_\alpha \circ f)$. For holomorphic functions $f : M \to N$ such that $f(M)$ is dense in $N$, we then obtain a homomorphism $$f^* : \mathrm{Div}(N) \to \mathrm{Div}(M).$$

## Relations between divisors and line bundles

Recall that a line bundle on a complex manifold $M$ can be given by an open cover $U_\alpha$ of $M$ and transition functions $$g_{\alpha\beta} : U_\alpha \cap U_\beta \to \mathbb{C}^*$$ of $M$. Using this description, it is not hard to see that the set of line bundles on $M$ can be identified with $H^1(M; \mathcal{O}^*_M)$. 

The set of line bundles on $M$ can be given the structure of group with multiplication given by tensor product and inverses given by dual bundles. This group is called the **Picard group** of $M$, denoted by $\mathrm{Pic}(M)$. Note that the group structure of $\mathrm{Pic}(M)$ and the group structure of $H^1(M; \mathcal{O}^*_M)$ is actually the same, we have the natural isomorphism $$\mathrm{Pic}(M) = H^1(M; \mathcal{O}^*_M).$$ 

Now we attempt to associate a line bundle to each divisor on $M$. Let $D$ be a divisor on $M$ with local defining functions $f_\alpha \in \mathcal{M}^*_M(U_\alpha)$ over an open cover $U_\alpha$ of $M$. Then the transition functions $$g_{\alpha\beta} = \frac{f_\alpha}{f_\beta} \in \mathcal{O}^*_M(U_\alpha \cap U_\beta)$$ determine a line bundle $[D]$ on $M$, called the *associated line bundle* of $D$. This is independent of $f_\alpha$ and hence well-defined. 

We see the following properties of $[D]$:
+ if $D_1$ and $D_2$ are divisors on $M$, then $$[D_1 + D_2] = [D_1] \otimes [D_2],$$ implying that the corresponding map $\mathrm{Div}(M) \to \mathrm{Pic}(M)$ is homomorphism;
+ the line bundle $[D]$ is trivial if and only if there is a nonzero meromorphic function $f$ on $M$ such that $D = (f)$. 

Thus we say that two divisors $D_1$ and $D_2$ are *linearly equivalent* if $D_1 = D_2 + (f)$ for some nonzero meromorphic $f$ on $M$, or equivalently $[D_1] = [D_2]$, written as $D_1 \sim D_2$.

The above discussion can be interpreted in the sheaf-theoretic opinion. Consider the exact sequence of sheaves on $M$ $$0 \to \mathcal{O}^*_M \to \mathcal{M}^*_M \to \mathcal{M}^*_M / \mathcal{O}^*_M \to 0.$$ This induces the exact sequence of cohomology groups that $$H^0(M; \mathcal{M}^*_M) \to H^0(M; \mathcal{M}^*_M / \mathcal{O}^*_M) \to H^1(M; \mathcal{O}^*_M).$$ Identifying the corresponding cohomology groups with $\mathrm{Div}(M)$ and $\mathrm{Pic}(M)$, respectively, we see that the homomorphism $$H^0(M; \mathcal{M}^*_M) \to H^0(M; \mathcal{M}^*_M / \mathcal{O}^*_M)$$ maps each meromorphic function $f$ to the divisor $(f)$, and the homomorphism $$H^0(M; \mathcal{M}^*_M / \mathcal{O}^*_M) \to H^1(M; \mathcal{O}^*_M)$$ maps each divisor $D$ to the line bundle $[D]$. Hence the latter property of the associated line bundle is nothing else than the exactness of the sequence. 

## Holomorphic and meromorphic sections of line bundles

Suppose $\pi : L \to M$ is a holomorphic line bundle on a complex manifold $M$ with trivializations $$\varphi_\alpha : \pi^{-1}(U_\alpha) \to U_\alpha \times \mathbb{C}$$ and corresponding transition functions $\psi_{\alpha\beta}$. These trivializations induce ismorphisms $$\varphi_\alpha^* : \mathcal{O}_M(L)(U_\alpha) \to \mathcal{O}_M(U_\alpha),$$ and then give a correspondence $$s \in \mathcal{O}_M(L)(U) \mapsto s_\alpha = \varphi_\alpha^*(s) \in \mathcal{O}_M(U \cap U_\alpha).$$ Thus a section of $L$ on $U$ is equivalent to a collection of functions $s_\alpha \in \mathcal{O}_M(U \cap U_\alpha)$ satisfying on each $U \cap U_\alpha \cap U_\beta$ $$s_\alpha = \psi_{\alpha\beta} \cdot s_\beta.$$

According to this point of view, we define a **meromorphic section** $s$ of $L$ on $U \subset M$ to be given by a collection of meromorphic functions $s_\alpha \in \mathcal{M}_M(U \cap U_\alpha)$ satisfying $$s_\alpha = \psi_{\alpha\beta} \cdot s_\beta$$ on each $U \cap U_\alpha \cap U_\beta$. This is equivalent to the section on $U$ of the sheaf $$\mathcal{M}_M(L) = \mathcal{O}_M(L) \otimes_{\mathcal{O}_M} \mathcal{M}_M.$$ Note that the quotient of two nonzero meromorphic sections of $L$ is a well-defined meromorphic function on $M$. 

For a non-trivial global meromorphic section $s$ of $L$, we have $$\frac{s_\alpha}{s_\beta} = \psi_{\alpha\beta} \in \mathcal{O}^*_M(U_\alpha \cap U_\beta),$$ implying that for any irreducible hypersurface $V \subset M$, we have $$\mathrm{ord}_V(s_\alpha) = \mathrm{ord}_V(s_\beta).$$ Thus we can define the **order** of $s$ along $V$ by $$\mathrm{ord}_V(s) = \mathrm{ord}_V(s_\alpha), \quad V \cap U_\alpha \neq \varnothing.$$ The *divisor associated to $s$* is then given by $$(s) = \sum_V \mathrm{ord}_V(s) \cdot V.$$ It is clear that $s$ is holomorphic is and only if $(s)$ is effective.

**Proposition.** Suppose $M$ is a complex manifold. Then the image of the natural map $$\mathrm{Div}(M) \to \mathrm{Pic}(M)$$ consists of those line bundles admitting non-trivial meromorphic sections. 

> *Proof:* If $D \in \mathrm{Div}(M)$ is given by functions $f_\alpha \in \mathcal{M}_M(U_\alpha)$, then clearly these functions give a meromorphic section $s$ of $[D]$ with $(s) = D$. Conversely, suppose $L$ is given by transition functions $\psi_{\alpha\beta}$ and $s$ is a non-trivial global meromorphic section of $L$, then $s_\alpha / s_\beta = g_{\alpha\beta}$ and hence $L = [(s)]$.

The holomorphic sections of the line bundle $[D]$ associated to a divisor $D$ on $M$ may be constructed in the following way. Consider the set $\mathcal{L}(D)$ of meromorphic functions $f$ on $M$ such that $$D + (f) \geq 0.$$ Fixed a global meromorphic section $s_0$ of $[D]$ with $(s) = D$. On the one hand, any holomorphic section $s$ of $[D]$ induces a meromorphic function $f = s / s_0$ on $M$ such that $$D + (f) = (s_0) + (f) = (s) \geq 0.$$ On the other hand, any meromorphic function $f \in \mathcal{L}(D)$ gives a holomorphic section $s = f \cdot s_0$ of $[D]$. Thus we obtain a bijection $$\mathcal{L}(D) \to H^0(M; \mathcal{O}_M([D])).$$ 

We end this post with some discussion of the relations between holomorphic sections of line bundles and holomorphic maps into projective spaces. 