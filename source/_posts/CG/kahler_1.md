---
title: K&#228;hler manifolds - 1
date: 2025-07-21 15:35:00
tags:
	- complex geometry
	- math
mathjax: true
---

For a hermitian complex manifold, there is a unique complex connection on the holomorphic tangent bundle compatible with the hermitian metric. Meaanwhile, as a Riemannian manifold, there is a unique torsion-free connection on the real tangent bundle compatible with the induced Riemannian metric. The notion of **K&#228;hler manifolds** then arises from the comparison of these two connections. 

## K&#228;hler condition

<!-- torsion-free complex connection -->
Suppose $M$ is a complex manifold and $D$ is a complex connection on the holomorphic tangent bundle $T^{1,0}(M)$. For a local holomorphic coordinates $z^1, \cdots, z^n$ of $M$, we can express $D$ locally as $$D\left(\frac{\partial}{\partial z^j}\right) = \sum_{k=1}^n \omega^k_j \otimes \frac{\partial}{\partial z^k} = \sum_{k,l=1}^n \Gamma^k_{jl} \\\, \mathrm{d}z^l \otimes \frac{\partial}{\partial z^k}, \quad j = 1, \cdots, n.$$ We call $D$ a **torsion-free** complex connection if for any local coordinates we have $$\Gamma^k_{jl} = \Gamma^k_{lj}$$ holds for any $j$, $k$ and $l$. It can be verified that this is independent of the choice of coordinates by the transformation formula for the connection matrix $(\omega^k_j)$. 

Now specify to the case when $M$ admits a hermitian metric $h$. We call the hermitian manifold $M$ a **K&#228;hler manifold** if the associated metric connection $D$ is a torsion-free connection on $T^{1,0}(M)$. The metric $g$ is then called the **K&#228;hler metric** on $M$ and the associated fundamental form $\omega$ of $h$ is called the **K&#228;hler form** on $M$. 

<!-- equivalence between torsion-free and $\omega$ closed -->

**Proposition.** Suppose $M$ is a complex manifold with a hermitian metric $h$, and $\omega$ is the associated fundamental form of $h$. Then $h$ is a K&#228;hler metric if and only if $\mathrm{d}\omega = 0$. 

> *Proof:* Consider the local coordinates $z^1, \cdots, z^n$ of $M$. Let $$h_{j\bar{k}} = h\left(\frac{\partial}{\partial z^j}, \frac{\partial}{\partial z^k}\right), \quad j, k = 1, \cdots, n,$$ and $(h^{\bar{j}k})$ the inverse matrix of $(h_{j\bar{k}})$. By the expression of the metric connection, we obtain $$D\left(\frac{\partial}{\partial z^j}\right) = \sum_{k=1}^n \left(\sum_{m=1}^n \\partial h_{j\bar{m}} \cdot h^{\bar{m}k}\right) \otimes \frac{\partial}{\partial z^k} = \sum_{k,l=1}^n \left(\sum_{m=1}^n \frac{\partial h_{j\bar{m}}}{\partial z^l} \cdot h^{\bar{m}k}\right) \mathrm{d}z^l \otimes \frac{\partial}{\partial z^k}.$$ Thus $D$ is torsion-free if and only if $$\sum_{m=1}^n \frac{\partial h_{j\bar{m}}}{\partial z^l} \cdot h^{\bar{m}k} = \sum_{m=1}^n \frac{\partial h_{l\bar{m}}}{\partial z^j} \cdot h^{\bar{m}k},$$ which is equivalent to $$\frac{\partial h_{j\bar{m}}}{\partial z^l} = \frac{\partial h_{l\bar{m}}}{\partial z^j}, \quad j, l, m = 1, \cdots, n.$$
>
> Meanwhile, as $$\omega = \frac{i}{2}\sum_{j,k=1}^n h_{j\bar{k}} \mathrm{d}z^j \wedge \mathrm{d}\bar{z}^k,$$ we see that $$\mathrm{d}\omega = \frac{i}{2}\sum_{j,k=1}^n \sum_{l=1}^n \left(\frac{\partial h_{j\bar{k}}}{\partial z^l} \mathrm{d}z^l \wedge \mathrm{d}z^j \wedge \mathrm{d}\bar{z}^k + \frac{\partial h_{j\bar{k}}}{\partial \bar{z}^l}\mathrm{d}\bar{z}^l \wedge \mathrm{d}z^j \wedge \mathrm{d}\bar{z}^k\right).$$ Therefore $\mathrm{d}\omega = 0$ if and only if $$\frac{\partial h_{j\bar{k}}}{\partial z^l} = \frac{\partial h_{l\bar{k}}}{\partial z^j}, \quad \frac{\partial h_{j\bar{k}}}{\partial \bar{z}^l} = \frac{\partial h_{j\bar{l}}}{\partial \bar{z}^k}, \quad j, l, m = 1, \cdots, n.$$ Note that by the hermitian property of $h$, we have $$\frac{\partial h_{j\bar{k}}}{\partial \bar{z}^l} - \frac{\partial h_{j\bar{l}}}{\partial \bar{z}^k} = \overline{\frac{\partial \bar{h}\_{j\bar{k}}}{\partial z^l} - \frac{\partial \bar{h}\_{j\bar{l}}}{\partial z^k}} = \overline{\frac{\partial h_{k\bar{j}}}{\partial z^l} - \frac{\partial h_{l\bar{j}}}{\partial z^k}}.$$ The equivalence of the two conditions then follows. 

