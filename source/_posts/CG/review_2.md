---
title: Review of holomorphic functions of one variable - 2
date: 2025-05-30 09:00:00
tags: 
    - complex geometry
    - math
mathjax: true
---

In this post, we are going to prove the *Riemann mapping theorem*, which characterizes the simply connected open subsets in $\mathbb{C}$. 

**Theorem (Riemann mapping theorem).** Suppose $\Omega$ is a simply connected nonempty proper subset in $\mathbb{C}$ and $z_0 \in \Omega$. Then there exists a unique bijective and holomorphic $F : \Omega \to D(0, 1)$ with nonvanishing derivative such that $F(z_0) = 0$ and $F'(z_0) > 0$. 

> *Remark:* A bijective and holomorphic function with nonvanishing derivative is usually called a **conformal** function. This is equivalent to that the function has a holomorphic inverse. 

First let us consider the uniqueness statement.

**Theorem (Schwarz lemma).** Suppose $f : D(0, 1) \to D(0, 1)$ is holomorphic and satisfies $f(0) = 0$. Then $|f(z)| \leq |z|$ for each $z \in D(0, 1)$ and $|f'(0)| \leq 1$. If either there is a nonzero $z_0 \in D(0, 1)$ such that $|f(z_0)| = |z_0|$, or $|f'(0)| = 1$, then $f(z) = e^{it}z$ for some $t \in \mathbb{R}$. 

> *Proof:* Since $f(0) = 0$, there is a holomorphic function $g : D(0, 1) \to \mathbb{C}$ such that $f(z) = zg(z)$ for each $z \in D(0, 1)$. For each $0 < r' \leq r < 1$, the maximal value of $|g(z)|$ on $\overline{D(0, r)}$ can only be attained on $\partial D(0, r)$, implying that $$|g(z)| \leq \max_{|z| = r}\frac{|f(z)|}{|z|} \leq \frac{1}{r}, \quad |z| \leq r'.$$ It follows that $|g(z)| \leq 1$ on $D(0, 1)$. Therefore $|f(z)| \leq |z|$ for any $z$ and $|f'(0)| = |g(0)| \leq 1$. If either of the equality holds, then $g$ must be constant on $D(0, 1)$ by the maximal module principle. Thus $g(z) = e^{it}$ for some $t \in \mathbb{R}$ and $f(z) = e^{it}z$. 

The uniqueness statement of the Riemann mapping theorem then follows from the Schwarz lemma. In fact, suppose $F$ and $G$ both satisfies the conditions, then we can consider the holomorphic functions $F \circ G^{-1}$ and $G \circ F^{-1}$. The Schwarz lemma then implies that $F$ and $G$ are only differ by a rotation. Since their derivatives are both positive real at $z_0$, they are actually the same. 

Before the proof of the existence statement, we introduce the concept of *univalent* functions. A function $f : D \to \mathbb{C}$ on a connected open set is called **univalent** if $f$ is injective and holomorphic. 

**Theorem.** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f : D \to \mathbb{C}$ is univalent. Then $f'$ has no zero on $D$.

> *Proof:* Assume $f'(z_0) = 0$ for some $z_0 \in D$. Let $f(z_0) = w_0$. Then $z_0$ is a zero of $f(z) - w_0$ with order $m \geq 2$. Take a neighborhood of $z_0$ on which $z_0$ is the only zero of $f'$. By a similar proof to the open mapping theorem, for each $w$ sufficiently near $w_0$, the total order of zeros of $f(z) - w$ in the neighborhood is $m \geq 2$. Since $f'$ is nonzero at these zeros, they must be $m$ different zeros of order $1$, contradicting the injectivity of $f$. We conclude that $f'$ cannot have any zero on $D$.

Since a bijective and holomorphic function is naturally univalent, it must have nonvanishing derivative, and hence become conformal. 

**Theorem (Montel theorem).** Suppose $D$ is a connected open set in $\mathbb{C}$, and $\mathcal{F}$ is a nonempty family of holomorphic functions on $D$ such that $\mathcal{F}$ is uniformly bounded on each compact subset. Then $\mathcal{F}$ is equicontinuous on each compact subset, and each sequence in $\mathcal{F}$ has a subsequence that is uniformly convergent on each compact subset. 

