---
title: Complex manifolds - 3
date: 2025-06-23 10:32:00
tags:
	- complex geometry
	- math
mathjax: true
---

In analogy to the de Rham cohomology, we define the *Dolbeault cohomology* for complex manifolds. To compare this new cohomology with the sigular cohomology, the *sheaf theory* is applied. It is worth reminding that the sheaf theory is of great importance in the further study of complex geometry.


## Dolbeault cohomology

Suppose $M$ is a complex manifold. Let $Z^{p,q}(M)$ be the kernel of the linear map $$\bar{\partial} : A^{p,q}(M) \to A^{p,q+1}(M).$$ The forms in $Z^{p,q}(M)$ are said to be *$\bar{\partial}$-closed*. Since $\bar{\partial}^2 = 0$, we have $$\bar{\partial}A^{p,q-1}(M) \subset Z^{p,q}(M).$$ The **Dolbeault cohomology group (of order $(p,q)$)** of $M$ is then defined to be the quotient space $$H^{p,q}(M) = Z^{p,q}(M) / \bar{\partial}A^{p,q-1}(M).$$ 

We may consider the *functorial property* of the Dolbeault cohomology. Suppose $f : M \to N$ is a holomorphic map between compex manifolds. The pullback of differential forms gives maps $$f^* : A_\mathbb{C}^n(N) \to A_\mathbb{C}^n(M).$$ As $f$ is holomorphic, it can be verified that $$f^*(A^{p,q}(N)) \subset A^{p,q}(M).$$ 

Noting that $f^*$ commutes with $\bar{\partial}$, we obtain the induced homomorphisms 

$$f^* : H^{p,q}(N) \to H^{p,q}(M).$$ 

The Poincar&#233; lemma for $\mathbb{R}^n$ impies that the de Rham cohomology groups are locally trivial. In analogy, we have the following $\bar{\partial}$-Poincar&#233; lemma which suggets that the positive-order Dolbeault cohomology groups of a polydisc are trivial.

