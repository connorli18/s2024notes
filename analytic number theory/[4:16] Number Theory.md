# [4/16] Number Theory

#### Elliptic Functions

Before we introduced modular forms, we talked about $\overline{X}^G$ where group $G$ is acting on a topological space $\overline{X}$. 

**Definition: (Periodic Functions)** (Fourier analysis) $G = \mathbb{Z}$ and $\overline{X} = \mathbb{R}$ 
$$
f : \mathbb{Z}\backslash \mathbb{R} \rightarrow \mathbb{C} \quad \quad \quad \text{Fundamental Domain} = (0,1]
$$
**Definition (Modular Functions):** $G = SL(2,\mathbb{Z}),\;X = \mathfrak{h} = \{x + iy\;:\; y > 0,\;x \in \mathbb{R}\}$
$$
f: SL(2,\mathbb{Z})\backslash \mathfrak{h} \to \mathbb{C} \quad \quad \quad \text{Fundamental Domain} = \text{Strip in HW}
$$
**Definition (Elliptic Functions):** $G =$ Lattic $= \mathcal{L} = \omega_1 \mathbb{Z} + \omega_2\mathbb{Z}$ with $\omega_1, \omega_2 \in \mathbb{C}$ where $\frac{\omega_1}{\omega_2} \notin \mathbb{R}$.
$$
\mathcal{L} = \{m\omega_1 + n\omega_2 \;:\; m,n\in\mathbb{Z}\} = \text{additive group}
$$
The functions in this group are defined as follows
$$
f: \mathcal{L}\backslash \mathbb{C} \to \mathbb{C} \quad \quad \quad f(z+\omega) = f(z),\;\;\forall \omega \in \mathcal{L}
$$
We can think of these functions are doubly-periodic 
$$
\begin{cases}
	f(z+\omega_1) = f(z)\\
	f(z+\omega_2) = f(z)
\end{cases}
$$

---

<u>Note:</u> If $\frac{\omega_1}{\omega_2} \in \mathbb{R}$, then a doubly periodic function $f(z+\omega_1) = f(z+\omega_2) = f(z) $ is not very interesting.

- **Case (1)**: $\frac{\omega_1}{\omega_2} \in \mathbb{Q} \implies f$ is simply periodic satisfying $f\left(z + \frac{\omega_1}{q}\right)  = f(z)$ where $\frac{\omega_1}{\omega_2} = \frac{p}{q}$ with $p,q \in \mathbb{Z}$ where $(p,q) = 1$ 

  - **Proof:** Since $(p,q ) =1 \implies \exists\;m,n \in \mathbb{Z}$ such that $mp + nq = 1 \implies m\frac{p}{q} + n = \frac{1}{q} \implies m\frac{\omega_1}{\omega_2} + n = \frac{1}{q}$ . This then implies that $m\omega_1 + n\omega_2 = \frac{\omega_2}{q}$. 

    Since we also knwo that $f(z + \omega_1) = f(z + \omega_2) = f(z) \implies f(z + n\omega_1 + m\omega_2) = f(z) \implies f\left(z + \frac{\omega_2}{q}\right)$. 

- **Case (2):** $\frac{\omega_1}{\omega_2} \in \mathbb{R}$ but $\frac{\omega_1 }{\omega_2} \notin \mathbb{Q}$. 

  - **Claim:** Any doubly periodic function satisfying $f(z + \omega_1) = f(z+ \omega_2) = f(z)$ has to be the constant function $f(z) = c \in \mathbb{C}$.

  - **Proof:** Assume $\tau \in \mathbb{R}$ is irrational. For every $\epsilon > 0$, $\exists\;m,n \in \mathbb{Z}$ such that $\left|\tau - \frac{m}{n}\right|  < \epsilon$. 

    This implies that $|m \tau - n| < \epsilon$. 
    $$
    \begin{align*}
    
    &\implies \left|m\frac{\omega_1}{\omega_2} - n \right| < \epsilon\\
    &\implies \left|m\omega_! - n\omega_2\right| < \omega_2 \epsilon \\
    &\implies f(z) = f(z + m\omega_! - n\omega_2) = f(z + \epsilon\omega)\\
    &\implies f(z) \text{ is constant}
    \end{align*}
    $$

