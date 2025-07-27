---
title: Riemann-Roch theorem
date: 2025-07-27 10:07:00
tags:
	- complex geometry
	- math
mathjax: true
---

We focus on the Riemann-Roch theorem in the study of compact Riemann surface in this post. This will be a comprehensive application of the tools we have developed. 

---

Suppose $M$ is a compact Riemann surface, i.e., a compact $1$-dimensional complex manifold. Recall our discussions about divisors and line bundles. We have associated to each nontrivial meromorphic function $f$ on $M$ a divisor $(f)$, and to each divisor $D$ a line bundle $[D]$. The divisor group $\mathrm{Div}(M)$ on $M$ is naturally identified with $H^0(M; \mathcal{M}^\*_M / \mathcal{O}^\*_M)$, while the Picard group $\mathrm{Pic}(M)$ of line bundles on $M$ is identified with $H^1(M; \mathcal{O}^\*_M)$. The exact seqeunce of sheaves $$0 \to \mathcal{O}^\*_M \to \mathcal{M}^\*_M \to \mathcal{M}^\*_M / \mathcal{O}^\*_M \to 0$$ induces the exct sequence $$H^0(M; \mathcal{M}^\*_M) \xrightarrow{(\cdot)} H^0(M; \mathcal{M}^\*_M / \mathcal{O}^\*_M) \xrightarrow{[\cdot]} H^1(M; \mathcal{O}^\*_M).$$

For a divisor $D$ on $M$, the holomorphic sections of the associated line bundle $[D]$ can be constructed by meromorphic functions on $M$ satifying some properties. Precisely, there is an isomorphism between $$\mathcal{L}(D) = \\\{f \in H^0(M; \mathcal{M}^\*_M) \mid (f) + D \geq 0\\\}$$ and $H^0(M; \mathcal{O}_M([D]))$. In particular, $$\dim \mathcal{L}(D) = \dim H^0(M; \mathcal{O}\_M([D])).$$ Here we consider meromorphic functions $f$ on $M$, however, we can also consider meromorphic differential forms $u$ on $M$. A *meromorphic differential form* $u$ on $M$ is a global meromorphic section of the differential form bundle $\Omega_M = K_M$ on $M$. Since $M$ is $1$-dimensional, $K_M$ is a line bundle, and each nontrivial global meromorphic section $u$ of $K_M$ induces a divisor $[u]$ just as meromorphic functions. Consider $$\mathcal{I}(D) = \\\{u \in H^0(M;\mathcal{M}^*_M(K_M)) \mid (u) - D \geq 0\\\}.$$ In analogy to the way that each $f \in \mathcal{L}(D)$ induces a holomorphic section of $[D]$, each $u \in \mathcal{I}(D)$ induces a holomorphic $[-D]$-valued differential form on $M$, and hence we obtain an isomorphism $$\mathcal{I}(D) \xrightarrow{\sim} H^0(M; \mathcal{O}_M([-D] \otimes K_M)).$$ Recall that by the generalized Dolbeault theorem and the Kodaira-Serre duality, we have $$H^0(M; \mathcal{O}\_M([-D] \otimes K_M)) \cong H^{0,0}(M, [-D] \otimes K_M) \cong (H^{0,1}(M, [D]))^\* \cong (H^1(M; \mathcal{O}\_M([D])))^\*,$$ implying that $$\dim \mathcal{I}(D) = \dim H^0(M; \mathcal{O}\_M([-D] \otimes K_M)) = \dim H^1(M; \mathcal{O}_M([D])).$$

---

Note that as $M$ is $1$-dimensional, the hypersurfaces on $M$ are exactly points. Thus each divisors $D$ on $M$ can be expressed as $$D = n_1 p_1 + \cdots + n_k p_k - m_1 q_1 - \cdots - m_l q_l,$$ where $p_1, \cdots, p_k, q_1, \cdots, q_l$ are distinct points on $M$ and $n_1, \cdots, n_k, m_1, \cdots, m_l$ are positive integers. We then define the **degree** of the divisor to be $$\deg(D) = n_1 + \cdots + n_k - m_1 - \cdots - m_l.$$

**Lemma.** Suppose $D = (f)$ is a divisor defined by a nontrivial meromorphic function $f$ on $M$. Then $\deg(D) = 0$. 