**Theorem ($\bar{\partial}$-Poincar&#233; lemma).** Suppose $D = D(0, r) \subset \mathbb{C}^n$ is a polydisc which can be unbounded and $q > 0$. If $\alpha \in A^{p,q}(D)$ is $\bar{\partial}$-closed, then there exists $\beta \in A^{p,q-1}(D)$ such that $\alpha = \bar{\partial}\beta$. 

We begin with the one-dimenional case.

**Lemma.** Suppose $U$ is an open neighborhood of the closure of a bounded disc $D(0,r) \subset \mathbb{C}$. Consider $\alpha = f \mathrm{d}\bar{z} \in A^{0,1}(U)$. Then the function $$g(z) = \frac{1}{2 \pi i}\int_{D(0,r)} \frac{f(\zeta)}{\zeta - z}\mathrm{d}\zeta \wedge \mathrm{d}\bar{\zeta}$$ is well-defined on $D(0,r)$ and satisfies $\bar{\partial}g = \alpha$.

> *Proof:* Consider any $0 < r' < r$. By the existence of the partition of unity, we may take the decomposition $$f = f_1 + f_2$$ with $f_1$ supported on $B(0,r)$ and $f_1$ supported outside $B(0, r')$. Let $$g_j(z) = \frac{1}{2 \pi i}\int_{D(0,r)} \frac{f_j(\zeta)}{\zeta - z}\mathrm{d}\zeta \wedge \mathrm{d}\bar{\zeta}, \quad j = 1,2.$$ It is clear that $g_2(z)$ is well-defined for $|z| < r'$. Consider the change of variable $\zeta = z + re^{i\varphi}$, we may write $$g_1(z) = \frac{1}{2 \pi i}\int_{D(0,r)} \frac{f_1(\zeta)}{\zeta - z}\mathrm{d}\zeta \wedge \mathrm{d}\bar{\zeta} = \frac{1}{2 \pi i}\int_\mathbb{C} \frac{f_1(\zeta)}{\zeta - z}\mathrm{d}\zeta \wedge \mathrm{d}\bar{\zeta} = \frac{1}{\pi}\int_\mathbb{C} f_1(z + re^{i\varphi})e^{-i\varphi} \mathrm{d}\varphi \wedge \mathrm{d}r,$$ which is certainly well-defined. Thus $g$ is well-defined for $|z| < r'$.
>
> Since $(\zeta - z)^{-1}$ is holomorphic in $z$ for $\zeta$ in the support of $f_2$, we see for $|z| < r'$ that $$\frac{\partial g_2}{\partial \bar{z}} = \frac{1}{2 \pi i}\int_{D(0,r)}f_2(\zeta)\frac{\partial ((\zeta - z)^{-1})}{\partial \bar{z}} \mathrm{d}\zeta \wedge \mathrm{d}\bar{\zeta} = 0.$$ Meanwhile, using the above expression of $g_1$, we can compute that $$\frac{\partial g_1}{\partial \bar{z}} = \frac{1}{2 \pi i}\int_{D(0,r)}\frac{\partial f_1}{\partial \bar{\zeta}} \frac{\mathrm{d}\zeta \wedge \mathrm{d}\bar{\zeta}}{\zeta - z}.$$ For a fixed $|z| < r'$ and any sufficiently small $\delta > 0$, we obtain from the Stokes' formula that $$\frac{1}{2 \pi i}\int_{D(0,r) \setminus D(z, \delta)} \frac{\partial f_1}{\partial \bar{\zeta}}\frac{\mathrm{d}\zeta \wedge \mathrm{d}\bar{\zeta}}{\zeta - z} = -\frac{1}{2 \pi i}\int_{D(0,r) \setminus D(z,\delta)} \mathrm{d}\left(\frac{f_1(\zeta)}{\zeta - z}\mathrm{d}\zeta\right) = \frac{1}{2 \pi i}\int_{\partial D(0,r)} \frac{f_1(\zeta)}{\zeta - z}\mathrm{d}\zeta.$$ Letting $\delta \to 0$, this yields $$\frac{\partial g}{\partial \bar{z}} = \frac{\partial g_1}{\partial \bar{z}} = f_1(z) = f(z), \quad |z| < r'.$$ Since $r'$ is arbitrary, we see that $\partial g = \alpha$ on the whole $D(0,r)$. 

**Lemma.** Suppose $U$ is an open neighborhood of the closure of a bounded polydisc $D(0,r) \subset \mathbb{C}^n$ and $q > 0$. If $\alpha \in A^{p,q}(U)$ is $\bar{\partial}$-closed, then there exists $\beta \in A^{p,q-1}(D(0,r))$ such that $\alpha = \bar{\partial}\beta$ on $D(0,r)$. 

> *Proof:* It suffices to prove for $p = 0$. Suppose $\alpha \in A^{0,q}(U)$ is given as $$\alpha = \sum_I f_I \mathrm{d}\bar{z}^I.$$ We claim that if the decomposition of $\alpha$ does not involve any $\mathrm{d}\bar{z}^j$ for $j > k$, then there exists $\gamma \in A^{0,q-1}(D(0,r))$ such that $\alpha - \bar{\partial}\gamma$ does not involve any $\mathrm{d}\bar{z}^j$ for $j > k - 1$. This is sufficient since the conclusion can be shown by induction after this assertion.
>
> Let $$\alpha_1 = \sum_{I:k \in I} f_I \mathrm{d} \bar{z}^{I \setminus k}, \quad \alpha_2 = \sum_{I:k \not\in I} f_I \mathrm{d} \bar{z}^I.$$ Then $$\alpha = \alpha_1 \wedge \mathrm{d}\bar{z}^k + \alpha_2.$$ Comparing the terms of $\bar{\partial}\alpha_1$ and $\bar{\partial}\alpha_2$, we have $\partial f_I / \partial \bar{z}^j = 0$ for any $j > k$ and $I$ such that $k \in I$. 
>
> Consider the functions $$g_I(z) = \frac{1}{2 \pi i}\int_{|z^k| < r_k}\frac{f_I(z^1, \cdots, z^{k-1}, \zeta, z^{k+1}, \cdots, z^n)}{\zeta - z^k} \mathrm{d}\zeta \wedge \mathrm{d}\bar{\zeta}, \quad z \in D(0,r).$$ Let $$\gamma = \sum_{I:k \in I} g_I \mathrm{d}z^{I \setminus k}.$$ Then the preceding lemma implies that this is the desired $\gamma$ up to a sign. 

