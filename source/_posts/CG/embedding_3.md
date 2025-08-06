---
title: Embedding of compact complex manifolds - 3
date: 2025-08-05 21:16:00
tags:
	- complex geometry
	- math
mathjax: true
---

For a positive line bundle on a compact complex manifold, the Kodaira vanishing thoerem tells us the higher cohomology groups can be controlled, and hence ensures that we can move from the local case to the global case. In this post we provide a proof of the Kodaira vanishing theorem and discuss some related results.

---

Note that a compact complex manifold with a positive line bundle admits a K&#228;hler metric from the metric on the bundle. First we extend some results about operators on the space of forms to those on the space of bundle-valued forms. Suppose $M$ is a compact K&#228;hler manifold with the K&#228;hler form $\omega$, and $E$ is a holomorphic vector bundle on $M$ with a hermitian metric $h$. Recall that we have operators $\partial, \bar{\partial}, \partial^\*, \bar{\partial}^\*, L$ and $\Lambda$ on $A(M)$, which satisfy on $A(M)$ that $[\Lambda, \bar{\partial}] = -i\partial^\*$ and on $A^{p,q}(M)$ that $[\Lambda, L] = n - p - q$. 

On the space $A(M,E)$, the operators $\bar{\partial}$ and $\bar{\partial}^\*$ are still well-defined. Meanwhile, $$\hat{L} : A^{p,q}(M,E) \to A^{p+1,q+1}(M,E), \quad \xi \mapsto \omega \wedge \xi$$ gives an operator on $A(M,E)$, whose dual operator clearly exists and is denoted by $\Lambda$. Since the metric connection $D$ on $E$ plays the role of the differential $\mathrm{d}$ on $M$, we can consider its holomorphic part $D^{1,0}$ as the analogy of $\partial$. Then we have a well-defined $$D^{1,0} : A^{p,q}(M,E) \to A^{p+1,q}(M,E).$$ Using the star operator, it is not hard to see that the operator $$D^{1,0*} = - \* D^{1,0} \* : A^{p,q}(M,E) \to A^{p-1,q}(M,E)$$ provides the dual of $D^{1,0}$. (Note that in the expression of $D^{1,0*}$, $D^{1,0}$ acts on $A(M,E^\*)$, where $E^\*$ is equipped with the induced metric from $E$.)

**Lemma.** Suppose $E$ is a holomorphic vector bundle on a compact K&#228;hler manifold $M$. Then we have on each $A^{p,q}(M,E)$ that $$[\Lambda, \bar{\partial}] = -iD^{1,0*}, \quad [\Lambda, \hat{L}] = n - p - q.$$ 

