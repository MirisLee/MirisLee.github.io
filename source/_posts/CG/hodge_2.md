---
title: Hodge theory on compact hermitian manifolds - 2
date: 2025-07-04 11:11:00
tags:
	- complex geometry
	- math
mathjax: true
---

In this post, we introduce some basic tools in functional analysis concerning differential operators and equations. The proof of the Hodge theorem will be presented on the basis of three key theorems, which will be proven in the next post.

## Sobolev spaces

<!-- (equivalent) $s$-norms on $A(M,E)$ -->
Recall our assumption that $M$ is a compact hermitian manifold and $E$ is a holomorphic hermitian vector bundle on $M$. The hermitian structure enables us to define an inner product $(\cdot,\cdot)$ on the space $A(M,E)$ of sections, which further induces a norm $\\\|\cdot\\\|$ on $A(M,E)$. 

However, as we are concerned with the *derivatives* of elements in $A(M,E)$, this norm is not satisfactory. The derivatives of sections are closely related to the connections on $E$. Denote the metric connection on $E$ by $\nabla$. Then we define the $s$-norm, where $s \geq 0$, of $E$-valued forms on $M$ by the following formula:

$$\\\|\xi\\\|\_s^2 = \sum_{k=0}^s \\\|\nabla^k\xi\\\|^2 = \sum_{k=0}^s \int_M \langle \nabla^k\xi, \nabla^k\xi \rangle_x \mathrm{d}V, \quad \xi \in A(M,E),$$ 

where $\langle\cdot,\cdot\rangle_x$ is the inner product on the fiber $T^{*p,q}_x(M) \otimes E_x$ and $\mathrm{d}V$ is the volumn form of $M$ induced by the hermitian metric. It is clear that each $\\\|\cdot\\\|_s$ is indeed a norm on $A(M,E)$ and that $\\\|\cdot\\\|_0$ is exactly $\\\|\cdot\\\|$ itself. 

Although this norm has a concise expression and is clearly globally well-defined, it is not so convenient in specific computations. Therefore we also introduce the following equivalent norms to simply our work. 

Suppose $U \subset \mathbb{C}^n = \mathbb{R}^{2n}$ is an open subset. For a smooth function $f$ on $U$ and a multi-index $\nu = (\nu_1, \cdots, \nu_{2n})$, we define $$|\nu| = \nu_1 + \cdots + \nu_{2n}, \quad D^\nu f = \frac{\partial^{|\nu|} f}{(\partial x^1)^{\nu_1} \cdots (\partial x^{2n})^{\nu_{2n}}}.$$ Now consider the compact complex manifold $M$. We may take an open cover $\\\{U_\alpha\\\}\_{\alpha=1}^l$ of $M$ such that on each $U_\alpha$ we have a holomorphic coordinate map $\varphi_\alpha : U_\alpha \to \mathbb{C}^n$ and a holomorphic frame $\\\{e^1, \cdots, e^r\\\}$ of $E$. Suppose $\\\{\eta_\alpha\\\}$ is a smooth partition of unity subordinate to the open cover $\\\{U_\alpha\\\}$. Then for each $\xi$ we can express $\eta_\alpha\xi$ locally as $$\eta_\alpha\xi = \sum_{I,J,k}\xi^\alpha\_{I\bar{J}k}\\\,\mathrm{d}z\_\alpha^I \wedge \mathrm{d}\bar{z}\_\alpha^J \otimes e^k, \quad \alpha = 1, \cdots, l.$$ We see that each $\xi^\alpha_{I\bar{J}k}$ is a smooth function on $U_\alpha$. Since $U_\alpha$ is identified with an open subset of $\mathbb{C}^n$ through $\varphi_\alpha$, we can consider $D^\nu \xi^\alpha_{I\bar{J}k}$ for each $\nu$. Then we define $${\\\|\xi\\\|\_s^\prime}^2= \sum_{|\nu| \leq s} \sum_{\alpha=1}^l \sum_{I,J,k} \int\_{U_\alpha} |D^\nu \xi^\alpha_{I\bar{J}k}|^2 \mathrm{d}\mu,$$ where $\mu$ is the Lebesgue measure on $\mathbb{C}^n = \mathbb{R}^{2n}$. 