Now we can prove the complete $\bar{\partial}$-Poincar&#233; lemma.

> *Proof of $\bar{\partial}$-Poincar&#233; lemma:* Consider a monotone increasing sequence $r_k$ tending to $r$ and let $D_k = D(0,r_k)$. The previous lemma yields for each $k$ some $\beta_k \in A^{p,q-1}(D)$ such that $\bar{\partial}\beta_k = \alpha$ on $D_k.$ It remains to show that these $\beta_k$ can be chosen such that they converge uniformly on each compact subset of $D$. 
>
> We procedure by induction on $k$. Suppose $\beta_k$ has been constructed. Take any $\tilde{\beta} \in A^{0,q-1}(D)$ such that $\bar{\partial}\tilde{\beta} = \alpha$ holds on $D_{k+1}$. Then $\bar{\partial}(\tilde{\beta} - \beta_k) = 0$ holds on $D_k$. When $q \geq 2$, there is some $\gamma \in A^{0,q-2}(D)$ such that $\bar{\partial}\gamma = \tilde{\beta} - \beta_k$ on $D_k$. The $\beta_{k+1}$ can then be given by $$\beta_{k+1} = \tilde{\beta} - \bar{\partial}\gamma.$$ 
>
> Now consider the case $q = 1$. We see that $\tilde{\beta} - \beta_k$ is holomorphic on $D_k$. Consider the power series expansion of this function and truncate it to get a polynomial $P$ such that $$\sup_{z \in D_{k-1}} |\tilde{\beta} - \beta_k - P| < \frac{1}{2^k}.$$ Then we can set $$\beta_{k+1} = \tilde{\beta} - P.$$ 
>
> In both cases we obtain a series $\beta_k$ such that $\beta = \lim_k \beta_k$ exists and satisfies $\bar{\partial}\beta = \alpha$ on $D$. 

## Sheaf theory on complex manifolds

The definitons and basic results in sheaf theory can be found in this [PDF file](/file/sheaf.pdf).

There are many examples of sheaves on a complex manifold $M$:

+ the locally constant sheaves $\underline{\mathbb{Z}}, \underline{\mathbb{Q}}, \underline{\mathbb{R}}, \underline{\mathbb{C}}$;
+ the additive sheaf $\mathcal{O}_M$ of holomorphic functions;
+ the multiplicative sheaf $\mathcal{O}^*_M$ of nonvanishing holomorphic functions;
+ the sheaf $\Omega^p_M$ of holomorphic $p$-forms, which can be expressed as $\sum f_I \mathrm{d}z^I$ with $f_I$ holomorphic;
+ the sheaf $\mathcal{A}^{p,q}_M$ of $(p,q)$-forms;
+ the sheaf $\mathcal{Z}^{p,q}_M$ of $\bar{\partial}$-closed $(p,q)$-forms;
+ the sheaf $\mathcal{I}_V$ of holomorphic functions vanishing on a fixed analytic subvariety $V \subset M$. 

Suppose $U$ is an open subset of $M$. A **meromorphic function** $f$ on $U$ is given locally as the quotient of two holomorphic functions. Precisely, there is a covering $U_\alpha$ of $U$ such that the restriction of $f$ on $U_\alpha$ is given by $g_\alpha / h_\alpha$ for each $\alpha$, where $g_\alpha$ and $h_\alpha$ are relatively prime in $\mathcal{O}(U_\alpha)$ and $g_\alpha h_\beta = h_\alpha g_\beta$ in $\mathcal{O}(U_\alpha \cap U_\beta)$. We can then consider the sheaf $\mathcal{M}_M$ of meromorphic functions and the multiplicative sheaf $\mathcal{M}^*_M$ of nonzero meromorphic functions. 

The exact sequences of sheaves on $M$ are widely used in the study of complex manifolds.