----

#### Liouville Theorems

Assume that $\frac{\omega_1}{\omega_2} \notin \mathbb{R}$. Want to study doubly periodic functions on the Lattice $\mathcal{L} = \{m\omega_1 + n\omega_2 \;:\; m,n \in \mathbb{Z}\}$. 

**Theorem: (Liouville Theorem 1)** A non-constant elliptic merimorphic function must have poles. Also, it cannot have a single pole (it must have more than $1$ pole). 

**Proof:** If we represent $\omega_1, \omega_2$ as vectors in $\mathbb{C}$, then we have that the parallelogram is a fundamental domain $\text{ mod }\mathcal{L}$. The fundamental domain only has half the boundary, but you can map any $\mathbb{C}$ into a point in the fundamental; domain.

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-16 at 3.20.48 PM.png" alt="Screenshot 2024-04-16 at 3.20.48 PM" style="zoom:50%;" />

If $f(z)$ is holomorphic $\implies f$ is bounded on $\mathcal{D} \implies f$ is bounded on all of $\mathbb{C}$. By Liouvilles theorem, this means that $f$​ is constant. 

---

**Theorem: (Liouville Theorem 2)** Let $\mathcal{L} = \{m\omega_1 + n\omega_2 \;:\; m,n\in\mathbb{Z}\}$ with $\frac{\omega_1}{\omega_2} \notin \mathbb{R}$. Assume $f : \mathbb{C} \backslash \mathcal{L} \to \mathbb{C}$ is a meromorphic function. Then, the sum of the residues is $0$. 
$$
\sum_{\rho \in \mathbb{C} \backslash \mathcal{L}} \Res_{z = \rho} \;f(z) = 0
$$
This then implies that $f$ cannot have a single pole.

**Proof:** We use Cauchy's Theorem where $C$ is the boundary of the parallelogram. 
$$
\frac{1}{2\pi i} \int_{C} f(z) \;dz = \sum_{\rho \in \mathbb{C}/\mathcal{L}} \Res_{z = \rho} \;f(z) = 0
$$
If $f(z)$ is meromorphic near $\rho \implies f(z) = \sum_{k=-N}^\infty c_k(z-p)^k \implies \Res_{z=\rho} \;f(z) = c_{-1}$. 

----

**Theorem: (Liouville Theorem 3)** This concerns the order of a pole. 

Let $f(z)$ be a meromorphic function on $\mathbb{C}$. We say $f$ has a pole of order $N$ at $\rho \in \mathbb{C}$ if
$$
f(z) = (z-\rho)^{-N} \cdot h(z) \implies \underbrace{\mathcal{V}_p(f) = -N}_{\text{notation for order of pole}}
$$
where $h(z)$ is holomorphic on $|z - \rho| < \epsilon$ for $\epsilon > 0$ sufficiently small. This implies that
$$
\frac{f'}{f}(z) = \frac{-N}{z-\rho} + \frac{h'}{h}(z)
$$
<u>Remark:</u> If $\mathcal{V}_{\rho}(f)$ is positive, then it equals the order of a zero!

**Proof:** Use Cauchy's Theorem again to show that
$$
\frac{1}{2\pi i } \int_{C} \frac{f'}{f}(z) \;dz = \sum_{\rho \in \mathbb{C}\backslash \mathcal{L}} \mathcal{V}_{\rho}(f) = 0 \implies f \text{ has same number of poles as zeroes}
$$
**Corollary:** Let $\alpha \in \mathbb{C}$. The number of $p \in \mathbb{C}\backslash \mathcal{L}$ such that $f(p) = \alpha$ is the same for any $\alpha \in \mathbb{C}$. 

**Proof:** We will use Liouville's third theorem. 

First, consider $f(z) = 0$, $\#\text{ zeroes} = \#\text{ poles}$. Now, consider $f(z) - a = 0$ where $\# \text{ zeroes} = \# \text{ poles}$. This means that the number of poles must be the same!