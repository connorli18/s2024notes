# [4/4] Number Theory

#### Extension of Cusp Forms

Let's begin by defining two vector spaces.

- $M_k = $ vector space of all holomorphic modular $f$ forms for $SL(2,\mathbb{Z})$ where $f(z) = \sum_{n=0}^\infty a(n) e^{2\pi i n z}$ 
- $S_k =$ vector space of holomorphic modular forms $f$ where $f(z) = \sum_{n=1}^\infty a(n) e^{2\pi i n z}$ (cusp forms)

<u>Examples:</u>

- $\widetilde{E}_k (z) = \sum_{\substack{c,d \in \mathbb{Z} \\ (c,d) \neq (0,0)}} \frac{1}{(cz+d)^k} \in M_k$  for $k = 4,6,8,\dots$ 
- $\Delta(z) = \sum_{n=1}^\infty \tau(n) e^{2\pi i n z} \in S_{12}$ 

---

**Definition:** Last time, we showed the following
$$
\widetilde{E}_k(z) = 2\zeta(k) + \frac{2(2\pi i)^k}{(k-1)!} \sum_{n=1}^\infty \sigma_{k-1}(n)e^{2\pi i n z} \quad \quad \quad \sigma_k(n) = \sum_{d|n} d^k
$$
**Claim:** $\dim(M_k) < \infty$ for all $k \in \mathbb{Z}$.

---

**Theorem:** If $k < 0$, then $M_k = \{0\}$. 

**Proof:** Assume $f \in M_k$ with $k < 0$. 
$$
f\left(\frac{az+b}{cz+d}\right) = (cz+d)^k f(z) \quad \quad \quad \Im\left(\frac{az+b}{cz+d}\right) = \frac{y}{|cz+d|^2}
$$
This implies that
$$
\begin{align*}
\left|f\left(\frac{az+b}{cz+d}\right)\right| \cdot \Im\left(\frac{az+b}{cz+d}\right)^{\frac{k}{2}} &= |f(z)| \cdot \Im(z)^{\frac{k}{2}}\\
\left|f\left(\frac{az+b}{cz+d}\right)\right| \cdot \frac{y^{\frac{k}{2}}}{(cz+d)^k} &= |f(z)| \cdot y^{\frac{k}{2}}
\end{align*}
$$
Now, let's take the following limit.
$$
\lim_{y\rightarrow \infty} |f(iy)| \cdot y^{\frac{k}{2}} = 0 \implies |f(z)| \cdot \Im(z)^{\frac{k}{2}} \ll 1
$$
This implies that,
$$
|f(x+iy)| \cdot y^{\frac{k}{2}} \ll 1
$$
If we define $f(z) = \sum_{m=0}^\infty b(m) e^{2\pi i m z}$, we want to show $b(m) = 0$ for all $m = 0,1,2,3,\dots$ To show this, let's start with the following integral, which holds for all $y > 0$. 
$$
b(m) e^{-2\pi m y} = \int_0^1 f(x+iy) e^{-2\pi i m x}\;dx \implies b(m) = e^{2\pi m y} \int_0^1 f(x+iy) e^{-2\pi i m x}\;dx
$$
Putting absolute values, we get the following.
$$
\begin{align*}
|b(m)| &\leq e^{2\pi m y} \int_0^1 \left|f(x+iy) e^{-2\pi i m x}\right| \;dx \\
&\leq \frac{e^{2\pi m y}}{y^{\frac{k}{2}}}
\end{align*}
$$
We can take the $\lim_{y\rightarrow 0}$ to show that, for $k < 0$, 
$$
\lim_{y\rightarrow 0}\frac{e^{2\pi m y}}{y^{\frac{k}{2}}} = 0 \implies b(m) = 0
$$

-----

**Theorem:** $\dim(M_0) = 0$ 

**Proof:** Left as an exercise on HW $5$​ 

---

**Theorem (Intermediate):** $\dim(M_2) = 0$ 

**Proof:** Let $f \in M_2 \implies f\left(-\frac{1}{z}\right) = z^2 f(z)$. Let $z = i \implies f(i) = -f(i) \implies f(i) = 0$. 

Now, $f^2 \in M_4$. We already proved that $M_4$ has dimension $1$ (see below) $\implies f^2(z) = cE_4(z)$ for some $c \in \mathbb{C}$​.  

