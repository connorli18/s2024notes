# [4/9] Number Theory

#### Holomorphic Modular Form

**Definition:** If a function $f: \mathfrak{h} \rightarrow \mathbb{C}$ and holomorphic at $i\infty$, $\lim_{y \rightarrow \infty} f(x + iy)$ exists and is $\neq \infty$. 

- $f\left(\frac{az+b}{cz+d}\right) = (cz+d)^k f(z)$ for all $\begin{pmatrix} a & b \\ c& d \end{pmatrix} \in SL(2,\mathbb{Z})$, $k \in \mathbb{Z}$ and $k \equiv 0 \text{ mod }2$ 
- $f(z) = \sum_{n=0}^\infty a_n e^{2\pi i n z}$ 

**Definition:** The following $L$ function converges absolutely for $\Re(s) \gg 1$ 
$$
L(s,f) := \sum_{n=1}^\infty \frac{a_n}{n^s}
$$


----

#### Functional Equation of $L(s,f)$​​

**Proof:** Let's evaluate the following.
$$
\begin{align*}

\int_0^\infty \left(f(iy) - a_0\right) y^s \;\frac{dy}{y} &= \int_0^\infty \sum_{n=1}^\infty \underbrace{a_n e^{-2\pi i n y} y^s \;\frac{dy}{y}}_{y \mapsto \frac{y}{2\pi n}} \\
&= (2\pi)^{-s} L(s,f) \int_0^\infty e^{-y}y^s \frac{dy}{y} \\
&= (2\pi )^{-s} \Gamma(s) L(s,f)


\end{align*}
$$

----

**Property**: A function is modular iff it is invariant under $\begin{pmatrix} 1 & 1 \\ 0 & 1\end{pmatrix}, \begin{pmatrix} 0 & -1 \\ 1 & 0\end{pmatrix}$. 
$$
f(z+1) = f(z) \quad \quad \quad f\left(-\frac{1}{z}\right) = z^k f(z)
$$

----

Utilizing the property, we have that
$$
\begin{align*}
\int_0^\infty (f(iy) - a_0) y^s \frac{dy}{y} &= \underbrace{\int_0^1 (f(iy) - a_0)y^s \frac{dy}{y}}_{I_1(s)} +\underbrace{\int_1^\infty (f(iy) - a_0) y^s \frac{dy}{y}}_{I_2(s)}\\
\end{align*}
$$
**Claim:** $I_2(s)$ is an entire function with no poles.
$$
I_2(s) = \int_1^\infty \sum_{n=1}^\infty a_n e^{-2\pi n y} y^s \frac{dy}{y}
$$
Thus, we only have to deal with $I_1(s)$. Let's use the relationship that $f\left(\frac{i}{y}\right) = (iy)^k f(y)$. 
$$
\begin{align*}

I_1(s) &= \int_0^1 (f(iy) - a_0) y^s \frac{dy}{y} \\
&= \int_0^1 \left(f\left(\frac{i}{y}\right) \cdot (iy)^{-k} - a_0\right) y^s \frac{dy}{y}\\
&= \underbrace{i^{-k} \int_0^1 f\left(\frac{i}{y}\right) y^{s - k} \frac{dy}{y}}_{y \mapsto \frac{1}{y}} - \int_0^1 a_0 y^{s-1}\;dy \\
&= i^{-k} \int_1^\infty f(iy) y^{k-s} \frac{dy}{y}\\
&= i^{k}  \int_1^\infty \sum_{n=1}^\infty a_n e^{-2\pi i ny}y^{k-s} \frac{dy}{y} + i^k \int_1^\infty a_0y^{k-s-1}\;dy\\
&= [\cdots] + \frac{i^k a_0}{k-s}
\end{align*}
$$
Thus, we have the following desired result.
$$
\begin{align*}
(2\pi)^{-s} \Gamma(s) L(s,f) &= i^k \int_1^\infty \underbrace{\left(\sum_{n=1}^\infty a_n e^{-2\pi n y}\right)}_{\text{entire}} y^{k-s} \frac{dy}{y} + \int_1^\infty \underbrace{\left(\sum_{n=1}^\infty a_n e^{-2\pi n y}\right)}_{\text{entire}} y^{s} \frac{dy}{y} - \frac{a_0}{s} + \frac{i^{k}a_0}{k-s}\\
&= -i^{k} (2\pi)^{-(k-s)} \Gamma(k-s) L(k-s, f)

