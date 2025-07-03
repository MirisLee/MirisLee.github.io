---
title: Hodge theory on compact hermitian manifolds - 1
date: 2025-07-02 21:33:00
tags:
	- complex geometry
	- math
mathjax: true
---

Hodge theory is an important tool used in the study of geometry and topology. Roughly speaking, Hodge theorem provides us with a unique harmonic form as a representative of each cohomology class, which enables us to use analytic methods to explore the topology of manifolds. Meanwhile, Hodge theory reveals an essential relation between the de Rham cohomology and the Dolbeault cohomology, which is almost indispensible in the further discussion of K&#228;hler manifolds. 

In this post we introduce some operators on a compact hermitian manifold with a hermitian bundle and formulate the Hodge theorem. 

## Inner product structure on the section space

<!-- notations -->

Suppose $M$ is a compact hermitian manifold with hermitian metric $g$ on $T^{1,0}(M)$, and $\pi : E \to M$ is a holomorphic hermitian vector bundle on $M$ with hermitian etric $h$. Recall that we have the holomorphic cotangent bundle and the antiholomorphic cotangent bundle $T^{*1,0}(M)$ and $T^{*0,1}(M)$ of $M$, whose direct sum yields the complexified cotangent bundle $T^\*_\mathbb{C}(M)$. Denote that $$T^{*p,q}(M) = (\wedge^p T^{*1,0}(M)) \wedge (\wedge^q T^{*0,1}(M)).$$ 

The sheaf of the sections of $T^{p,q}(M)$ is denoted by $\mathcal{A}^{p,q}\_M$ and that of the tensor product $T^{*p,q}(M) \otimes E$ is denoted by $\mathcal{A}^{p,q}\_M(E)$. For an open subset $U \subset M$, denote the space of $(p,q)$-forms and $E$-valued $(p,q)$-forms on $U$ by $A^{p,q}(U)$ and $A^{p,q}(U,E)$, i.e., $$A^{p,q}(U) = \mathcal{A}^{p,q}\_M(U), \quad A^{p,q}(U,E) = \mathcal{A}^{p,q}\_M(E)(U).$$ We also consider the direct sum $$A(U,E) = \bigoplus_{p,q} A^{p,q}(U,E).$$ 

<!-- hermitian structure on $T^{*p,q}(M) \otimes E$ -->

As we have hermitian metrics on $T^{1,0}(M)$ and $E$, the bundle $T^{\*p,q}(M) \otimes E$ can also admit a hermitian structure. Specifically, consider local orthonormal frames $\\\{v_1, \cdots, v_n\\\}$ and $\\\{e^1, \cdots, e^r\\\}$ of $T^{1,0}(M)$ and $E$. Suppose the dual frame of them are given by $\\\{\varphi^1, \cdots, \varphi^n\\\}$ and $\\\{e^\*_1, \cdots, e^\*_r\\\}$, respectively. Then we have the local expression of $g$ and $h$ as $$g = \sum\_{j=1}^n \varphi^j \otimes \bar{\varphi}^j, \quad h = \sum\_{k=1}^r e^\*_k \otimes \bar{e}^\*_k.$$ 

The fundamental form associated to the hermitian metric $g$ is $$\omega = \frac{i}{2}\sum_{j=1}^n \varphi^j \wedge \bar{\varphi}^j,$$ and the volumn form is then $$\mathrm{d}V = \frac{\omega^n}{n!} = \left(\frac{i}{2}\right)^n \varphi^1 \wedge \bar{\varphi}^1 \wedge \cdots \wedge \varphi^n \wedge \bar{\varphi}^n.$$