> *Proof:* First we show that for each $z_0 \in D$, there is $r > 0$ such that $\overline{D(z_0, r)} \subset D$ and $\mathcal{F}$ is equicontinuous on $\overline{D(z_0, r)}$. Since $D$ is open, we can take $D(z_0, d_0) \subset D$. Let $r = d_0 / 3$, and we see that $\overline{D(z_0, r)} \subset D$. There is $M > 0$ such that for each $z \in \overline{D(z_0, 2r)}$ and each $f \in \mathcal{F}$, we have $|f(z)| < M$. Consider any $\varepsilon > 0$. Take $\delta < r \varepsilon / 2M$. For each $z_1, z_2 \in \overline{D(z_0, r)}$ such that $|z_1 - z_2| < \delta$, and each $f \in \mathcal{F}$, we have $$|f(z_1) - f(z_2) = \left|\frac{1}{2 \pi i}\oint_{|z - z_0| = 2r} f(z)\left(\frac{1}{z - z_1} - \frac{1}{z - z_2}\right) \mathrm{d} z\right| \leq \frac{1}{2 \pi} \cdot 4 \pi r \cdot \frac{M \delta}{r^2} < \varepsilon.$$
> 
> Then we show that $\mathcal{F}$ is equicontinuous on each compact subset. Consider any compact subset $K \subset D$ and $\varepsilon > 0$. For each $z \in K$, there is a neighborhood $\overline{D(z, r_z)} \subset D$ such that $\mathcal{F}$ is equicontinuous on $\overline{D(z, r_z)}$. Since $D(z, r_z)$ form an open cover of $K$ and $K$ is compact, there are $z_1, \cdots, z_m \in K$ such that $$K \subset \bigcup_{k=1}^m D(z_k, r_k).$$ By the *Lebesgue number lemma*, we have a $\delta_0 > 0$ such that for $\omega_1, \omega_2 \in K$, $|\omega_1 - \omega_2| < \delta_0$ implies that they are contained in the same $D(z_k, r_k)$ for some $k$. As shown in the previous part, for each $k$ there is $\delta_k > 0$ such that $$|f(\omega_1) - f(\omega_2)| < \varepsilon, \quad \omega_1, \omega_2 \in K, |\omega_1 - \omega_2| < \delta_k, f \in \mathcal{F}.$$ Let $\delta = \min_{0 \leq k \leq m} \delta_k$. Then we can see that for each $\omega_1, \omega_2 \in K$ such that $|\omega_1 - \omega_2| < \delta$, and each $f \in \mathcal{F}$, we have $|f(\omega_1) - f(\omega_2)| < \varepsilon$. 
> 
> Now we show the final conclusion. Suppose $f_n$ is a sequence in $\mathcal{F}$. Take a sequence $K_n$ of compact substes of $D$ such that $$\bigcup_{n=1}^\infty K_n = D,$$ that $K_n \subset K_{n+1}^\circ$ for ech $n$, and that for each compact $K \subset D$, there is $N$ such that $K \subset K_N$. By the previous part and the *Arzela-Ascoli theorem*, there is a subsequence $f_{1,n}$ of $f_n$ such that $f_{1,n}$ converges uniformly on $K_1$. Then there is a subsequence $f_{2,n}$ of $f_{1,n}$ such that $f_{2,n}$ converges uniformly on $K_2$. Doing this repeatedly, we have a list of sequence $f_{m,n}$ such that $f_{k,n}$ converges uniformly on $K_m$ for each $k \geq m$. Let $g_n = f_{n,n}$. For a compact $K \subset D$, take $N$ such that $K_N$ contains $K$. We see that $g_n (n \geq N)$ is a subsequence of $f_{N,n}$, implying that $g_n$ converges uniformly on $K \subset K_N$. 

Now we step into the proof of the existence statement of the Riemann mapping theorem.

**STEP 1.** Each simply connected nonempty proper subset $\Omega$ of $\mathbb{C}$ can be conformally mapped into a subset of $D(0, 1)$, with the given $z_0$ maps to $0$. 

> Take $\zeta \in \mathbb{C} \setminus \Omega$. Since $\Omega$ is simply connected, we have take a simple-valued holomorphic branch of $$f(z) = \log(z - \zeta), \quad z \in \Omega.$$ We can directly see that $f$ is injective. Fix a $\omega \in \Omega$. We claim that $|f(z) - [f(\omega) + 2 \pi i]|$ has a positive lower bound on $\Omega$. Otherwise, there is a sequence $z_1, \cdots, z_n, \cdots$ in $\Omega$ such that $f(z_n) \to f(\omega) + 2 \pi i$. Then $$z_n = e^{f(z_n)} + \zeta \to e^{f(\omega) + 2 \pi i} + \zeta = \omega,$$ implying that $f(z_n) \to f(\omega)$, a contradiction. Thus $$F_0(z) = \frac{1}{f(z) - [f(\omega) + 2 \pi i]}$$ is a bounded univalent mapping on $\Omega$. By a scaling and a translation, we get a conformal mapping from $\Omega$ to a subset of $D(0, 1)$ that maps $z_0$ to $0$. 

Therefore we can assume that $\Omega$ is contained in $D(0, 1)$ and that $z_0 = 0$. 

