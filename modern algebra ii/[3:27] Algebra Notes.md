# [3/27] Algebra Notes

#### Solvability in Radicals

**Definition:** An extension $F \leq B$ is called a pure/simple radical extension of type $n$ if $B = F(\alpha)$ such that $\alpha^n \in F$. 

**Definition:** An extension $F \leq B$ is called a radical extension if there exists a tower of extensions 
$$
F \leq B_0 \leq B_1 \leq \cdots \leq B_t = B
$$
where every extension in the tower is a simple radical extension. 

**Definition:** We say $f \in F[x]$ is <u>solvable in radicals</u> if the splitting field $E$ of $f$ is a subfield in a radical extension of $F$. 

<u>Remark:</u> $f$ is solvable in radicals $\iff$ every root $\alpha_i \in E$ of $f$ can be written as an algebraic expression using field operations and elements of $F$. 
$$
+\;, \;-\;,\; \circ\;,\;/\;, \;\sqrt[n]{\cdot}
$$

---

**Question:** What are the implications of solvability in radicals for $\text{Gal}(E/F)$?

<u>Simple Case:</u> Let $F = B_0 \leq B_1 \leq \cdots \leq B_t = B$ be the radical extension of $F$ such that each $B_{i-1} \leq B$ is a sure pure extension of type $n_i$. 

- $F$ contains all $n_i$-th roots of $1$ 
- Each $B_i$ is a splitting field of some polynomial $\in F[x]$ 

Now, define $G_i = \text{Gal}(B/B_i)$, then
$$
G_0 \rhd G_1 \rhd G_2 \rhd \cdots \rhd G_t  = \text{Gal}(B/B) = \{\text{id}\}
$$
*Recall:* The following theorem shows why these groups are normal $\rhd$. $F \leq K \leq E$ such that $K,E$ are splitting fields of some polynomials in $F[x]$, then $\text{Gal}(E/K) \lhd \text{Gal}(E/F)$ and $\text{Gal}(E/F) / \text{Gal}(E/K) \cong \text{Gal}(K/F)$. 

By the same theorem,
$$
G_{i-1}/ G_i = \text{Gal}(B/B_{i-1}) / \text{Gal}(B/B_i) \cong \text{Gal}(B_i/B_{i-1})
$$
Recall, that we have $B_i = B_{i-1} (\alpha_{i-1})$ where $\alpha_{i-1}^{n_i} \in B_{i-1}$. In particular, the following polynomial has a root in $B_i$.
$$
x^{n_i} - (\alpha_{i-1})^{n_i}
$$
By assumption, 1) $x^{n_i} - (\alpha_{i-1})^{n_i}$ splits in $B_i$ as 
$$
\prod_{k=0}^{n_i-1}  (x - \underbrace{\omega^k}_{\omega = e^{\frac{2\pi i}{n}}} \alpha_{i-1})
$$
where $\omega$ is a primitive $n_i$-th root of $1 \implies B_i$ is the splitting field of $x^{n_i} - (\alpha_{i-1})^{n_i}$. Then, $\text{Gal}(B_i/B_{i-1})$ is isomoprhic to some subgroup of $\mathbb{Z}/n_i\mathbb{Z}$. In particular, it is abelian!

As a result, $G_0 = \text{Gal}(B/F)/Gal(B/E) \cong \text{Gal}(E/F)$ where
$$
G_0 \rhd G_1 \rhd \cdots \rhd G_t = \{1\}
$$
such that $G_{i-1}/G_i$ is abelian for all $i$​. 

----

**Definition:** Group $G$ is called <u>solvable</u> if there exists 
$$
G_0 \rhd G_1 \rhd G_2 \rhd \cdots \rhd G_t = \{1\}
$$
such that $G_{i-1}/G_i$ is abelian for all $i$. 

**Proposition:** If $G$ is solvable and $H \lhd G_i$, then $H, G/H$ are solvable. 

**Corollary:** If $f$ is solvable in radicals, where the radical extension satisfies our assumptions 1) 2), then the $\text{Gal}(E/F)$ is solvable. 

**Remark:** $\mathbb{Z}/2\mathbb{Z} \cong S_2$ is solvable.

$S_3 \rhd A_3 \cong \mathbb{Z}/3\mathbb{Z} \rhd \{1\}$ is solvable.

$S_4 \rhd A_4 \rhd K_4 \rhd \{1\}$ is solvable.

$S_5$​ is not! 

----

**Theorem:** Let $\text{char\;} F = 0$ and $f \in F[x]$ be solvalbe in radicals, then $\text{Gal}(E/F)$ is solvable.

**Proof:** Let us start from radical extension
$$
F = B_0 \leq B_1 \leq \cdots \leq B_t = B
$$
such that each $B_{i-1} \leq B_i$ is of type $n_i$. Let $\omega$ be a primitiveroot of $1$ of order $\text{lcm}(\left\{n_i\right\}_{i=1}^t)$, then $F(\omega)$ contains all $n_i$-th roots of $1$ and so are $B_i(\omega)$. 

Moreover, $F(\omega) \leq B_i(\omega) \leq \cdots \leq B_t(\omega)$ is a radical extension of $F(\omega)$ satisfiying assumption 1). Now, consider the extension
$$
F \leq F(\omega \leq \cdots \leq B_t(\omega)
$$
This means that 
$$
\text{Gal}(B_t(\omega)/F) / \text{Gal}(B_t(\omega) / F(\omega)) = \text{Gal} (F(\omega)/F) \rightarrow_{\text{embeds}} U(\mathbb{Z}/\text{lcm}\{n_i\}\mathbb{Z}) \implies \text{abelian}
$$
To get rid of the assumption 2) we construct a different tower of field extensions
$$
F = R_0 \leq R_1 \leq \cdots \leq R_t = R
$$
such that $E \leq R$ and $\text{Gal}(R/R_{i-1})/\text{Gal}(R/R_i) \cong \text{Gal}(R_i/R_{i-1})$ are abelian. By part I of the proof, without loss of generality we can assume that $F$ contains all $n_i$-th roots of $1$. 

Define $R_1 = B_1 = F(\alpha_0)$ where $\alpha_0^{n_1} \in F$. Since $F$ contains $n_1$-th roots of $1$, then 
$$
x^{n_1} - (\alpha_0)^{n_1} = \prod_{k=0}^{n_1-1} (x-\omega^k \alpha_0)
$$
splits in $R_1$ where $\omega =$ primitive $n_1$-st root of $1$. In particular, $R_1$ is the splitting field of $x^{n_1} - (\alpha_0)^{n-1} \in F[x]$.  

By induction, assume we contstruct $R_i$ such that $B_i \leq R_i$ and $R_i$ is the splitting field of some polynomial such that $\text{Gal}(R_i/R_{i-1})$ is abelian. Let's construct $R_{i+1}$. 

Let $\widetilde{R_{i+1}} = R_i(\alpha_i) \iff B_{i+1} = B_i(\alpha_i)$. Then, $\widetilde{R_{i+1}}$ is the splitting field of $x^{n_{i + 1}} - (\alpha_i)^{n_{i+1}} \in B_i[x] \subset R_i[x]$.

Define the following
$$
f_i = \prod_{\sigma \in \text{Gal}(B_i/F)} (x^{n_{i+1}} - \sigma(\alpha_i)^{n_{i+1}}) \in F[x]
$$
 By construction, $\tau(f_i) = f_i$ for any $\tau \in \text{Gal}(B_i / F)$. Define $R_{i+1}$ to be the splitting field of $f_i$. 