Requiring that $\\\{\varphi^1, \cdots, \varphi^n\\\}$ form a local orthogonal frame of $T^{*1,0}(M)$ and that $|\varphi^j|^2 = 2$ for each $j$, we obtain a hermitian metric locally on $T^{*1,0}(M)$. More generally, to introduce a hermitian structure on $T^{*p,q}(M) \otimes E$, we let $$\left\\\{\varphi^I \wedge \bar{\varphi}^J \otimes e^k \mid |I| = p, |J| = q, 1 \leq k \leq r\right\\\}$$ be a local orthogonal frame on $T^{*p,q}(M) \otimes E$, with $$|\varphi^I \wedge \bar{\varphi}^J \otimes e^k|^2 = 2^{p+q}.$$ Meanwhile, we can also give $T^{\*p,q}(M) \otimes E^\*$ a hermitian structure, with $$\left\\\{\varphi^I \wedge \bar{\varphi}^J \otimes e^\*_k \mid |I| = p, |J| = q, 1 \leq k \leq r\right\\\}$$ a local orthogonal frame and $$|\varphi^I \wedge \bar{\varphi}^J \otimes e^\*_k|^2 = 2^{p+q}.$$

We can verify that these hermitian metrics are independent of the choice of the local orthogonal frame of $T^{1,0}(M)$ and $E$, and hence are well-defined hermitian structure globally.

<!-- the inner product on $A^{p,q}(M,E) -->

In order to pass the inner product at each point of the bundle to the inner product of global sections, we need to consider the integral. Suppose $s_1, s_2$ are two global $E$-valued $(p,q)$-forms on $M$. For each point $x \in M$, the hermitian metric on $T^{*p,q}(M) \otimes E$ gives an inner product $\langle\cdot,\cdot\rangle_x$ on the fiber at $x$. Note that $\langle s_1, s_2 \rangle_x$ is a smooth function in $x$, we can define that $$(s_1, s_2) = \int_M \langle s_1, s_2 \rangle_x \cdot \mathrm{d}V,$$ where $\mathrm{d}V$ is the volumn form on $M$ given by the hermitian metric $g$. It can be verified that this indeed gives an inner product on $A^{p,q}(M,E)$. Since $A(M, E)$ is exactly the direct sum of these $A^{p,q}(M,E)$, we also obtain an inner product $(\cdot,\cdot)$ on $A(M,E)$. The norm on $A(M,E)$ induced by this inner product is denoted by $\\\|\cdot\\\|$. 

---
<!-- the star opertor -->

To discuss further properties of this inner product, the *star operator* $\*$ is introduced. First let us consider $$\* : T^{*p,q}_x(M) \to T^{*n-p,n-q}_x(M)$$ defined by the relation $$\alpha \wedge \*\beta = \langle \alpha, \beta \rangle_x \cdot \mathrm{d}V_x.$$ Since we have the nondegenrate pairing $$\wedge : T^{*p,q}_x(M) \times T^{*n-p,n-q}_x(M) \to T^{*n,n}_x(M) = \mathbb{C} \cdot \mathrm{d}V_x,$$ the operator $\*$ is well-defined. 

We illustrate the local expression of $\*$ in order to show that $\*$ gives a bundle homomorphism $$\* : T^{*p,q}(M) \to T^{*n-p,n-q}(M).$$ Suppose with respect to the local frame $\\\{\varphi^1, \cdots, \varphi^n\\\}$ we can express $\alpha$ as $$\alpha = \sum_{I,J} \alpha_{I\bar{J}} \\\, \varphi^I \wedge \bar{\varphi}^J \in T^{*p,q}_x(M)$$ 

Direct computation yields that $$\*\alpha = (-1)^{n(n-1)/2 + q(n-p)} \\\, 2^{p+q} \left(\frac{i}{2}\right)^n \sum_{I,J} \varepsilon_{I,I'} \\\, \varepsilon_{J,J'} \\\, \bar{\alpha}_{I \bar{J}} \\\, \varphi^{I'} \wedge \bar{\varphi}^{J'},$$ 