> *Proof:* Consider a finite open cover $\\\{U_\alpha\\\}$ of $M$ such that each $U_\alpha$ is identified with an open subset of $\mathbb{C}$. We can take $V_\alpha \subset U_\alpha$ for each $\alpha$ such that these $V_\alpha$ are disjoint, $\overline{V}\_\alpha$ cover $M$, and there is no zero or pole of $f$ on any $\partial V_\alpha$. By the argument principle for meromorphic functions, we see that the difference between the number of zeros of $f$ on $V_\alpha$ and the number of poles of $f$ on $V_\alpha$, both counted with multiplicities, is the integral of $\partial f / f$ along $\partial V_\alpha$. Thus $$\deg(D) = \sum_\alpha \int_{\partial V_\alpha} \frac{\partial f}{f} = 0,$$ where the last equality holds by the definition of contour integrals. 

Another important concept appeared in the statement of the Riemann-Roch theorem is the **genus** $g$ of a Riemann surface $M$. This is just the genus of a compact surface of real dimension $2$, and by the orientability of $M$, we have the expression of $g$ as $$g = \frac{1}{2} \dim H^1(M; \mathbb{C}) = \frac{1}{2} \dim H^1(M; \underline{\mathbb{C}}),$$ where the first $H^1$ is the de Rham cohomology with complex coefficients, and the second one is the sheaf cohomology of the locally constant sheaf $\underline{\mathbb{C}}$.

Consider any hermitian metric on $M$. As soon as $M$ is a hermitian Riemann surface, $M$ becomes a K&#228;hler manifold. Then by the Hodge decomposition theorem for compact K&#228;hler manifolds, we see that $$g = \frac{1}{2}b_1(M) = \frac{1}{2}(h^{1,0}(M) + h^{0,1}(M)) = h^{0,1}(M).$$ Using the Dolbeault theorem, it follows that $$\dim H^1(M; \mathcal{O}_M) = \dim H^{0,1}(M) = h^{0,1}(M) = g.$$ 

---

The following lemma will be repeatedly used in our discussion.

**Lemma.** Suppose $M$ is a compact Riemann surface, $L$ is a line bundle on $M$ and $D$ is an effective divisor. Then $$\dim H^0(M; \mathcal{O}_M(L \otimes [D])) - \dim H^1(M; \mathcal{O}_M(L \otimes [D])) = \dim H^0(M; \mathcal{O}_M(L)) - \dim H^1(M; \mathcal{O}_M(L)) + \deg(D).$$

> *Proof:* Suppose $D$ is given as $$D = n_1 p_1 + \cdots + n_k p_k, \quad n_j \geq 0.$$ By the identification of $\mathrm{Div}(M)$ with $H^0(M; \mathcal{M}\_M^\* / \mathcal{O}\_M^\*)$, we can take a nontrivial meromorphic section $s_0 \in H^0(M; \mathcal{M}\_M^\*([D]))$ such that $(s_0) = D$. Since $D$ is effective, $s_0$ is indeed holomorphic, and has zeros at each $p_j$ with order $n_j$. 
>
> For each local holomophic section $t \in \mathcal{O}_M(L)(U)$ of $L$, $t \cdot s_0$ gives a holomorphic section of $L \otimes [D]$. If $t \cdot s_0 = 0$, then $t$ is zero on a dense subset of $U$, implying that $t$ is the trivial section of $L$ on $U$. Thus we obtain an injective sheaf morphism $$\mathcal{O}\_M(L) \xrightarrow{\cdot s_0} \mathcal{O}\_M(L \otimes [D]).$$ Put this into an exact sequence of sheaves: $$0 \to \mathcal{O}\_M(L) \to \mathcal{O}\_M(L \otimes [D]) \to \mathcal{Q} \to 0.$$ 
>
> For $x \in M \setminus \\\{p_1, \cdots, p_k\\\}$, $s_0(x)$ is nonzero and hence $$\mathcal{O}\_M(L)\_x \xrightarrow{\cdot s_0(x)} \mathcal{O}\_M(L \otimes [D])\_x$$ is an isomorphism, implying that $\mathcal{Q}\_x = 0$. For $x = p_j$ for some $1 \leq j \leq k$, the image of $\mathcal{O}\_M(L)\_x$ in $\mathcal{O}\_M(L \otimes [D])\_x$ consists of those local sections $s$ such that $x = p_j$ is a zero of $s$ with multiplicity no less than $n_j$. Thus $$\mathcal{Q}\_x \cong \\\{a_0 + a_1 z + \cdots + a_{n_j - 1} z^{n_j - 1} \mid a_0, \cdots, a_{n_j - 1} \in \mathbb{C}\\\}.$$ Therefore it is not hard to see that $$H^1(M; \mathcal{Q}) = 0, \quad \dim H^0(M; \mathcal{Q}) = n_1 + \cdots + n_k = \deg(D).$$ 
>
> We have the long exact sequence of cohomology groups $$0 \to H^0(M; \mathcal{O}\_M(L)) \to H^0(M; \mathcal{O}\_M(L \otimes [D])) \to H^0(M; \mathcal{Q}) \to H^1(M; \mathcal{O}\_M(L)) \to H^1(M; \mathcal{O}\_M(L \otimes [D])) \to 0.$$ The Hodge theorem and the generalized Dolbeault theorem have shown the finiteness of the dimensional of these cohomology groups. Thus $$\dim H^0(M; \mathcal{O}\_M(L)) - \dim H^0(M; \mathcal{O}\_M(L \otimes [D])) + \dim H^0(M; \mathcal{Q}) - \dim H^1(M; \mathcal{O}\_M(L)) + \dim H^1(M; \mathcal{O}\_M(L \otimes [D])) = 0,$$ implying the desired formula. 