<!-- osculate to Euclidean to order 2 -->

Another important equivalent description of K&#228;hler metrics is that they are *almostly* the Euclidean metric locally. 

**Proposition.** Suppose $M$ is a complex manifold with a hermitian metric $h$. Then $h$ is a K&#228;hler metric if and only if for each $p \in M$, there is a coordinate system $(z^1, \cdots, z^n)$ centered at $p$ such that $h$ is expressed locally as $$h = \sum_{j,k=1}^n [\delta_{jk} + O(|z|^2)] \mathrm{d}z^j \wedge \mathrm{d}\bar{z}^k.$$

> *Proof:* One direction is clear: if $h$ has the above local expression, then we see that $h$ is K&#228;hler. Conversely, suppose that $h$ is a K&#228;hler metric on $M$. Fix a point $p \in M$ and consider a local coordinate system $w^1, \cdots, w^n$ centered at $p$ with $h$ expressed as $$h = \sum_{j,k=1}^n h_{j\bar{k}} \mathrm{d}w^j \otimes \mathrm{d}\bar{w}^k.$$ By the Gram-Schimdt process, we may assume that $h_{j\bar{k}}(p) = \delta_{jk}$ for each $j, k$. Then $$h_{j\bar{k}} = \delta_{jk} + \sum_{l=1}^n \left(\frac{\partial h_{j\bar{k}}}{\partial w^l} w^l + \frac{\partial h_{j\bar{k}}}{\partial \bar{w}^l} \bar{w}^l\right) + O(|w|^2).$$ Now define $z^1, \cdots, z^n$ by $$w^j = z^j - \frac{1}{2}\sum_{k,l=1}^n \frac{\partial h_{j\bar{k}}}{\partial w^l} z^k z^l.$$ We can verify that $(z^1, \cdots, z^n)$ is a well-defined coordinate system locally centered at $p$. Then $$\mathrm{d}w^j = \mathrm{d}z^j - \frac{1}{2}\sum_{k,l=1}^n \left(\frac{\partial h_{j\bar{k}}}{\partial w^l} (\mathrm{d}z^k \cdot z^l + z^k \cdot \mathrm{d}z^l) + O(|z|^2)\right) = \mathrm{d}z^j - \frac{1}{2}\sum_{k,l=1}^n \left(\frac{\partial h_{j\bar{k}}}{\partial w^l} + \frac{\partial h_{j\bar{l}}}{\partial w^k}\right) z^k \cdot \mathrm{d}z^l + O(|z|^2) = \mathrm{d}z^j - \sum_{k,l=1}^n \frac{\partial h_{j\bar{k}}}{\partial w^l} z^k \cdot \mathrm{d}z^l + O(|z|^2),$$ and hence $$\mathrm{d}w^j \otimes \mathrm{d}\bar{w}^k = \mathrm{d}z^j \otimes \mathrm{d}\bar{z}^k - \sum_{l,m=1}^n \left(\frac{\partial h_{j\bar{l}}}{\partial w^m} z^l \cdot \mathrm{d}z^m \otimes \mathrm{d}\bar{z}^k + \frac{\partial h_{l\bar{k}}}{\partial \bar{w}^m} \bar{z}^l \cdot \mathrm{d}z^j \otimes \mathrm{d}\bar{z}^m\right) + O(|z|^2).$$ Note that $$h_{j\bar{k}} = \delta_{jk} + \sum_{l=1}^n \left(\frac{\partial h_{j\bar{k}}}{\partial w^l}z^l + \frac{\partial h_{j\bar{k}}}{\partial \bar{w}^l} \bar{z}^l\right) + O(|z|^2),$$ direct computation yields that $$h = \sum_{j,k=1}^n [\delta_{jk} + O(|z|^2)] \mathrm{d}z^j \wedge \mathrm{d}\bar{z}^k.$$

## Examples and basic properties

<!-- examples -->
There are several examples of K&#228;hler manifolds whin our familiar complex manifold. 

