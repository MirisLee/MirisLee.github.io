---
title: Hodge theory on compact hermitian manifolds - 5
date: 2025-07-18 12:32:00
tags:
	- complex geometry
	- math
mathjax: true
---

We introduce some applications of the Hodge theory on compact hermitian manifolds in the post, including the isomorphism of $\mathcal{H}^{p,q}$ and $H^{p,q}$ and the Kodaira-Serre duality. 

## Relations of harmonic forms and Dolbeault cohomology

Suppose $M$ is a compact hermitian complex manifold and $E$ is a hermitian holomorphic vector bundle on $M$. Since we have well-defined operator $$\bar{\partial} : A^{p,q}(M,E) \to A^{p,q+1}(M,E)$$ for each $p,q$, the **$E$-valued Dolbeault cohomology** $H^{p,q}(M,E)$ on $M$ can be defined analogously to the ordinary Dolbeault cohomology on $M$. 

**Proposition.** Suppose $M$ is a compact hermitian complex manifold and $E$ is a hermitian holomorphic vector bundle on $M$. Then we have the orthogonal direct sum decompostion $$A(M,E) = \mathcal{H}(M,E) \oplus \bar{\partial}A(M,E) \oplus \bar{\partial}^\*A(M,E).$$

> *Proof:* Let $H$ be the orthogonal projection of $A(M,E)$ to $\mathcal{H}(M,E)$. Then by Hodge theorem (and part of its proof), we see that $I = H + \Delta G$, where $G$ is the Green operator. For each $\omega \in A(M,E)$, there is a decomposition $$\omega = H\omega + \Delta G\omega = H\omega + \bar{\partial}(\bar{\partial}^\* G\omega) + \bar{\partial}^\*(\bar{\partial} G \omega),$$ implying that $$A(M,E) = \mathcal{H}(M,E) + \bar{\partial}A(M,E) + \bar{\partial}^\*A(M,E).$$ Meanwhile, noting that $$\mathcal{H}(M,E) = \mathrm{ker}\\\,\bar{\partial} \cap \mathrm{ker}\\\,\bar{\partial}^\*,$$ we obtain the orthogonal relations of $\mathcal{H}(M,E)$ with the image of $\bar{\partial}$ and $\bar{\partial}^\*$. The images of the two operators are orthogonal since $\bar{\partial}^2 = 0$. 

**Proposition.** Suppose $M$ is a compact hermitian complex manifold and $E$ is a hermitian holomorphic vector bundle on $M$. Then there exists a unique harmonic form in each cohomology class in $H^{p,q}(M,E)$. Such harmonic form is the only element in $H^{p,q}(M,E)$ with the minimal length.

> *Proof:* Consider the cohomology class $[\omega] \in H^{p,q}(M,E)$ represented by $\omega \in A^{p,q}(M,E)$, which satisfies $\bar{\partial}\omega = 0$. By the previous proposition, there exists a unique $\eta \in \mathcal{H}^{p,q}(M)$, together with $\alpha \in A^{p,q-1}(M,E), \beta \in A^{p,q+1}(M,E)$ such that $$\omega = \eta + \bar{\partial}\alpha + \bar{\partial}^\*\beta.$$ We claim that $\eta$ is desired harmonic form. 
>
> First we need $\eta \in [\omega]$, and to show this it suffices to prove $\bar{\partial}^\*\beta = 0$. Note that $$0 = \bar{\partial}\omega = \bar{\partial}\eta + \bar{\partial}^2\alpha + \bar{\partial}\bar{\partial}^\*\beta = \bar{\partial}\bar{\partial}^\*\beta,$$ we have $$\bar{\partial}^\*\beta \in \mathrm{ker}\\\,\bar{\partial} \cap \mathrm{ker}\\\,\bar{\partial}^\* = \mathcal{H}^{p,q}(M,E).$$ The direct sum deecompostion implies that $\bar{\partial}^\*\beta = 0$. 
>
> If there is another harmonic $\eta' \in [\omega]$, then $$\eta - \eta' \in \bar{\partial}A^{p,q-1}(M,E) \cap \mathcal{H}^{p,q}(M,E) = 0,$$ showing the uniqueness of such $\eta$.
>
> For any other $\psi \in [\omega]$, there is $\gamma \in A^{p,q-1}(M,E)$ such that $$\psi = \eta + \bar{\partial}\gamma, \quad \bar{\partial}\gamma \neq 0.$$ It follows that $$\\\|\psi\\\|^2 = \\\|\eta\\\|^2 + \\\|\bar{\partial}\gamma\\\|^2 > \\\|\eta\\\|^2.$$