By comparing the order of differentiation, it can be verified that the norms $\\\|\cdot\\\|_s$ and $\\\|\cdot\\\|_s^\prime$ are equivalent to each other. 

---

<!-- Sobolev space $H_s(M,E)$ with $s \geq 0$ -->

Note that $A(M,E)$ is not complete with respect to the norm $\\\|\cdot\\\|_s$, it is not a choice to do analysis on $A(M,E)$. Thus we need to consider the completion of $A(M,E)$ with respect to these norms. The completion of $A(M,E)$ with respect to $\\\|\cdot\\\|_s$ is denoted by $H_s(M,E)$, usually called the **Sobolev space**. These Sobolev spaces are actually Hilbert spaces with respect to some inner product. It worth mentioning that the inner product on $H_0(M,E)$ is induced from the inner product $(\cdot,\cdot)$ on $A(M,E)$ and will be denoted by the same notation. 

It is not hard to see that $H_0(M,E)$ consists of those $L^2$ forms of $E$ on $M$. Precisely, an element $\gamma \in H_0(M,E)$ can be written locally as $$\eta_\alpha\gamma = \sum_{I,J,k} \gamma^\alpha_{I\bar{J}k} \\\, \mathrm{d}z\_\alpha^I \wedge \mathrm{d}\bar{z}\_\alpha^J \otimes e^k, \quad \alpha = 1, \cdots, l,$$ where $\gamma^\alpha\_{I\bar{J}k} \in L^2(U_\alpha)$. Using this description of $H_0(M,E)$ and the equivalence of $\\\|\cdot\\\|\_s$ and $\\\|\cdot\\\|\_s^\prime$, we can see that $H_s(M,E)$ can be identified with the subspace of $H_0(M,E)$ consisting of $\gamma$ such that $D^\nu \gamma^\alpha\_{I\bar{J}k} \in L^2(U\_\alpha)$ for all $|\nu| \leq s$. We could also see that for each $s, t \geq 0$, if $\gamma \in H_{s+t}(M,E)$, then $\nabla^t\gamma \in H_s(M,E)$. Meanwhile, if $\nabla^k\gamma \in H_s(M,E)$ holds for each $k \leq t$, then $\gamma \in H_{s+t}(M,E)$. 

<!-- Sobolev space $H_s(M,E)$ with $s < 0$ -->

For the sake of techinal convenience, the Sobolev spaces $H_s(M,E)$ with $s < 0$ are introduced. First let us consider the Sobolev spaces $H_s(U)$ on an open subset $U \subset \mathbb{C}^n = \mathbb{R}^{2n}$. When $s \geq 0$, we define $H_s(U)$ to be given by $$H_s(U) = \left\\\{f \in L^2(U) \mid \int_U |D^\nu f|^2 \mathrm{d}\mu < +\infty, |\nu| \leq s\right\\\}.$$ The norm $\\\|\cdot\\\|_s$ on $H_s(U)$ is defined as $$\\\|f\\\|\_s^2 = \sum\_{|\nu| \leq s} \int_U |D^\nu f|^2 \mathrm{d}\mu.$$ If we let $$A_s(U) = \\\{f \in C^\infty(U) \mid \\\|f\\\|_s < +\infty\\\},$$ then we can see that $H_s(U)$ is exactly the completion of $A_s(U)$ with respect to the norm $\\\|\cdot\\\|\_s$. For each $f \in H_s(U)$, the partial derivatives $D^\nu f$ is defined for any $|\nu| \leq s$, with $D^\nu f \in H\_{s - |\nu|}(U)$. 

If we want to consider the derivative $D^\nu f$ of $f \in H_s(U)$ with $|\nu| > s$, it is necessary to figure out what $H_t(U)$ means for $t < 0$. For $s \geq 0$, we define $H_{-s}(U)$ to be the dual space of $H_s(U)$, i.e., the space of bounded linear functional on $H_s(U)$. The norm on $H_{-s}(U)$ is given by $$\\\|\varphi\\\|\_{-s} = \sup_{0 \neq f \in H_s(U)} \frac{|\varphi(f)|}{\\\|f\\\|\_s}, \quad \varphi \in H_{-s}(U).$$ Since $H_0(U)$ is identified with its dual by $f \mapsto \varphi_f,$ where $$\varphi_f(g) = (g, \bar{f}) = \int_U g \cdot f \\\,\mathrm{d}\mu, \quad g \in H_0(U),$$ this above definition of $H_{-s}(U)$ is suitable for $s = 0$. 

