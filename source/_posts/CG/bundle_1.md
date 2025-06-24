---
title: Holomorphic vector bundles - 1
date: 2025-06-24 14:32:00
tags:
	- complex geometry
	- math
mathjax: true
---

Holomorphic vector bundles are quite essential objects in the study of the geometry of a complex manifold. On one hand, using holomorphic vector bundles, we can consider the analogy of Riemannian geometry in the complex case. On the other hand, the study of vector bundles leads to the concept of divisors, which are frequently considered in algebraic geometry as well.

## Definitons and constructions

The definition of a holomorphic vector bundle is analogous to the definition of a smooth vector bundle. Suppose $M$ is a complex manifold. A **holomorphic vector bundle** $E$ (of rank $r$) on $M$ is a complex manifold $E$ together with a holomorphic map $\pi : E \to M$ satisfiying that
+ each **fiber** $E_x = \pi^{-1}(x)$ where $x \in M$ is an $r$-dimenional complex vector space;
+ for each $x_0 \in M$, there is an open neighborhood $U$ of $x_0$ in $M$ together with a holomorphic homeomorphism $\varphi_U : \pi^{-1}(U) \to U \times \mathbb{C}^r$ such that $E_x$ is mapped linearly isomorphically onto $x \times \mathbb{C}^r$. 
A holomorphic vector bundle of rank $1$ is usually called a **holomorphic line bundle**.

Suppose $E$ and $F$ are holomorphic vector bundles on $M$. Then a *homomorphism* from $E$ to $F$ is a holomorphic map $f : E \to F$ such that $f(E_x) \subset F_x$ for each $x \in M$ and that $f_x : E_x \to F_x$ is linear with rank independent of $x$. If $f_x$ is linear isomorphism for each $x$, then we say $f$ is an *isomorphism*, and $E$ and $F$ are isomorphic. 

Note that if $U$ and $V$ are open subsets in $M$ with noempty intersection and trivializations $$\varphi_U : \pi^{-1}(U) \to U \times \mathbb{C}^r, \quad \varphi_V : \pi^{-1}(V) \to V \times \mathbb{C}^r,$$ then we have a holomorphic map $$\psi_{UV} : U \cap V \to \mathrm{GL}_r(\mathbb{C})$$ given by $$\psi_{UV}(x) = (\varphi_U \circ \varphi_V^{-1})|_{x \times \mathbb{C}^r}.$$ These $\psi_{UV}$ are called *transitions functions* of $E$. The transition functions of $E$ necessarily satisfy the identities $$\psi_{UV}(x) \cdot \psi_{VU}(x) = I, \quad x \in U \cap V,$$ $$\psi_{UV}(x) \cdot \psi_{VW}(x) \cdot \psi_{WU}(x) = I, \quad x \in U \cap V \cap W.$$ 

Conversely, given an open cover $U_\alpha$ of $M$ and holomorphic maps $$\psi_{\alpha\beta} : U_\alpha \cap U_\beta \to \mathrm{GL}_r(\mathbb{C})$$ satisfying the above identities, we may consider the complex manifold $$E = \frac{\coprod_\alpha U_\alpha \times \mathbb{C}^r}{(x, v) (\in U_\beta \times \mathbb{C}^r) \sim (x, \psi_{\alpha\beta}(x)v) (\in U_\alpha \times \mathbb{C}^r)},$$ which has the structure of a holomorphic vector bundle on $M$ such that $\psi_{\alpha\beta}$ are the transition functions. This holomorphic vector bundle is unique up to an isomorphism. 

Suppose $E$ and $F$ are holomorphic vector bundles of rank $r$ and $s$ on $M$ with transition functions given by $\psi_{\alpha\beta}$ and $\psi'_{\alpha\beta}$. Using the description of a holomorphic vector bundle by transition functions, we have the following constructions.
+ The *direct sum* $E \oplus F$ is given by transition functions $$\phi_{\alpha\beta} = \begin{pmatrix} \psi_{\alpha\beta} & \\\\ & \psi'_{\alpha\beta} \end{pmatrix} \in \mathrm{GL}_{r+s}(\mathbb{C}).$$ The fiber $(E \oplus F)_x$ is canonically isomorphic to $E_x \oplus F_x$.
+ The *tensor product* $E \otimes F$ is given by transition functions $$\phi_{\alpha\beta} = \psi_{\alpha\beta} \otimes \psi'_{\alpha\beta} \in \mathrm{GL}_{rs}(\mathbb{C}).$$ The fiber $(E \otimes F)_x$ is canonically isomorphic to $E_x \otimes F_x$.
+ The *dual bundle* $E^*$ is given by transition functions $$\phi_{\alpha\beta} = (\psi_{\alpha\beta}^{-1})^\mathrm{T} \in \mathrm{GL}_r(\mathbb{C}).$$ The fiber $(E^*)_x is canonically isomorphic to $(E_x)^*$. Note that $E^{**}$ is isomorphic to $E$ naturally. 
+ The *exterior product* $\wedge^k E$ is given by transition functions $$\phi_{\alpha\beta} = \wedge^k \psi_{\alpha\beta} \in \mathrm{GL}_d(\mathbb{C}), \quad d = \binom{r}{k}.$$ We also have the canonical isomorphism of fibers $(\wedge^k E)_x = \wedge^k E_x$. In particular, $\det(E) = \wedge^r E$ is the line bundle given by transition functions $$\phi_{\alpha\beta} = \det(\psi_{\alpha\beta}) \in \mathbb{C}^*,$$ called the *determinant line bundle* of $E$.
+ Suppose for each $x \in U_\alpha \cap U_\beta$ the matrix $\psi'_{\alpha\beta}$ can be written as $$\psi'_{\alpha\beta} = \begin{pmatrix} \psi_{\alpha\beta} & * \\\\ & \phi_{\alpha\beta} \end{pmatrix},$$ then $E$ is naturally a *holomorphic subbundle* of $F$. The *quotient bundle* $F/E$ is then given by the transition functions $\phi_{\alpha\beta} \in \mathrm{GL}_{s-r}(\mathbb{C})$. 