As harmonic forms are all $\bar{\partial}$-closed, we have a natural homomorphism $$\mathcal{H}^{p,q}(M,E) \to H^{p,q}(M,E).$$

**Corollary.** The above homomorphism is an isomorphism. In particular, $H^{p,q}(M,E)$ is finite dimensional. 

Let $\Omega^p_M(E)$ be the sheaf of $E$-valued holomorphic $p$-forms on $M$. In analogy of the ordinary Dolbeault theorem, we have the canonical isomorphism $$H^q(M; \Omega^p_M(E)) \xrightarrow{\sim} H^{p,q}(M,E) \xrightarrow{\sim} \mathcal{H}^{p,q}(M,E).$$

## Kodaira-Serre duality

The Hodge theory permits us to study Dolbeault cohomology by harmonic forms. Recall that when $M$ is $n$-dimensional, we have the star operator $$\* : A^{p,q}(M,E) \xrightarrow{\sim} A^{n-p,n-q}(M,E^\*).$$ As $\*$ commutes with $\Delta$, there is a induced ismorphism $$\* : \mathcal{H}^{p,q}(M,E) \xrightarrow{\sim} \mathcal{H}^{n-p,n-q}(M,E^\*).$$ Using the isomorphism of $\mathcal{H}^{p,q}$ and $H^{p,q}$, we see that $$\dim H^{p,q}(M,E) = \dim \mathcal{H}^{p,q}(M,E) = \dim \mathcal{H}^{n-p,n-q}(M,E^\*) = \dim H^{n-p,n-q}(M,E^\*).$$ This relation is usually called **Kodaira-Serre duality**. 

There is another approach to the above equality, which actually identify $H^{n-p,n-q}(M,E^\*)$ with the dual of $H^{p,q}(M,E)$. Consider the pairing $$P : A^{p,q}(M,E) \times A^{n-p,n-q}(M,E^\*) \to \mathbb{C}$$ given by $$P(\alpha, \beta) = \int_M \alpha \wedge \beta = (-1)^{p+q}(\alpha, \*\beta), \quad \alpha \in A^{p,q}(M,E), \quad \beta \in A^{n-p,n-q}(M,E^\*).$$ 

We claim that this induces a well-defined pairing on the corresponding cohomology groups. Suppose $\alpha \in A^{p,q}(M,E)$ and $\beta \in A^{n-p,n-q}(M,E^\*)$ are $\bar{\partial}$-closed forms. Then for any $\gamma \in A^{p,q-1}(M,E)$ we have $$\mathrm{d}(\gamma \wedge \beta) = \bar{\partial}(\gamma \wedge \beta) = \bar{\partial}\gamma \wedge \beta,$$ implying that $$\int_{M} (\alpha + \bar{\partial}\gamma) \wedge \beta = \int_M \alpha \wedge \beta.$$ Similarly for any $\psi \in A^{n-p,n-q-1}(M,E^\*)$ it holds that $$\int_M \alpha \wedge (\beta + \bar{\partial}\psi) = \int_M \alpha \wedge \beta.$$ Thus the value of $P(\alpha, \beta)$ only depends on the cohomology class of $\alpha$ and $\beta$, yielding a pairing $$P : H^{p,q}(M,E) \times H^{n-p,n-q}(M,E^\*) \to \mathbb{C}.$$ We see that this pairing is nondegenerate and hence gives a natural isomorphism $$H^{n-p,n-q}(M,E^\*) \xrightarrow{\sim} (H^{p,q}(M,E))^\*.$$ In particular, let $E = M \times \mathbb{C}$, we obtain $$H^{n-p,n-q}(M) \xrightarrow{\sim} (H^{p,q}(M))^\*.$$ 

Another useful form of the Kodaira-Serre duality is obtained by taking $p = 0$. In this case we have $$(H^{0,q}(M,E))^\* \cong H^{n,n-q}(M,E^\*) = H^{0,n-q}(M, E^\* \otimes \wedge^n T^{*1,0}(M)) = H^{0,n-q}(M, E^\* \otimes K_M),$$ and particularly $$\dim H^{0,q}(M,E) = \dim H^{0,n-q}(M,E^\* \otimes K_M).$$ Considering the generalized Dolbeault theorem, we further get the natural isomorphism $$(H^q(M; \mathcal{O}_M(E)))^\* \cong H^{n-q}(M; \mathcal{O}_M(E^\* \otimes K_M)).$$ 

One thing to mention that the Kodaira-Serre duality only needs the condition that $M$ is a compact complex manifold and $E$ is a holomorphic vector bundle on $M$. On the one hand, the pairing $P$ above has nothing to do with the hermitian structure on $M$ and $E$. On the other hand, by considering a partition of unity, we see that $M$ and $E$ can always be equipped with hermitian structures. 