Noting that when $0 \leq s \leq t$, we can view $H_t(U)$ as a subspace of $H_s(U)$ in a natural way. Analogously, we want to cannonically embed $H_{-s}(U)$ into $H_{-t}(U)$. For $\varphi \in H_{-s}(U)$, the corresponding element in $H_{-t}(U)$ is obtained by the restriction of $\varphi$ to $H_t(U)$. Since $$|\varphi(f)| \leq \\\|\varphi\\\|\_{-s} \\\|f\\\|\_s \leq \\\|\varphi\\\|\_{-s} \\\|f\\\|\_t, \quad f \in H\_t(U),$$ $\varphi$ indeed gives an element in $H\_{-t}(U)$. Thus we obtain a sequence of inclusion: $$\cdots H_s(U) \subset \cdots \subset H_2(U) \subset H_1(U) \subset H_0(U) \subset H\_{-1}(U) \subset H\_{-2}(U) \subset \cdots \subset H_{-t}(U) \subset \cdots.$$

---

<!-- derivatives in the weak sense -->
Denote the space of smooth functions on $U \subset \mathbb{C}^n$ with compact support by $C^\infty_c(U)$. For each $f \in C^\infty(U)$ and $g \in C^\infty_c(U)$, the integral by parts yields that $$(D^\nu f, g) = \int_U D^\nu f \cdot \bar{g} \\\, \mathrm{d}\mu = (-1)^{|\nu|}\int_U f \cdot \overline{D^\nu g} \\\, \mathrm{d}\mu = (-1)^{|\nu|}(f, D^\nu g).$$ This inspires us to generalized the concept of derivatives in the following way. Suppose $f \in H_s(U)$ and $g \in H_{s-|\nu|}(U)$. We write $D^\alpha f = g$ if for each $h \in C^\infty_c(U)$, we have $$[f, D^\alpha h] = (-1)^{|\nu|} [g, h],$$ where the pairing $$[\cdot,\cdot] : H_t(U) \times C^\infty_c(U) \to \mathbb{C}$$ is given by the inner product $(\cdot,\cdot)$ on $H_0(U)$ if $t \geq 0$, and $[\varphi, h] = \varphi(\bar{h})$ if $t < 0$. 

**Propostion.** Suppose $U \subset \mathbb{C}^n = \mathbb{R}^{2n}$ is an open subset. Then for each integer $s$ and multi-index $\nu = (\nu_1, \cdots, \nu_{2n})$ with $|\nu| = t$, $D^\nu : H_s(U) \to H_{s-t}(U)$ defines a bounded operator with $\\\|D^\nu\\\| \leq 1$. 

> *Proof:* The assertion is direct if $s \geq t \geq 0$ as we have $\\\|D^\nu f\\\|_{s-t} \leq \\\|f\\\|_s$ for $f \in A_s(U)$ and $A_s(U)$ is dense in $H_s(U)$. 
>
> Then suppose that $s \geq 0$ and $t > s$. We need to find for each $f \in H_s(U)$ some $g \in H_{s-t}(U)$ such that $D^\nu f = g$. Consider the linear funcctional $g : C^\infty_c(U) \to \mathbb{C}$ given by $g(h) = (-1)^t (f, D^\nu \bar{h})$. Since $t > s$, we can find a multi-index $\lambda = (\lambda_1, \cdots, \lambda_{2n})$ such that $0 \leq \lambda_j \leq \nu_j$ for each $j$ and $|\lambda| = s$. Then for each $h \in C^\infty_c(U)$, we have $$(f, D^\nu \bar{h}) = (-1)^s (D^\lambda f, D^{\nu - \lambda} \bar{h}),$$ and hence $$|g(h)| \leq \\\|D^\lambda f\\\|\_0 \\\|D^{\nu - \lambda} \bar{h}\\\|\_0 \leq \\\|f\\\|\_s \\\|h\\\|\_{t-s}.$$ Thus $g$ defines a bounded linear functional on $C^\infty_c(U) \subset H\_{t-s}(U)$. By Hahn-Banach theorem, $g$ can be extended to a bounded linear functional on $H\_{t-s}(U)$ without changing its norm, i.e., we obtain $g \in H\_{s-t}(U)$ with $D^\nu f = g$ and $\\\|g\\\|\_{s-t} \leq \\\|f\\\|_s$.
>
> Now we consider the case $s < 0$. Similarly for $f \in H_s(U)$ define $g : C^\infty_c(U) \to \mathbb{C}$ by $g(h) = (-1)^t f(D^\nu h)$. We see that $$|g(h)| \leq \\\|f\\\|\_s \\\|D^\nu h\\\|\_{-s} \leq \\\|f\\\|\_s \\\|h\\\|\_{t-s}.$$ The same argument as the previous case is valid and hence the conclusion is shown.