**Proposition.** Suppose $M$ is a compact Riemann surface and $L$ is a line bundle on $M$. Then there is a divisor $D$ on $M$ such that $L = [D]$.

> *Proof:* Let $p \in M$ and $n \geq 1$. By the lemma, we have $$\dim H^0(M; \mathcal{O}\_M(L \otimes [np])) - \dim H^1(M; \mathcal{O}\_M(L \otimes [np])) = \dim H^0(M; \mathcal{O}\_M(L)) - \dim H^1(M; \mathcal{O}\_M(L)) + n.$$ For a sufficiently large $n$, we must have $$\dim H^0(M; \mathcal{O}\_M(L \otimes [np])) > 0,$$ i.e., $L \otimes [np]$ has a nontrivial global holomorphic (and hence meromorphic) section. As we have shown before, $L \otimes [np]$ is contained in the image of $\mathrm{Div}(M) \to \mathrm{Pic}(M)$. Suppose $L \otimes [np] = [D']$. Then $L = [D' - np]$, proving our assertion. 

Now we can define the degree of a line bundle on $M$. Suppose $L$ is a line bundle on $M$. Take a divisor $D$ on $M$ such that $[D] = L$. We simply define the **degree** $\deg(L)$ of $L$to be the degree of $D$. However, the well-definedness needs considering. Suppose $D'$ is another divisor on $M$ such that $[D'] = L$. Then there exists a meromorphic function $f$ on $M$ such that $D' - D = (f)$. Hence $$\deg(D') = \deg(D) + \deg((f)) = \deg(D),$$ showing that $\deg(L)$ is actually well-defined. 

**Theorem. (Riemann-Roch theorem).** Suppose $M$ is a compact Riemann surface with genus $g$ and $L$ is a line bundle on $M$. Then $$\dim H^0(M; \mathcal{O}\_M(L)) - \dim H^1(M; \mathcal{O}\_M(L)) = \deg(L) - g + 1.$$

> *Proof:* Take a divisor $D$ on $M$ such that $[D] = L$. Clearly there exist effective divisors $D_1$ and $D_2$ on $M$ such that $D = D_1 - D_2$. By the lemma we have from $[D_1] = (M \times \mathbb{C}) \otimes [D_1]$ that $$\dim H^0(M; \mathcal{O}\_M([D_1])) - \dim H^0(M; \mathcal{O}\_M([D_1])) = \dim H^0(M; \mathcal{O}\_M) - \dim H^1(M; \mathcal{O}\_M) + \deg(D_1),$$ and from $[D_1] = L \otimes [D_2]$ that $$\dim H^0(M; \mathcal{O}\_M([D_1])) - \dim H^0(M; \mathcal{O}\_M([D_1])) = \dim H^0(M; \mathcal{O}\_M(L)) - \dim H^1(M; \mathcal{O}\_M(L)) + \deg(D_2).$$ It follows that $$\dim H^0(M; \mathcal{O}\_M(L)) - \dim H^1(M; \mathcal{O}\_M(L)) = \dim H^0(M; \mathcal{O}\_M) - \dim H^1(M; \mathcal{O}\_M) + \deg(D_1) - \deg(D_2).$$ Since $M$ is a compact complex manifold, we have $$\dim H^0(M; \mathcal{O}\_M) = \dim \mathbb{C} = 1.$$ Note that $\dim H^1(M; \mathcal{O}\_M) = g$ and that $$\deg(D_1) - \deg(D_2) = \deg(D) = \deg(L),$$ we conclude that $$\dim H^0(M; \mathcal{O}\_M(L)) - \dim H^1(M; \mathcal{O}\_M(L)) = 1 - g + \deg(L).$$

Using $\mathcal{L}(D)$ and $\mathcal{I}(D)$, we can express the Riemann-Roch theorem as follows:

**Theorem (Riemann-Roch theorem).** Suppose $M$ is a compact Riemann surface with genus $g$ and $D$ is a divisor on $M$. Then $$\dim \mathcal{L}(D) - \dim \mathcal{I}(D) = \deg(D) - g + 1.$$