where $I'$ and $J'$ are the complements of $I$ and $J$ in $\\\{1, \cdots, n\\\}$ and $\varepsilon_{I,I'}$ is the sign of the permutation $$(1, \cdots, p, p+1, \cdots, n) \mapsto (i_1, \cdots, i_p, i'\_{p+1}, \cdots, i'\_n), \quad I = \\\{i_1 < \cdots < i_p\\\}, \quad I' = \\\{i'\_{p+1} < \cdots < i'\_n\\\},$$ and analogously for $\varepsilon_{J,J'}$. 

This verifies that $\*\alpha$ depends smoothly on $\alpha$, implying that $\*$ yields the desired bundle homomorphism. This further induces a homomorphism $$\* : A^{p,q}(M) \to A^{n-p,n-q}(M).$$ The inner product on $A^{p,q}(M)$ can then be expressed as $$(\alpha, \beta) = \int_M \alpha \wedge \*\beta, \quad \alpha, \beta \in A^{p,q}(M).$$ We can see the property of $\*$ that $$\*\*\alpha = (-1)^{p+q}\alpha, \quad \alpha \in A^{p,q}(M),$$ and that $$(\alpha, \*\beta) = (-1)^{p+q}(\*\alpha, \beta), \quad \alpha \in A^{p,q}(M), \beta \in A^{n-p,n-q}(M).$$

The star operator can also be defined on the tensor bundle $T^{*p,q}(M) \otimes E$. Consider the bundle homomorphism $h^\sharp : E \to E^\*$ given by $$h^\sharp(e) = \langle \cdot, e \rangle_x : E_x \to \mathbb{C}, \quad e \in E_x.$$ We see that this is a bundle isomorphism whose inverse is often denoted by $h^\flat : E^\* \to E$. Since $h$ induces a hermitian metric $h^\*$ on $E^\*$ and $(E^\*)^\*$ is identified with $E$, we also have $(h^\*)^\sharp : E^\* \to E$. It is direct to check that $(h^\*)^\sharp$ is nothing else than $h^\flat$. We define the star operator on $T^{*p,q}(M) \otimes E$ to be $$\* = \* \otimes h^\sharp : T^{*p,q}(M) \otimes E \to T^{*n-p,n-q}(M) \otimes E^\*,$$ and analogously $$\* = \* \otimes h^\flat : T^{*p,q}(M) \otimes E^\* \to T^{*n-p,n-q}(M) \otimes E.$$ These induce homomorphisms $$\* : A^{p,q}(M,E) \to A^{n-p,n-q}(M,E^\*), \quad \* : A^{p,q}(M,E^\*) \to A^{n-p,n-q}(M,E).$$ Using the pairing $$\wedge : A^{p,q}(M,E) \times A^{n-p,n-q}(M,E^\*) \to A^{n,n}(M,E \otimes E^\*) \to A^{n,n}(M),$$ we see that $$(s_1, s_2) = \int_M s_1 \wedge \*s_2$$ also holds for $s_1, s_2 \in A^{p,q}(M,E)$, and the two properties of the star operator on $A^{p,q}(M)$ still hold true here. 

## Statement of the Hodge theorem

<!-- the adjoint operator $\bar{partial}^*$ -->

Recall that $\bar{\partial}$ gives a well-defined operator $$\bar{\partial} : A^{p,q}(M, E) \to A^{p,q+1}(M,E)$$ for each $p$ and $q$, which together gives an operator $$\bar{\partial} : A(M, E) \to A(M, E).$$ As we have an inner product $(\cdot,\cdot)$ on the space $A(M,E)$, the *adjoint* operator of $\bar{\partial}$ is worth considering. Let $\bar{\partial}^\*$ by the operator defined as $$\bar{\partial}^\* = - \* \bar{\partial} \* : A(M,E) \to A(M,E).$$ Note that here $\bar{\partial}$ actually acts on the space $A(M, E^\*)$, and for some $\alpha \in A^{p,q}(M,E)$, we have $$\*\alpha \in A^{n-p,n-q}(M,E^\*), \quad \bar{\partial}\*\alpha \in A^{n-p,n-q+1}(M,E^*),$$ and hence $$\bar{\partial}^\* \alpha = -\* \bar{\partial} \* \alpha \in A^{p,q-1}(M,E).$$

We claim that $\bar{\partial}^\*$ is exactly the adjoint operator of $\bar{\partial}$ with respect to the inner product $(\cdot,\cdot)$. It suffices to verify this on each $A^{p,q}(M,E)$. Suppose $\alpha \in A^{p,q}(M,E)$ and $\beta \in A^{p,q+1}(M,E)$. We have $$(\bar{\partial}\alpha, \beta) = \int_M \bar{\partial}\alpha \wedge \*\beta = \int_M \bar{\partial}(\alpha \wedge \*\beta) - \int_M (-1)^{p+q}\alpha \wedge \bar{\partial} \* \beta.$$ Note that $\alpha \wedge \* \beta \in A^{n,n-1}(M)$, we have $\partial (\alpha \wedge \*\beta) = 0$, implying that $$\int_M\bar{\partial}(\alpha \wedge \*\beta) = \int_M \mathrm{d}(\alpha \wedge \*\beta) = 0,$$ where the last equality holds from the Stokes' formula. As $\bar{\partial}\*\beta \in A^{n-p,n-q}(M,E^\*)$, we have $$\*\*\bar{\partial}\*\beta = (-1)^{2n-p-q}\bar{\partial}\*\beta = (-1)^{p+q} \bar{\partial}\*\beta,$$ implying that $$(\bar{\partial}\alpha, \beta) = -\int_M \alpha \wedge \*(\*\bar{\partial}\*\beta) = (\alpha, \bar{\partial}^\*\beta).$$ This proves our assertion. 

<!-- the Laplace-Beltrami operator $\Delta$ -->

Using $\bar{\partial}$ and $\bar{\partial}^\*$, we can define the **Laplace-Beltrami operator** $$\Delta = \bar{\partial}^\*\bar{\partial} + \bar{\partial}\bar{\partial}^\* : A(M, E) \to A(M, E).$$ This has some properties which are quite clear from its definition. First, $\Delta$ is an operator preserving the type of a form, i.e., for each $p$ and $q$ we have $$\Delta : A^{p,q}(M,E) \to A^{p,q}(M,E).$$ Second, by the adjoint relation of $\bar{\partial}$ and $\bar{\partial}^\*$, we have $$(\Delta\alpha, \beta) = (\bar{\partial}\alpha, \bar{\partial}\beta) + (\bar{\partial}^\*\alpha, \bar{\partial}^\*\beta) = (\alpha, \Delta\beta),$$ showing that $\Delta$ is self-adjoint with respect to $(\cdot,\cdot)$. Moreover, using the above expression we can see that the kernel of $\Delta$ is exactly the intersection of the kernel of $\bar{\partial}$ and that of $\bar{\partial}^\*$. The forms in the kernel of $\Delta$ are called the **harmonic forms**, and the kernel of $\Delta$ is often denoted by $\mathcal{H}(M,E)$. The space of harmonic $E$-valued $(p,q)$-forms are denoted by $\mathcal{H}^{p,q}(M,E)$.

<!-- statement of the Hodge theorem -->

Now we can state the main theorem of the Hodge theory -- the Hodge theorem.

**Theorem (Hodge theorem).** Suppose $M$ is a compact hermitian manifold and $\pi : E \to M$ is a holomorphic hermitian vector bundle on $M$. Then 
1. $\dim \mathcal{H}(M,E) < +\infty$;
2. providing the orthogonal projection $$H : A(M,E) \to \mathcal{H}(M,E),$$ there exists a compact operator $$G : A(M,E) \to A(M,E)$$ called the **Green operator** such that $G\bar{\partial} = \bar{\partial}G$, $G\bar{\partial}^\* = \bar{\partial}^\*G$ and $I = H + G\Delta$, where $I$ is the identity operator.

The proof of the Hodge theorem involves some functional analysis methods and will occupy the following several posts. 