If we let $z = i$, and with the fact that $E_4(i) \neq 0$
$$
0 = cE_4(i) \implies c = 0
$$

---

**Theorem:** $\dim(M_4) = \dim(M_6) = \dim(M_8) = \dim(M_{10}) = 1$

In other words, in each $M_k$ for $k = 4,6,8,10$, there is only one modular form, namely $E_k$. 

**Proof:** Let $f \in M_k$ where $k = 4,6,8, 10$. 

Set $a_0 = \lim_{z \rightarrow i\infty} f(z)$. Consider the following function
$$
H(z) = \frac{f(z) - a_0 E_k(z)}{\Delta(z)}
$$
This function has weight $k - 12 < 0$. If $\Delta(z) = 0$, only for $z = i\infty \implies H(z) = 0$. 

-----

**Theorem:** Let $k \equiv 0 \text{ mod 2}$ with $k \geq 4$. Then,
$$
\dim(M_k) = \begin{cases}
	\left[\frac{k}{12}\right] + 1 &\text{if }k \not\equiv 2 \text{ mod }12 \\
	\left[\frac{k}{12}\right] &\text{if }k \equiv 2 \text{ mod }12 
\end{cases}
$$
Using $[x] = n$ where  $n$ is the large integer such that $x \geq n$. 

**Proof:** We already proved this for $k = 0,2,4,6,8,10$. Assume $f \in M_k (k \geq 12)$ with constant term $a_0 = \lim_{y \rightarrow \infty} f(iy)$. 
$$
\frac{f - a_0E_k}{\Delta} \in M_{k-12} \implies f - a_0 E_k = c\Delta \cdot g 
$$
where $g \in M_{k-12}$. So, the $\mathbb{C}$ linear map $\mathbb{C} \oplus M_{k-12} \to M_k$ is surjective and
$$
(c,g) \to_{\text{surjective}} cE_k + \Delta \cdot g
$$

---

**Claim:** The mapping above in $(11)$ is injective. 

**Proof:** We need to prove the Kernel of $(11)$ is $0$. If $c E_k + \Delta \cdot g = 0$, then looking at the constant terms of $E_k$ and $\Delta \cdot g$ , we know that $E_k$ has a non-zero constant $(2 \zeta(k))$ and $\Delta \cdot g$ has a zero constant term $\implies c = 0 \implies g= 0 $. 

We can just conclude that 
$$
\mathbb{C} \oplus M_{k-12} \cong M_k \implies \dim(M_k) = 1 + \dim(M_{k-12})
$$

---

#### L-function (Modular Form)

**Definition:** Let $f(z) = \sum_{n = 0}^\infty a(n) e^{2\pi i n z} \in M_k$. Then, we define
$$
L(s,f) := \sum_{n=1}^\infty a(n) \cdot n^{-s}
$$
**Ramanajan Conjecture**: Proved by Deligne!
$$
|a(n)| \ll n^{\frac{k-1}{2} + \epsilon}
$$
**Hecke:** This proof is easy!
$$
|a(n)| \ll n^{\frac{k}{2} + \epsilon}
$$
**Theorem:** Let $s \in \mathbb{C}$. Then $L(s,f)$ has a meromorphic continuation to all $\mathbb{C}$ with a most a simple pole at $\Re(s) = \frac{k+1}{2}$ if $a_0 \neq 0$. If $a_0 = 0$, then $L(s,f)$ is entire. Furthermore, $L(s,f)$ satisfies a functional equation $s \rightarrow k-s$ (?) 

**Idea (Hecke):** Take the Mellin transform at $f(1,y)$. 
$$
\int_0^\infty (f(iy) - a_0)y^s \; \frac{ds }{y} = \int_0^\infty \sum_{n=1}^\infty \underbrace{a_n e^{-2\pi n y} \;y^{s} \;\frac{dy}{y}}_{y \to \frac{y}{2\pi n}} = \sum_{n=1}^\infty a_n \cdot \frac{1}{(2\pi n)^s} \int_0^\infty e^{-y} y^s \frac{dy}{y} = (2\pi)^{-s} \Gamma(s) L(s,f)
$$
Now, use the modular relation.
$$
\begin{pmatrix} 0 & -1 \\ 1 & 0\end{pmatrix} z = -\frac{1}{z} \implies f\left(-\frac{1}{z}\right) = z^k f(z)
$$