The above constructions can be done for $H_s(M,E)$ in a corresponding way. The space $H_{-s}(M,E)$ with $s \geq 0$ is defined to be the dual space of $H_s(M,E)$, and $H_0(M,E)$ defined in this way agrees with the original definition. The seqeuence of inclusion also holds for $H_s(M,E)$, that is, $H_s(M,E) \subset H_{s-1}(M,E)$ for any integer $s$. We see that $\nabla$, $\bar{\partial}$ and $\bar{\partial}^\*$ give operators from $H_s(M,E)$ to $H_{s-1}(M,E)$, while $\Delta$ yields an operator from $H_s(M,E)$ to $H_{s-2}(M,E)$. 


## Key theorems

<!-- statement of three theorems -->
Now we can state our three key theorems before the proof of the Hodge theorem. From now on, we also assume that $M$ is a compact hermitia manifold and $E$ is a holomorphic hermitian vector bundle on $M$.

**Theorem A (G&#229;rding's inequality).** There exist positive constants $c_1, c_2 > 0$ such that for each $\xi \in A(M, E)$, we have $$(\Delta\xi, \xi) \geq c_1 \\\|\xi\\\|_1^2 - c_2 \\\|\xi\\\|_0^2.$$

**Theorem B.** If $\xi \in H_0(M,E)$ satisfies that $(\bar{\partial} + \bar{\partial}^\*)\xi \in A(M,E)$, then $\xi \in A(M,E)$. 

**Theorem C.** Suppose $\\\{\xi_n\\\}$ is a sequence in $A(M,E)$ such that $\\\|\xi_n\\\|\_1$ is bounded. Then there exists a subsequence $\\\{\xi\_{n_k}\\\}$ of $\\\{\xi_n\\\}$ which is a Cauchy sequence with respect to $\\\|\cdot\\\|_0$, i.e., converges in $H_0(M,E)$. 

<!-- proof of the Hodge theorem -->
The proof of these theorems will not be given in this post. Instead, we will apply them in the proof of the Hodge theorem. 

The first assertion of the Hodge theorem follows from *Theorem A* and *Theorem C*.

> *Proof of the first assertion of the Hodge theorem:* Assume that $\mathcal{H}(M,E)$ is infinite dimensional. Then we can take a countable orthonormal list $\\\{\xi_n\\\}$ of elements in $\mathcal{H}(M,E)$, with respect to the inner product $(\cdot,\cdot)$ on $A(M,E) \subset H_0(M,E)$. By *Theorem A* we obtain $$\\\|\xi_n\\\|_1^2 \leq c_1^{-1}((\Delta\xi_n,\xi_n) + c_2 \\\|\xi_n\\\|_0^2) = c_1^{-1}c_2,$$ showing the boundedness of $\\\{\xi_n\\\}$ with respect to $\\\|\cdot\\\|_1$. Thus *Theorem C* implies that $\\\{\xi_n\\\}$ contains a subsequence that is a Cauchy sequence with respect to $\\\|\cdot\\\|_0$. However, the orthonormal property of $\\\{\xi_n\\\}$ suggests that $\\\|\xi_m - \xi_n\\\|_0 = \sqrt{2}$ for any $m \ne n$, which yields a contradiction. 

As the Hodge theorem is concerned with $\Delta$ instead of $\bar{\partial} + \bar{\partial}^\*$, we need a regularity lemma for $\Delta$ similar to *Theorem B*. 

**Lemma.** If $\xi \in H_1(M,E)$ satisfies that $\Delta\xi \in A(M,E)$, then $\xi \in A(M,E)$. 
> *Proof:* As $\xi \in H_1(M,E)$, we have $\zeta = (\bar{\partial} + \bar{\partial}^\*)\xi \in H_0(M,E)$. Note that $\bar{\partial}^2 = 0$, it is clear that $(\bar{\partial}^\*)^2 = 0$, and hence $$(\bar{\partial} + \bar{\partial}^\*)^2 = \bar{\partial}\bar{\partial}^\* + \bar{\partial}^\*\bar{\partial} = \Delta.$$ Therefore $$(\bar{\partial} + \bar{\partial}^\*)\zeta = \Delta\xi \in A(M,E),$$ which implies $\zeta \in A(M,E)$ by *Theorem B*. This is exactly $(\bar{\partial} + \bar{\partial}^\*)\xi \in A(M,E)$, which again by *Theorem B* suggests that $\xi \in A(M,E)$. 

Write $\mathcal{H}$ instead of $\mathcal{H}(M,E)$ for short. Denote the orthogonal complement of $\mathcal{H}$ in $A(M,E)$ by $\mathcal{H}^\perp$. As $\mathcal{H}$ is finite dimensional, we have the direct sum decomposition $A(M,E) = \mathcal{H} \oplus \mathcal{H}^\perp$. 

**Lemma.** There exists a positive constant $c_0 > 0$ such that for each $\xi \in \mathcal{H}^\perp$, we have $\\\|\xi\\\|_1^2 \leq c_0(\Delta\xi,\xi)$. 

> *Proof:* Assume that the assertion is not true. Then there exists a sequence $\\\{\xi_n\\\}$ in $\mathcal{H}^\perp$ such that $\\\|\xi_n\\\|_1 = 1$ for each $n$ and $(\Delta\xi_n,\xi_n) \to 0$. By *Theorem C*, passing to a subsequence if necessary, we may assume that $\\\{\xi_n\\\}$ converges to $\xi \in H_0(M,E)$ with respect to $\\\|\cdot\\\|_0$. Note that $$\\\|(\bar{\partial} + \bar{\partial}^\*) \xi_n\\\|_0 = (\Delta \xi_n, \xi_n) \to 0,$$ we have 
> 
> $$(\xi, (\bar{\partial} + \bar{\partial}^\*)\gamma) = \lim_{n \to \infty} (\xi_n, (\bar{\partial} + \bar{\partial}^\*)\gamma) = \lim_{n \to \infty} ((\bar{\partial} + \bar{\partial}^\*)\xi_n, \gamma) = 0, \quad \gamma \in A(M,E).$$ 
>
> This exactly means that $(\bar{\partial} + \bar{\partial}^\*)\xi$ is zero as an element in $H_{-1}(M,E)$. Clearly the zero functional belongs to $A(M,E)$, and then it follows from *Theorem B* that $\xi \in A(M,E)$. 
> 
> On the one hand, as $\mathcal{H}^\perp$ is a closed subspace of $A(M,E)$ with respect to the norm $\\\|\cdot\\\|_0$, we have $\xi \in \mathcal{H}^\perp$. On the other hand, we have $$\Delta\xi = (\bar{\partial} + \bar{\partial}^\*)^2\xi = 0,$$ showing that $\xi \in \mathcal{H}$. Thus $\xi = 0$, and hence $\\\|\xi_n\\\|_0 \to 0$. However, *Theorem A* yields that $$0 < c_1 = c_1 \\\|\xi_n\\\|_1^2 \leq (\Delta\xi_n, \xi_n) + c_2\\\|\xi_n\\\|_0^2 \to 0,$$ a contradiction. 

Noting that $$(\Delta\xi,\xi) = \\\|\bar{\partial}\xi\\\|_0 + \\\|\bar{\partial}^\*\xi\\\|_0,$$ and that $\bar{\partial}$ and $\bar{\partial}^\*$ are both differential operators of order $1$, we see that $(\Delta\xi,\xi)$ can be bounded by some constant multiple of $\\\|\xi\\\|\_1^2$ for $\xi \in \mathcal{H}^\perp$. Thus if we let $$\\\|\xi\\\|\_\Delta^2 = (\Delta\xi, \xi), \quad \xi \in \mathcal{H}^\perp,$$ then $\\\|\cdot\\\|\_\Delta$ and $\\\|\cdot\\\|\_1$ are equivlent norms on $\mathcal{H}^\perp$. 

**Lemma.** The image of $\Delta$ is contained in $\mathcal{H}^\perp$, and the restriction of $\Delta$ to $\mathcal{H}^\perp$ gives a bijective operator $\Delta : \mathcal{H}^\perp \to \mathcal{H}^\perp$.
> *Proof:* For each $\xi \in A(M,E)$ and $\zeta \in \mathcal{H}$, we have $$(\Delta\xi, \zeta) = (\xi, \Delta\zeta) = 0,$$ implying that $\Delta\xi \in \mathcal{H}^\perp$. If there is some $\xi \in \mathcal{H}^\perp$ such that $\Delta\xi = 0$, then $\xi \in \mathcal{H}$ and hence $\xi = 0$, showing the injectivity of $\Delta : \mathcal{H}^\perp \to \mathcal{H}^\perp$. 
>
> Now we turn to the surjectivity. Fix a $\xi \in \mathcal{H}^\perp$ and we have to find some $\gamma \in \mathcal{H}^\perp$ such that $\Delta\gamma = \xi$. Let $B$ be the closure of $\mathcal{H}^\perp$ in $H_1(M,E)$ with respect to $\\\|\cdot\\\|_1$. Then the regularity lemma for $\Delta$ implies that it suffices to show that there exists $\gamma \in B$ such that $\Delta\gamma = \xi$ in the sense that $(\gamma, \Delta\varphi) = (\xi, \varphi)$ for any $\varphi \in A(M,E)$. 
>
> Define an inner product $(\cdot,\cdot)\_\Delta$ on $\mathcal{H}^\perp$ by $$(\xi, \zeta)\_\Delta = (\Delta\xi, \zeta) = (\xi, D\zeta), \quad \xi, \zeta \in A(M,E).$$ Then the norm induced by $(\cdot,\cdot)\_\Delta$ is exactly $\\\|\cdot\\\|\_\Delta$, which is equivalent to $\\\|\cdot\\\|_1$ on $\mathcal{H}^\perp$. As $B$ is the completion of $\mathcal{H}^\perp$ with respect to $\\\|\cdot\\\|\_1$, the inner product $(\cdot,\cdot)\_\Delta$ naturally extends to $B$. Consider the linear functional $\Phi$ on $\mathcal{H}^\perp$ given by $$\Phi(\varphi) = (\varphi, \xi), \quad \varphi \in \mathcal{H}^\perp.$$ Since $$|\Phi(\varphi)| \leq \\\|\varphi\\\|_0 \\\, \\\|\xi\\\|_0 \leq \\\|\xi\\\|_0 \\\, \\\|\varphi\\\|\_1 \leq \sqrt{c_0} \\\|\xi\\\|\_0 \\\|\varphi\\\|\_\Delta,$$ $\Phi$ defines a bounded linear functional on $\mathcal{H}^\perp$ with respect to $\\\|\cdot\\\|\_\Delta$. 
> 
> Hahn-Banach theorem implies that $\Phi$ extends to a linear functional $B$ with the same operator norm, and then the Riesz representation theorem yields $\gamma \in B$ such that $\Phi(\varphi) = (\varphi, \gamma)\_\Delta$ for each $\varphi \in B$. In particular, we have $$(\gamma, \Delta\varphi) = (\gamma, \varphi)\_\Delta = \overline{\Phi(\varphi)} = (\xi, \varphi), \quad \varphi \in \mathcal{H}^\perp.$$ Meanwhile, since $\xi \in \mathcal{H}^\perp$, we have $$(\gamma, \Delta\psi) = (\xi, \psi) = 0, \quad \psi \in \mathcal{H}.$$ Together we obtain the desired relation between $\gamma$ and $\xi$, and hence the assertion is proven.

Now we can prove the second assertion of the Hodge theorem.

> *Proof of the second assertion of the Hodge theorem:* Define $G : A(M, E) \to A(M, E)$ by $$G|\_\mathcal{H} = 0, \quad G|\_{\mathcal{H}^\perp} = \left(\Delta|_{\mathcal{H}^\perp}\right)^{-1}.$$ 
>
> First we show that $G$ is a compact operator. Suppose $\\\{\xi_n\\\}$ is a sequence in $A(M,E)$ with $\\\|\xi_n\\\|\_0 \leq 1$ for each $n$. We need to show that there is a subsequence $\\\{\xi_{n_k}\\\}$ of $\\\{\xi_n\\\}$ such that $\\\{G\xi_{n_k}\\\}$ is a Cauchy sequence with respect to $\\\|\cdot\\\|\_0$. By *Theorem C*, it suffices to show that $\\\{G\xi_n\\\}$ is bounded with respect to $\\\|\cdot\\\|\_1$. 
>
> For each $\varphi \in \mathcal{H}^\perp$, we have $$\\\|\varphi\\\|_1^2 \leq c_0(\Delta\varphi,\varphi) \leq c_0 \\\|\Delta\varphi\\\|_0 \\\, \\\|\varphi\\\|_0 \leq c_0 \\\|\Delta\varphi\\\|_0 \\\, \\\|\varphi\\\|_1,$$ implying that $$\\\|\varphi\\\|_1 \leq c_0 \\\|\Delta\varphi\\\|_0.$$ Suppose $\xi_n = \psi_n + \varphi_n$ with $\psi_n \in \mathcal{H}$ and $\varphi_n \in \mathcal{H}^\perp$ for each $n$. Then $$\\\|G\xi_n\\\|_1 = \\\|G\varphi_n\\\|_1 \leq c_0 \\\|\Delta G\varphi_n\\\|_0 = c_0 \\\|\varphi_n\\\|_0 \leq c_0 \\\|\xi_n\\\|_0 \leq c_0,$$ showing the boundedness of $\\\{G\xi_n\\\}$ in $H_1(M,E)$. 
>
> Next we show the commutatvity of $G$ with $\bar{\partial}$ and $\bar{\partial}^\*$. Note that $$\bar{\partial}\Delta = \bar{\partial}\bar{\partial}^\*\bar{\partial} = \Delta\bar{\partial}, \quad \bar{\partial}^\*\Delta = \bar{\partial}^\*\bar{\partial}\bar{\partial}^\* = \Delta\bar{\partial}^\*,$$ and the image of $\bar{\partial}$ and $\bar{\partial}^\*$ are both contained in $\mathcal{H}^\perp$.  For $\varphi \in \mathcal{H}^\perp$, there exists $\gamma \in \mathcal{H}^\perp$ such that $\varphi = \Delta\gamma$. Then $$\bar{\partial}G\varphi = \bar{\partial}G\Delta\gamma = \bar{\partial}\gamma = G\Delta\bar{\partial}\gamma = G\bar{\partial}\Delta\gamma = G\bar{\partial}\varphi,$$ $$\bar{\partial}^\*G\varphi = \bar{\partial}^\*G\Delta\gamma = \bar{\partial}^\*\gamma = G\Delta\bar{\partial}^\*\gamma = G\bar{\partial}^\*\Delta\gamma = G\bar{\partial}^\*\varphi.$$ For $\psi \in \mathcal{H}$, we have $\bar{\partial}\psi = 0$ and $\bar{\partial}^\*\psi = 0$, implying that $$\bar{\partial}G\psi = G\bar{\partial}\psi = \bar{\partial}^\*G\psi = G\bar{\partial}^\*\psi = 0.$$ Together we see that $$\bar{\partial}G = G\bar{\partial}, \quad \bar{\partial}^\*G = G\bar{\partial}^\*.$$
>
> Last we show that $I = H + G\Delta$. For each $\xi \in A(M,E)$ we have $\xi - H\xi \in \mathcal{H}^\perp$, showing that $$\xi = H\xi + (\xi - H\xi) = H\xi + G\Delta(\xi - H\xi) = H\xi + G\Delta\xi,$$ which directly prove our assertion. 