Suppose $f : E \to F$ is a vector bundle homomorpism, then there exist holomorphic subbundles $\mathrm{ker}(f) \subset E$ and $\mathrm{im}(f) \subset F$ such that we have the canonical isomorphism of fibers $$(\mathrm{ker}(f))_x = \mathrm{ker}(f_x), \quad (\mathrm{im}(f))_x = \mathrm{im}(f_x).$$ These are called the *kernel bundle* and *image bundle* of $f$. We can also define the *cokernel bundle* of $f$, which is exactly the quotient bundle $$\mathrm{coker}(f) = F / \mathrm{im}(f).$$ Using these definitions, we may consider the exact sequences of vector bundles in a natural way.

Suppose $g : N \to M$ is a holomorphic map between complex manifolds and $E$ is a holomorphic vector bundle on $M$ with transition function $\psi_{\alpha\beta}$. The *pullback bundle* $g^*E$ of $E$ along $g$ is the holomorphic vector bundle on $N$ given by transition functions $\psi_{\alpha\beta} \circ g$. For each $y \in N$ there is a canonical isomorphism $(g^*E)_y = E_{g(y)}$. If $N$ is a submanifold of $M and $g$ is the inclusion, then we call $E|_N = g^*E$ the *restriction* of $E$ on $N$. 

For a holomorphic vector bundle $\pi : E \to M$, we define a **holomorphic section** of $E$ on an open subset $U \subset M$ to be a holomorphic map $s : U \to E$ such that $\pi \circ s$ is identity on $U$, i.e., $s(x) \in E_x$ for each $x \in E$. The collection of all holomorphic sections of $E$ on $U$ is denoted by $\Gamma(U, E)$. The assignment $U \mapsto \Gamma(U, E)$ gives a sheaf on $M$, denoted by $\mathcal{O}_M(E)$. We see that $\mathcal{O}_M(E)$ is naturally a $\mathcal{O}_M$-module. 

## Tangent bundles and related bundles

Suppose $M$ is an $n$-dimensional complex manifold. From its complex manifold structure, we may construct some holomorphic vector bundles on $M$ which are not trivial in general. 

Viewing $M$ as an $2n$-dimensional smooth manifold, we can consider its tangent bundle $T(M)$ and its complexification $T_\mathbb{C}(M)$. Note that we have the canonical isomorphism $$(T_\mathbb{C}(M))_x = T_{\mathbb{C},x}(M) = T^{1,0}_x(M) \oplus T^{0,1}_x(M).$$ Then we have smooth subbundles of $T_\mathbb{C}(M)$ given by $$T^{0,1}(M) = \bigcup_{x \in M} T^{0,1}_x(M), \quad T^{0,1}(M) = \bigcup_{x \in M} T^{0,1}_x(M).$$ The bundle $T^{1,0}(M)$ is called the **holomorphic tangent bundle** of $M$ and $T^{0,1}(M)$ is called the **antiholomorphic tangent bundle** of $M$.

We claim that the holomorphic tangent bundle $T^{1,0}(M)$ is actually a holomorphic vector bundle on $M$. Consider a coordinate covering $(U_\alpha, \varphi_\alpha)$ of $M$. The transition functions of $T^{1,0}M$ with respect to the trivializations induced by the coordinate maps $\varphi_\alpha$ are given by $$\psi_{\alpha\beta}(z) = J(\varphi_\alpha \cdot \varphi_\beta^{-1})(\varphi_\beta(z)), \quad z \in U_\alpha \cap U_\beta.$$ These $\psi_{\alpha\beta}$ are holomorphic, and hence $T^{1,0}(M)$ is a holomorphic vector bundle. We may also write $\mathcal{T}_M$ for the holomorphic tangent bundle of $M$ to specift that it is a holomorphic vector bundle.

Similarly we can define the **holomorphic cotangent bundle** $T^{*1,0}(M)$ and the **antiholomorphic cotangent bundle** $T^{*0,1}(M)$ on $M$, and $T^{*1,0}(M)$ is a holomorphic vector bundle, also denoted by $\Omega_M$. Note that $\Omega_M$ is the dual bundle of $\mathcal{T}_M$. 

Using $\Omega_M$, we can defined the bundle of holomorphic $p$-forms $\Omega^p_M = \wedge^p \Omega_M$ on $M$. In particular, $K_M = \det(\Omega_M) = \Omega^n_M$ is called the **canonical bundle** of $M$. We can see that the transition functions of $K_M$ is given by $$\phi_{\alpha\beta}(z) = \det((\psi_{\alpha\beta}(z)^{-1})^\mathrm{T}) = (\det J(\varphi_\alpha \circ \varphi_\beta^{-1})(\varphi_\beta(z)))^{-1} \in \mathbb{C}^*.$$

Analogously to the construction of $(p,q)$-forms, we may also construct the bundle of $(p,q)$-forms on $M$ given as $$T^{*p,q}(M) = (\wedge^p T^{*1,0}(M)) \wedge (\wedge^q T^{*0,1}(M)).$$ The smooth sections of $T^{*p,q}(M)$ are exactly the $(p,q)$-forms on $M$. 

Now suppose $N$ is a complex submanifold of $M$. 