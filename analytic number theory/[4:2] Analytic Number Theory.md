# [4/2] Analytic Number Theory

#### Eisenstein Series

**Definition:** We define the following series and it converges for $k = 4,6,8,10,\dots$
$$
E_k(z) := \sum_{\substack{c,d \in \mathbb{Z}\\ (c,d) = 1}} \frac{1}{(cz+d)^k}
$$
**Limit Bound:** Last class, we proved
$$
\lim_{z\rightarrow i\infty} E_k(z) = 2
$$

$$
E_k\left(\frac{az+b}{cz+d}\right) = (cz+d)^k E_k(z)
$$

Since $\begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \in SL(2,\mathbb{Z}) \implies E_k(z+1) = (0+1)^k E_k(z) = E_k(z)$. 
$$
E_k(z) = \sum_{n=0}^\infty a_k(n) e^{2\pi i n z} \quad \quad a_k(0) = 2
$$
 **Definition: (Cusp Form)** $f: \mathcal{Y} \rightarrow \mathbb{C}$ holomorphic at $\infty$. 
$$
\lim_{z\rightarrow i\infty}f(z) = 0 \implies f(z) = \sum_{n=1}^\infty a(n)e^{2\pi i n z}
$$
**Question:** Do cusp forms exist? <u>YES!</u> Below is a cusp form of weight $12$. 
$$
2 \cdot \underbrace{(E_6)^2(z)}_{\text{constant term} = 4}  - \underbrace{(E_4)^3(z)}_{\text{constant term}=8 }
$$
If we take the above expression, we can turn it into a Fourier transform.
$$
\underbrace{\sum_{n=1}^\infty \tau(n)\; e^{2\pi i n z}}_{\tau(1) = 1}  = 2 \cdot (E_6)^2(z)  - (E_4)^3(z)
$$

| $n$       | **1** | **2** | 3    | 4     | 5    | 6     | 7      |
| --------- | ----- | ----- | ---- | ----- | ---- | ----- | ------ |
| $\tau(n)$ | 1     | -24   | 252  | -1472 | 4830 | -6048 | -16744 |

**Ramanujan Conjectures:**

1. $\tau(mn) = \tau(m) \cdot \tau(n)$ if $(m,n) = 1$ 
2. $\tau(p^k) = \tau(p) \tau(p^{k-1}) - p^{11} \tau(p^{k-2})$ for $k \geq 2$ 
3. $|\tau(p)| \leq 2 \cdot p^{\frac{11}{2}}$ 

---

#### Ramanujan Conjectures:

**Definition (class):**
$$
E_k(z) = \sum_{(c,d) = 1} \frac{1}{(cz + d)^k}
$$
**Definition (Serre's):** Different from the one in class!
$$
\widetilde{E_k}(z) := \sum_{\substack{c,d \in \mathbb{Z}\\ (c,d) \neq (0,0)}} \frac{1}{(cz+d)^k} = \zeta(k) \cdot E_k(z)
$$

$$
2 \cdot \zeta(4)^3 \cdot (\widetilde{E_6})^2(z) - \zeta(6)^2 (\widetilde{E_4})^3(z)
$$

**Proof:** Let's show first via an expansion,
$$
\widetilde{E_k}(z) = \sum_{(c,d) \neq (0,0)} \frac{1}{(cz+d)^k} = \sum_{n=0}^\infty a_k(n)e^{2\pi i n z} \quad \quad a_k(0) = 2 \cdot \zeta(k)
$$
Using Fourier theory, we also have
$$
\begin{align*}
a_k(n) e^{-2\pi n y} &= \int_0^1 \widetilde{E_k}(x + iy) e^{-2 \pi i n x}\;dx\\
&= \int_0^1 \sum_{c\neq 0} \sum_{d=-\infty}^\infty \frac{e^{-2\pi i n x}}{(\underbrace{cx + d + icy}_{d = \ell c + r \;(1 \leq r \leq c)})^k} \;dx\\
&= \int_0^1 \sum_{c \neq 0} \sum_{\ell = -\infty}^\infty \sum_{r=1}^c \underbrace{\frac{e^{-2\pi i nx}}{(cx + c\ell + r + icy)^k}}_{x \mapsto x - \ell - \frac{r}{c}} \;dx\\
&= \sum_{c \neq 0} \sum_{\ell = -\infty}^\infty \sum_{r=1}^c \int_{-\ell - \frac{r}{c}}^{-\ell - \frac{r}{c} + 1} \frac{e^{2\pi i n (x - \ell - \frac{r}{c})}}{(cx + icy)^k}\\
&= \sum_{c \neq 0} \sum_{r=1}^c \int_{-\infty}^\infty \frac{e^{-2\pi i n (x - \frac{r}{c})}}{(x+iy)^k}\;dx\\
&= \sum_{c\neq 0}\sum_{r=1}^c \frac{e^{\frac{2\pi i n r}{c}}}{c^k} \cdot \int_{-\infty}^\infty \frac{e^{2\pi i n x}}{(x+iy)^k}\;dx\\
&= \sum_{c|n} \frac{1}{c^{k-1}} \int_{-\infty}^\infty \frac{e^{-2\pi i n (x+ iy)}}{(x+iy)^k} \cdot e^{-2\pi n y}\\
a_k(n) &=  \sum_{c|n} \frac{1}{c^{k-1}} \int_{-\infty}^\infty \frac{e^{2\pi i n (x + iy)}}{(x+iy)^k}\;dx\\
&= \frac{(-2\pi i n)^{k-1}}{(k-1)!}
\end{align*}\\
$$
We can evaluate this by the Cauchy Reimann equation with a pole at $x = -iy$ and also using the Taylor Series expansion.
$$
\begin{align*}
\frac{e^{-2\pi i n (x + iy)}}{(x+iy)^k} &= \frac{\sum_{\ell = 0}^{\infty} \frac{(-2\pi i n ( x + iy))^\ell}{\ell \; !}}{(x+iy)^k} \\
&= \frac{(2\pi i n )^{k-1}}{(k-1)! ( x+iy)} + \text{Other Terms}
\end{align*}
$$
<u>Remark:</u>
$$
\widetilde{E_k}(x + iy) = 2\cdot \zeta(k) + \sum_{c \neq 0} \sum_{d} \frac{1}{(cz+d)^k}
$$

$$
\sum_{r=1}^c e^{\frac{2\pi i n r}{c}} = \begin{cases} 0 &\text{if } c \nmid n \\
c &\text{if } c\mid n
\end{cases}
$$

This means that we can show the complete theorem. 

**Theorem:** $\widetilde{E}_k(z) = \sum_{n=0}^\infty a_k(n) e^{2\pi i n z}$ where $a_0(n) =  2 \cdot \zeta(k)$ and $a_k(n) = \sum_{c|n} \frac{1}{c^{k-1}} \cdot \frac{(-2\pi i n)^k}{(k-1)!}$ for $n = 1,2,3,\dots$

---

**Example:** Let's define some function
$$
F(z) = 2 \cdot \zeta(4)^3 \cdot \widetilde{E}_6^2(z) - \zeta(6)^2 \cdot \widetilde{E}_4^3 (z) \implies F(z) = \sum_{n=1}^\infty c(n) e^{2\pi i n z}
$$
**Ramanujan Formula:** We have that
$$
\Delta(z) = \sum_{n=1}^\infty \tau(n) e^{2\pi i n z} = \left(e^{\frac{2\pi i z}{24}} \prod_{n=1}^\infty \left(1-e^{2\pi i n z}\right)\right)^{24}
$$