+ The exponential morphism $$\exp : \mathcal{O}_M \to \mathcal{O}^*_M$$ yields an exact sequence 
  
  $$0 \to \underline{\mathbb{Z}} \to \mathcal{O}_M \to \mathcal{O}^*_M \to 0.$$ This is called the *exponential sheaf sequence*.
+ Suppose $N \subset M$ is a submanifold. The sheaf $\mathcal{O}_N$ can be viewed as a sheaf on $M$. Then the sequence $$0 \to \mathcal{I}_N \to \mathcal{O}_M \to \mathcal{O}_N \to 0$$ is exact, where the morphisms are given by inclusion and restriction.
+ By the $\bar{\partial}$-Poincar&#233; lemma, the sequence $$0 \to \Omega^p_M \to \mathcal{A}^{p,0}_M \to \mathcal{A}^{p,1}_M \to \mathcal{A}^{p,2}_M \to \cdots$$ is exact. 

For a sheaf $\mathcal{F}$ on a topological space $X$ we can consider its cohomology groups $H^n(X; \mathcal{F})$. Basic results concerning the sheaf cohomology can also be found in this [PDF file](/file/sheaf.pdf). 

Applying the results of sheaf theory to a complex manifold $M$, we obtain the following theorem.

**Theorem (Dolbeault theorem).** Suppose $M$ is a complex manifold. Then we have the canonical isomorphism $$H^q(M; \Omega^p_M) = H^{p,q}(M)$$ for each nonnegative $p$ and $q$.
> *Proof:* Note that the exact sequence $$0 \to \Omega^p_M \to \mathcal{A}^{p,0}_M \to \mathcal{A}^{p,1}_M \to \mathcal{A}^{p,2}_M \to \cdots$$ gives an *acyclic* resolution of the sheaf $\Omega^p_M$, we have the canonical isomorphism $$H^q(M; \Omega^p_M) = H^q(\Gamma(M, \mathcal{A}^{p,-}_M)) = H^q(A^{p,-}(M)) = H^{p,q}(M).$$ 

Another application of the sheaf theory is the answer to the *Cousin problem*.

By $\bar{\partial}$-Poincar&#233; lemma, we have $$H^q(\mathbb{C}^n; \mathcal{O}) = H^q(\mathbb{C}^n; \Omega^0) = 0, \quad q > 0.$$ Meanwhile, by the singular cohomology, $$H^q(\mathbb{C}^n; \underline{\mathbb{Z}}) = H_\mathrm{sing}^q(\mathbb{C}^n; \mathbb{Z}) = 0, \quad q > 0.$$ Then the exponential exact sequence yields a long exact sequence of cohomoogy groups which implies that $$H^q(\mathbb{C}^n; \mathcal{O}^*) = 0, \quad q > 0.$$

**Proposition.** Any analytic hypersurface in $\mathbb{C}^n$ is the zero set of an entire function.

> *Proof:* Suppose $V \subset \mathbb{C}^n$ is an analytic hypersurface. For each $p \in \mathbb{C}^n$, there is a neighborhood of $p$ such that $V$ is given by a holomorphic $f \in O_{\mathbb{C}^n,p}$ in this neighborhood, and $f$ can be chosen to be of no square factor uniquely up to a unit. 
> 
> Thus there is a cover $U_\alpha$ of $\mathbb{C}^n$ and functions $f_\alpha \in \mathcal{O}(U_\alpha)$ such that $$Z(f_\alpha) = V \cap U_\alpha$$ for each $\alpha$, and that 
> 
> $$g_{\alpha\beta} = \frac{f_\alpha}{f_\beta} \in \mathcal{O}^*(U_\alpha \cap U_\beta)$$ 
> 
> for each $\alpha$ and $\beta$. Since 
> 
> $$H^1(\mathbb{C}^n; \mathcal{O}^*) = 0,$$ 
> 
> after a refinement of covering if necessary, there exists $h_\alpha \in \mathcal{O}^*(U_\alpha)$ for each $\alpha$ such that $f_\alpha / f_\beta = g_{\alpha\beta} = h_\beta / h_\alpha$. Therefore we obtain an entire function $f = f_\alpha h_\alpha = f_\beta h_\beta$ whose zero set is exactly $V$. 