**Lemma.** Suppose $D$ is a connected open set in $\mathbb{C}$ and $f_n$ is a sequence of univalent functions on $D$ such that $f_n$ converges uniformly to $f$ on each compact subset. Then either $f$ is constant or $f$ is univalent.

> *Proof:* The Cauchy integral formula and the uniform convergence on each compact subset implies that $f$ is holomorphic. Assume that $f$ is nonconstant and not injective. Then there are $z_1 \neq z_0$ in $D$ such that $f(z_1) = f(z_0)$.  Since $g$ is nonconstant, there is $r > 0$ such that $z_1$ is the only zero of $f(z) - f(z_0)$ in $D(z_1, 2r) \subset D$. It follows from the argument principle that $$\frac{1}{2 \pi i}\oint_{|z - z_1| = r}\frac{f'(z)}{f(z) - f(z_0)} \mathrm{d} z = 1.$$ Noting that each $f_n$ is injective, and that we have the uniform convergence $$\frac{f_n'(z)}{f_n(z) - f_n(z_0)} \to \frac{f(z)}{f(z) - f(z_0)}, \quad |z - z_1| = r,$$ we obtain $$\oint_{|z - z_1| = r}\frac{f'(z)}{f(z) - f(z_0)} \mathrm{d} z = \lim_{n \to \infty} \oint_{|z - z_1| = r}\frac{f_n'(z)}{f_n(z) - f_n(z_0)} \mathrm{d} z = 0,$$ a contradiction. The conclusion follows. 

**STEP 2.** The "maximal" univalent function from $\Omega$ to $D(0, 1)$ preserving the origin is the desired conformal mapping. 

> Let $\mathcal{F}$ be the family of all univalent functions from $\Omega$ to $D(0, 1)$ that maps $0$ to $0$. Since the identity function belongs to $\mathcal{F}$, $\mathcal{F}$ is nonempty. It is clear that $\mathcal{F}$ is uniformly bounded. Take $r > 0$ such that $D(0, 2r) \subset \Omega$. By the Cauchy integral formula, we have $$|f'(0)| = \left|\frac{1}{2 \pi i} \oint_{|z| = r} \frac{f(z)}{z^2} \mathrm{d}z\right| \leq \frac{1}{2 \pi} \cdot 2 \pi r \cdot \frac{1}{r^2} = \frac{1}{r}, \quad f \in \mathcal{F}.$$ Thus $s = \sup_{f \in \mathcal{F}} |f'(0)|$ is finite. Meanwhile, as the identity function belongs to $\mathcal{F}$, we have $s \geq 1$. Suppose $f_n$ is a sequence in $\mathcal{F}$ such that $|f_n'(0)| \to s$. By the Montel theorem, there is a subsequence of $f_n$ converging uniformly to a function $f : \Omega \to D(0, 1)$ on each compact subsets on $\Omega$. We can then see that $f$ is univalent and $f(0) = 0$ from the lemma and the fact that $s \geq 1 > 0$. Thus $f \in \mathcal{F}$ with $|f'(0)| = s$. 
>
> It remains to show that $f$ is surjective onto $D(0, 1)$. Assume that $f$ is not surjective. Then there is $\alpha \in D(0, 1) \setminus f(\Omega)$. Let $$\psi_\alpha(z) = \frac{\alpha - z}{1 - \bar{\alpha}z}.$$ Then $\psi_\alpha$ is a conformal mapping from $D(0, 1)$ to itself that switches $0$ and $\alpha$. It follows that $U = (\psi_\alpha \circ f)(\Omega)$ does not contain $0$, and hence there is a simple-valued holomorphic branch of $h(z) = \sqrt{z}, z \in U.$ Consider $$\tilde{f} = \psi_{h(\alpha)} \circ h \circ \psi_\alpha \circ f : \Omega \to D(0, 1).$$ It can be seen that $\tilde{f}$ is univalent with $\tilde{f}(0) = 0$, i.e., $\tilde{f} \in \mathcal{F}$. Let $g(z) = z^2$ and $$\Psi = \psi_\alpha^{-1} \circ g \circ \psi_{h(\alpha)}^{-1} : D(0, 1) \to D(0, 1).$$ Since $\Psi$ is not injective, it cannot be a rotation, and then the Schwarz lemma suggests that $|\Psi'(0)| < 1$. Noting that $f = \Psi \circ \tilde{f}$, we have $$|f'(0)| = |\Psi'(0)||\tilde{f}'(0)|.$$ If $|\tilde{f}'(0)|$ is positive, then $s = |f'(0)| < |\tilde{f}'(0)|$, contracting to that $s$ is the supremum. Otherwise $|f'(0)| = |\tilde{f}'(0)| = 0$, a contradiction as well. In conclusion, $f$ must be surjective. 

The proof of the Riemann mapping theorem is now completed. 