\end{align*}
$$

----

 **Theorem:** (Hecke) Let $f: \mathfrak{h} \rightarrow \mathbb{C}$ be a holomorphic modular form (also holomorphic at $i\infty)$. Then, 
$$
\psi_f(s) = (2\pi)^{-s}\;\Gamma(s) \;L(s,f)
$$
has meromorphic continuity to all $s \in \mathbb{C}$ with simploe poles at $s = 0, k$ with residues $-a_0, \;i^k a_0$ respectively. It also has a functional equation $\psi_f(s) = -i^{k}\cdot  \psi_f(k-s)$. 

---

**Theorem:** Let $f \in M_k$. Then, for every integer $n$, define
$$
T_n \;f(z) := \frac{1}{n} \sum_{\substack{ad = n \\ a \geq 1 \\0 \leq b < d}} a^k f\left(\frac{az+b}{d}\right)
$$
Assume that $f$ satisfies $T_n \; f = \lambda_n \;f$ for all $n \in \mathbb{N}$. Then,
$$
f(z) = \sum_{n=1}^\infty \lambda_n e^{2\pi i n z}
$$
This also implies that $L(s,f) = \prod_{p} \left(1 - \lambda_p p^{-s} + p^{2k - 1 - 2s}\right)^{-1}$.

----

#### Valence Formula

Let $p \in \mathfrak{h}$ and assume that $f(p) = 0$. This implies that
$$
f(z) = (z-p)^{m} \cdot h(z)
$$


where $h$ is holomorphic and $h(p) \neq 0$​. If we take the $\log$ of both sides,
$$
\frac{d}{dz} \log f(z) = \frac{m}{z-p} + \frac{h'(z) }{h(z)} \implies \frac{f'(z)}{f(z)} \backsim \frac{m}{z-p} \quad \text{ for } z \rightarrow p
$$
<u>Notation:</u> $\mathcal{V}_p(f) = m$. We consider $m =$ order of the zero $p$.

<u>Zero at $i\infty$</u>: $\mathcal{V}_\infty(f) = m$ means that $f$ has a zero of order $m$ at $i\infty$. 

If $q = e^{2\pi i z}$, then
$$
F(q) = f(z) = \sum_{n=0}^\infty a_nq^n
$$
We say that $F$ has a zero of order $m$ at $i \infty$ if $F(q) = q^m h(q)$ where $h(q)$ is holomorphic and doesn't vanish at $i \infty$. For $y \rightarrow \infty$, 
$$
q = e^{2\pi i (x + iy)} \implies \lim_{y\rightarrow \infty} q^m = \lim_{y\rightarrow \infty} e^{(2\pi i x - 2 \pi y)m} = 0
$$
This also implies that $\frac{F'(q)}{F(q)} \backsim \frac{m}{q}$ as $y \rightarrow \infty$. 

**Theorem (Valence):** Let $f \in M_k$. Then, when $\rho = \frac{1}{2} + \frac{\sqrt{3}}{2}i$, 
$$
\mathcal{V}_\infty (f) + \frac{1}{2} \mathcal{V}_i(f) + \frac{1}{3} \mathcal{V}_\rho (f) + \sum_{\substack{p \in \mathfrak{h}/SL(2,\mathbb{Z}) \\ p \neq i, \rho}} \mathcal{V}_p (f) = \frac{k}{12}
$$

- If $k < 0$, then holomorphic modular forms don't exist. In other words, $k < 0 \implies \dim(M_k) = 0 $. 

- If $k = 0$, then the only holomorphic form is the constant function $f(z) = c$ where $c \neq 0$. In other words, $k = 0 \implies \dim(M_k) = 1$. 

- If $k = 2$, then $\dim(M_2) = 0$. 

- If $k = 4$, then $\dim(M_4) = 1$ and $E_4(\rho) = 0$ 
- If $k=0$, then $\dim(M_6) = 1$  and $E_6(1) = 0$ 

- $\dim(M_8) = 1 \implies E_8(\rho) = 0$ with zero of order $= 2$
- $\dim(M_{10}) = 1 \implies E_{10}(i) = 0$ and $E_{10}(\rho) = 0$ 
- $\dim(M_{12}) = 2$

Since $\Delta(z) = \sum_{n=1}^\infty \tau(n) e^{2\pi i n z}$ where $ \tau(1) = 1 \implies \mathcal{V}_\infty (\Delta) = 1$ which vanishes at $i\infty$.   