> *Proof:* Suppose $\\\{e^1, \cdots, e^k\\\}$ is a smooth local frame of $E$, with respect to which the connection matrix of $D$ is $A = A' + A''$, where $A' = \left({\alpha'}^k_l\right)$ consists of $(1,0)$-forms and $A'' = \left({\alpha''}^k_l\right)$ consists of $(0,1)$-forms. For $\xi \in A^{p,q}(M,E)$, we can express it as $$\xi = \sum_{k=1}^r \xi_k \otimes e^k, \quad \xi_k \in A^{p,q}(M).$$ Then it can be seen that $$\bar{\partial}\xi = \sum_{k=1}^r\left(\bar{\partial}\xi_k \otimes e^k + \sum_{l=1}^r \xi_k \wedge {\alpha''}^k_l \otimes e^l\right) = \sum_{k=1}^r\bar{\partial}\xi_k \otimes e^k + A''\xi,$$ and $$D^{1,0*} \xi = \sum_{k=1}^r \partial^\* \xi_k \otimes e^k + {A'}^\*\xi.$$ Meanwhile, it is clear that $$\hat{L}\xi = \sum_{k=1}^r \hat{L}\xi_k \otimes e^k, \quad \Lambda\xi = \sum_{k=1}^r \Lambda\xi_k \otimes e^k.$$ Thus $$\left([\Lambda, \bar{\partial}] + iD^{1,0*}\right)\xi = \sum_{k=1}^r \left([\Lambda,\bar{\partial}] + i\partial^\*\right)\xi_k \otimes e^k + \left([\Lambda, A''] + i{A'}^\*\right)\xi = \left([\Lambda, A''] + i{A'}^\*\right)\xi.$$
>
> For each $x \in M$, we can take a smooth frame such that $A$ vanishes at $x$, which implies that $$\left.\left([\Lambda, \bar{\partial}] + iD^{1,0*}\right)\xi\right|\_x = \left.\left([\Lambda, A''] + i{A'}^\*\right)\xi\right|\_x = 0.$$ By the arbitrarity of $x$, we see that $$[\Lambda, \bar{\partial}] = -iD^{1,0*}$$ holds as operators on $A^{p,q}(M,E)$.
>
> It is direct to see that $$[\Lambda, \hat{L}]\xi = \sum_{k=1}^r [\Lambda, \hat{L}]\xi_k \otimes e^k = \sum_{k=1}^r (n - p - q)\xi_k \otimes e^k = (n - p - q)\xi$$ holds for any $\xi \in A^{p,q}(M,E)$. 

---

Now we can prove the Kodaira vanishing theorem.

**Theorem (Kodaira vanishing theorem).** Suppose $M$ is an $n$-dimensional compact complex manifold and $L$ is a positive line bundle on $M$. Then $$H^{p,q}(M,L) = 0, \quad p + q > n.$$ 

> *Proof:* Suppose $h$ is a metric on $L$ such that the associated real $(1,1)$-form $$\omega = \frac{i}{2\pi}\Omega = -\frac{i}{2\pi}\partial\bar{\partial}\log h$$ is positive. Then $\omega$ provides a K&#228;hler stucture on $M$. Assume that the metric connection of $h$ on $L$ is $D = D^{1,0} + \bar{\partial}$. Comparing the type of forms in the equality $$(D^{1,0})^2\xi + (D^{1,0}\bar{\partial} + \bar{\partial}D^{1,0})\xi + \bar{\partial}^2\xi = D^2\xi = \Omega \wedge \xi = -2\pi i \hat{L}\xi, \quad \xi \in A^{p,q}(M,L),$$ we see that $$D^2 = D^{1,0}\bar{\partial} + \bar{\partial}D^{1,0} = -2\pi i\hat{L}.$$
>
> Now by Hodge theorem, there is a canonical isomorphism $H^{p,q}(M,L) \cong \mathcal{H}^{p,q}(M,L)$. Thus it suffices to show that a harmonic form $\xi \in \mathcal{H}^{p,q}(M,L)$ must be zero whenever $p + q > n$. Take any $\xi \in \mathcal{H}^{p,q}(M,L)$ with $p + q > n$. Then $$2\pi\hat{L}\xi = iD^2\xi = iD^{1,0}\bar{\partial}\xi + i\bar{\partial}D^{1,0}\xi = i\bar{\partial}D^{1,0}\xi,$$ implying that $$2\pi(\Lambda\hat{L}\xi,\xi) = i(\Lambda\bar{\partial}D^{1,0}\xi,\xi) = i(\bar{\partial}\Lambda D^{1,0}\xi,\xi) + i(-iD^{1,0*}D^{1,0}\xi,\xi) = i(\Lambda D^{1,0}\xi,\bar{\partial}^\*\xi) + (D^{1,0}\xi,D^{1,0}\xi) = \\\|D^{1,0}\xi\\\|^2.$$ On the other hand, since $$2\pi\hat{L}\Lambda\xi = i(\bar{\partial}D^{1,0} + D^{1,0}\bar{\partial})\Lambda\xi = i\bar{\partial}D^{1,0}\Lambda\xi + iD^{1,0}(\Lambda\partial + iD^{1,0*})\xi = i\bar{\partial}D^{1,0}\Lambda\xi - D^{1,0}D^{1,0*}\xi,$$ we have $$2\pi(\hat{L}\Lambda\xi,\xi) = i(\bar{\partial}D^{1,0}\Lambda\xi,\xi) - (D^{1,0}D^{1,0*}\xi,\xi) = i(D^{1,0}\Lambda\xi,\bar{\partial}^\*\xi) - (D^{1,0*}\xi,D^{1,0*}\xi) = -\\\|D^{1,0*}\xi\\\|^2.$$ Therefore $$2\pi(n - p - q)\\\|\xi\\\|^2 = 2\pi([\Lambda,\bar{L}]\xi,\xi) = \\\|D^{1,0}\xi\\\|^2 + \\\|D^{1,0*}\xi\\\|^2 \geq 0.$$ Since $n - p - q < 0$, it must be true that $\xi = 0$, proving our assertion. 

Using the Dolbeault theorem, it is direct that $$H^q(M; \Omega_M^p(L)) \cong H^{p,q}(M,L) = 0, \quad p + q > n.$$ In particular, taking $p = n$, we obtain $$H^q(M; \mathcal{O}_M(L \otimes K_M)) \cong H^q(M; \Omega_M^n(L)) = 0, \quad q > 0.$$ If we consider the Kodaira-Serre duality, then $$H^q(M;\Omega_M^p(L^\*)) \cong H^{p,q}(M,L^\*) \cong (H^{n-p,n-q}(M,L))^\* = 0, \quad p + q < n.$$

As an corollary, we see that $H^q(\mathbb{P}^n; \mathcal{O}(H^k))$ vanishes for several cases, where $H$ is the hyperplane bundle on $\mathbb{P}^n$. Note that since $H$ is positive, any tensor power $H^k$ with $k > 0$ is positive. 
+ if $k < 0$, then $H^{-k}$ is positive, implying that $$H^q(\mathbb{P}^n; \mathcal{O}(H^k)) = H^q(\mathbb{P}^n; \Omega_M^0((H^{-k})^\*)) = 0, \quad k < 0, \quad q < n;$$ 
+ if $k \geq -n$, then note that by computations of transition functions we have $K_{\mathbb{P}^n} \cong H^{-n-1}$, suggesting that $$H^q(\mathbb{P}^n; \mathcal{O}(H^k)) = H^q(M; \mathcal{O}(H^{k+n+1} \otimes K_{\mathbb{P}^n})) = 0, \quad q > 0.$$ 

Therefore $$H^q(\mathbb{P}^n; \mathcal{O}(H^k)) = 0, \quad \text{if } \begin{cases} q = 0, \\\; k < 0; \\\\ 0 < q < n; \\\\ q = n, \\\; k \geq -n. \end{cases}$$

---

There is another interesting vanishing theorem which can be shown in a similar method to the Kodaira vanishing theorem. 

**Theorem.** Suppose $M$ is an $n$-dimensional compact complex manifold and $L$ is a positive line bundle on $M$. Then for any holomorphic vector bundle $E$ on $M$, there exists $k_0 > 0$ such that $$H^q(M; \mathcal{O}_M(L^k \otimes E)) = 0, \quad k \geq k_0, \quad q > 0.$$ 

> *Proof:* Note that $$H^q(M; \mathcal{O}_M(L^k \otimes E)) \cong H^{0,q}(M, L^k \otimes E) \cong (H^{n,n-q}(M, L^{-k} \otimes E^\*))^\* \cong (H^{0,n-q}(M, L^{-k} \otimes E^\* \otimes K_M)) \cong (\mathcal{H}^{0,n-q}(M, L^{-k} \otimes E^\* \otimes K_M))^\*,$$ it suffices to show that for any holomorphic vector bundle $E$ and sufficiently large $k$ we have $$\mathcal{H}^{0,n-q}(M, L^{-k} \otimes E) = 0, \quad k \geq k_0, \quad q > 0.$$ 
>
> Suppose $h_L$ is the metric on $L$ such that $\omega_L = (i/2\pi)\Omega_L$ gives a K&#228;hler metric on $M$, and $h_E$ is a metric on $E$ with curvature form $\Omega_E$. Then $h = h_L^{-k} \cdot h_E$ provides a metric on $L^{-k} \otimes E$, whose metric connection is denoted by $D = D^{1,0} + \bar{\partial}$. Then the curvature of $h$ is exactly $$\Omega = -k \Omega_L \otimes I + \Omega_E = 2\pi i k \omega_L \otimes I + \Omega_E.$$ By a similar argument in the proof of the Kodaira vanishing theorem, we see that $$i([\Lambda, \Omega]\xi, \xi) = i(\Lambda\Omega\xi,\xi) - i(\Omega\Lambda\xi,\xi) = \\\|D^{1,0}\xi\\\|^2 + \\\|D^{1,0*}\xi\\\|^2 \geq 0, \quad \xi \in \mathcal{H}^{0,n-q}(M, L^{-k} \otimes E).$$ Thus $$0 \leq i([\Lambda,\Omega]\xi,\xi) = -2\pi k([\Lambda,\hat{L}]\xi,\xi) + i([\Lambda,\Omega_E]\xi,\xi) = -2\pi kq \\\|\xi\\\|^2 + i([\Lambda,\Omega_E]\xi,\xi).$$ 
>
> For each $x \in M$, $[\Lambda, \Omega_E]|\_x$ is an operator on the fiber $(L^{-k} \otimes E)\_x$ such that the norm $\\\|[\Lambda,\Omega_E]|\_x\\\|$ is independent of $k$. Let $$C = \max_{x \in M} \\\|[\Lambda,\Omega_E]|\_x\\\|,$$ then we have $$0 \leq -2\pi kq \\\|\xi\\\|^2 + i([\Lambda,\Omega_E]\xi,\xi) \leq (C - 2\pi kq)\\\|\xi\\\|^2.$$ Therefore $\xi = 0$ whenever $k > C / 2 \pi$, proving our assertion.