+ The affine space $\mathbb{C}^n$ together with the Euclidean metric is K&#228;hler.
+ For a lattice $\Lambda$ generated by $2n$ real-linearly independent vectors, the complex torus $\mathbb{C}^n / \Lambda$ with the Eucliden metric is K&#228;hler.
+ Suppose $M$ is a Riemann surface, i.e., a complex manifold of dimension one. For any hermitian metric $h$ with the associated fundamental form $\omega$, $\mathrm{d}\omega$ is a $3$-form on $M$, which must be zero. Therefore $M$ is a K&#228;hler manifold.
+ If $M$ and $N$ are both K&#228;hler manifolds, then as the associated fundamental form of the induced metric on $M \times N$ is given by $$\omega_{M \times N} = \pi\_M^\* \omega\_M + \pi\_N^\* \omega\_N,$$ we see that $M \times N$ is also K&#228;hler.
+ Suppose $M$ is a K&#228;hler manifold and $S \subset M$ is a complex submanifold with the induced metric. Then $\omega_S = i^\*\omega_M$, where $i : S \to M$ is the embedding, implying that $S$ is a K&#228;hler manifold as well. 
+ We show that the projective space $\mathbb{P}^n$, together with the Fubini-Study metric $\omega$, is a K&#228;hler manifold. Let $\mathrm{d^c}$ be the real differential operators given by $$\mathrm{d}^\mathrm{c} = \frac{i}{4\pi}(\bar{\partial} - \partial).$$ Then $$\mathrm{d}\mathrm{d}^\mathrm{c} = -\mathrm{d}^\mathrm{c}\mathrm{d} = \frac{i}{2\pi}\partial\bar{\partial},$$ and hence locally we have $$\omega = \frac{i}{2\pi}\partial\bar{\partial} \log |z|^2 = \mathrm{d}\mathrm{d}^\mathrm{c} \log |z|^2.$$ Thus $\omega$ is $\mathrm{d}$-closed everywhere. 
+ By the previous two results, any compact complex manifold that can be embedded into $\mathbb{P}^n$ admits a K&#228;hler metric. 

<!-- H^0(M; \Omega^k_M) \to H^k(M; \mathbb{C}) injective -->
The K&#228;hler condition actually implies some topological properties of $M$. 

**Proposition.** Suppose $M$ is a compact K&#228;hler manifold. Then the holomorphic $k$-forms $H^0(M; \Omega^k_M)$ maps injectively into $H^k(M; \mathbb{C})$.

> *Proof:* Suppose $\eta$ is a holomorphic $k$-form. We first show that $\mathrm{d}\eta = 0$ implies that $\eta = 0$. Let $v_1, \cdots, v_n$ be a local orthonormal frame of $T^{1,0}(M)$ with dual frame $\varphi^1, \cdots, \varphi^n$. Suppose $$\eta = \sum_I \eta_I \varphi^I, \quad |I| = k,$$ then we have $$\eta \wedge \bar{\eta} = \sum_{I,J} \eta_I \bar{\eta}_J \varphi^I \wedge \varphi^J.$$ Note that 
> 
> $$\omega^{n-k} = C_k (n-k)! \sum_{K} \varphi^K \wedge \bar{\varphi}^K, \quad |K| = n - k,$$ we obtain the local expression 
> 
> $$\eta \wedge \bar{\eta} \wedge \omega^{n-k} = C_k \sum_I |\eta_I|^2 \cdot \mathrm{d}V.$$
>
> It follow that $$\int_M \eta \wedge \bar{\eta} \wedge \omega^{n-k} \neq 0$$ whever $\eta$ is nonzero. However, if $\eta = \mathrm{d}\xi$ for some $\xi$, then Stokes' formula implies that $$\int_M \eta \wedge \bar{\eta} \wedge \omega^{n-k} = \int_M \mathrm{d}(\xi \wedge \bar{\eta} \wedge \omega^{n-k}) = 0,$$ which can only hold when $\eta = 0$. 
>
> Now we see that $\mathrm{d}\eta = \partial\eta$ is a holomorphic $(k+1)$-form. Applying the previous arguments to $\mathrm{d}\eta$, we obtain $\mathrm{d}\eta = 0$.
>
> Altogether we conclude that there is a natural well-defined injection $H^0(M; \Omega^k_M) \to H^k(M; \mathbb{C})$. 

<!-- b_{2k}(M) > 0 -->

Recall that the **Betti number** $b_k(M)$ is defined to be the dimensional of the de Rham cohomology: $$b_k(M) = \dim H^k(M; \mathbb{C}).$$ 

**Propostion.** Suppose $M$ is a compact K&#228;hler manifold, then $b_{2k}(M) > 0$ for any $0 \leq k \leq n$.

> *Proof:* It suffices to find a closed $2k$-form which is not exact for each $0 \leq k \leq n$. Consider $\omega^k$, whose closedness follows from the K&#228;hler condition. If $\omega^k = \mathrm{d}\eta$ for some form $\eta$, then $$n! \cdot \mathrm{Vol}(M) = \int_M \omega^n = \int_M \mathrm{d}\eta \wedge \omega^{n-k} = \int_M \mathrm{d}(\eta \wedge \omega^{n-k}) = 0,$$ a contradiction. Thus $\omega^k$ cannot be exact. 