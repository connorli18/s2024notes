# [4/3] Algebra II

#### Review

**Theorem:** If $f \in F[x]$ where $\text{char} \;F = 0$ is solvalbe in radicals, then $\text{Gal}(E/F)$ is solvable. 

**Lemma:** Let $F$ be of $\text{char} \;0$, $F \leq E$ be the splitting field of some polynomial, then $E^{\text{Gal}(E/F)  } = \left\{ \alpha \in E \;:\; \forall \sigma \in \text{Gal}(E/F), \;\sigma(\alpha) = \alpha\right\} = F$. 

**Proof:** $E = F(\alpha_1, \dots, \alpha_n)$ where $\alpha_1, \dots, \alpha_n \notin F$ are roots of $f$. 

- We will show that for every $\alpha_i$, there exists $\sigma \in \text{Gal}(E/F)$ such that $\sigma(\alpha_i) \neq \alpha_i$. 

Let $f_i = \text{irr}(\alpha_i, F)$. Since $F$ is perfect, if $\deg (f_i) > 1$, there exists $\beta_i$ such that $f_i(\beta_i) = f(\alpha_i) = 0$, but $\beta_i \neq \alpha_i$. Now, examine the subfields
$$
F \leq F(\alpha_i) \leq E \quad \quad F \leq F(\beta_i) \leq E
$$
By the theorem of extending the isomorphism, there exist unique isomorphism $\sigma_1: F(\alpha_i) \to F(\beta_i)$ such that $\sigma_1(\alpha_i) = \beta_i$ and it can be extended to an isomorphism $\sigma_i: E \to E$. 
$$
F(\alpha_i) \to_{\sigma_i} F(\beta_i) \quad \quad \quad E \to_{\sigma_i} E
$$
This also means that $\sigma_i \in \text{Gal}(E/F)$ and $\sigma_i(\alpha_i) = \beta_i \neq \alpha_i$. 

---

**Question:** Given a subgroup $H \subset \text{Gal}(E/F)$, what can you say about $E^H$ ? 

<u>Example:</u> $\mathbb{Q} \leq \mathbb{Q}(\sqrt[3]{2}) \leq \mathbb{Q}(\sqrt[3]{2}, \omega)$ where $\text{Gal}(\mathbb{Q}(\sqrt[3]{2}/\mathbb{Q}) = \{1\}$. 

Given, $F \leq K \leq E$ we can associate $\text{Gal}(E/K) \leq \text{Gal}(E/F)$.

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-03 at 3.09.11 PM.png" alt="Screenshot 2024-04-03 at 3.09.11 PM" style="zoom:50%;" />

----

#### Normal Extension

**Proposition:** A field extension $F \leq E$ is called <u>normal</u> if any of the following equivalent conditions is true:

1. $E$ is a splitting field of some polynomial $f \in F[x]$ 
2. For any extension, $E \leq K$ and any homomorphism $\psi: E \to K$ which fixes $F$ pointwise, $\psi(E) = E$ (not necessarily pointwise)
3. Any irreducible $p \in F[x]$ that has root $\alpha \in E$ splits in $E$ 

**Proof (Part 1):** Lets first show $(1) \implies (2)$. Let $E$ be a splitting field of $f \in F[x]$, then $E = F(\alpha_1, \dots, \alpha_n)$ which are roots of $f$. 

For any $\psi: E \to K$ where $E \leq K$, If $f(\alpha) = 0$ where $f = \sum_{i} c_i x^i$ 
$$
0 = \psi(f(\alpha)) = \sum_{i} c_i \psi(\alpha)^i  \implies \psi(\alpha) 
\text{ is also a root}
$$
Since $\psi$ sends roots to roots, $\psi(E) = \psi(F(\alpha_1, \dots, \alpha_n)) = F(\psi(\alpha_1), \dots, \psi(\alpha_n)) \subset E$. 

**Proof (Part 2):** Now, let's show $(2) \implies (3)$. Let $p \in F[x]$ be an irreducible polynomial and $\alpha \in E$, $p(\alpha) = 0$. 
$$
F \leq E \leq K \quad \quad \quad K = \text{splitting field, }p \text{ splits in }K
$$
Let $\beta \in K$ be a root $p$. 
$$
F \leq F(\alpha) \leq E \leq K \quad \quad \quad F \leq  F(\beta) \leq K
$$
By extension of isomorphism theorem, $\exists \;\sigma_1 : F(\alpha) \rightarrow^{\cong} F(\beta)$ such that $\sigma_1$ fixes $F$ pointwise and it can be extended to $\sigma: K \to K$ such that
$$
F(\alpha) \rightarrow^{\sigma_1} F(\beta) \quad \quad \quad K \rightarrow^{\sigma} K
$$
Let $\psi = \sigma|_{E \leq K}$ be homomorphism $\psi: E \rightarrow K$. By (2),  $\psi (E) \subset E$ but $\beta = \sigma(\alpha) = \psi(\alpha)$ so $\beta \in E$. 

**Proof (Part 3):** Let's show $(3) \implies (1)$. Let $E = F(\alpha_1, \dots, \alpha_n)$, then define $E \leq \widetilde{E}$ to be the splitting field of $\text{irr}(\alpha_1, F)\; \cdots \; \text{irr}(\alpha_n, F)$, but by $(3)$,  $\text{irr}(\alpha_1,F)$ already splits in $E \implies \widetilde{E} = E$.  

----

#### Galois Extension

**Definition:** $F \leq E$ is called a <u>Galois extension</u> if 

- It is separable 
- It is normal

<u>Remark:</u> If $F$ is perfect (e.g. $\text{char }F = 0$ or $F = \mathbb{F}_q$ ), then $F \leq E$ is automatically separable. 

<u>Example:</u> The extensions used in the proof of solvability theorem are Galois.

**Corollary:** If $F \leq E$ is Galois, then $|\text{Gal}(E/F)| = [E : F]$ (this follows from the second part of extension of isomorphisms theorem). 

**Theorem:** (Main theorem of Galois Theory) Let $F \leq E$ be a Galois extension, then

$(1)$ The set of subgroups of $\text{Gal}(E/F) \cong$ the set of $F \leq K \leq E$ via the construction above, 
$$
H \rightarrow E^H \quad \quad \quad K \rightarrow \text{Gal}(E/K)
$$
The maps are inverses of each other in the sense that
$$
E^{\text{Gal}(E/K)} = K \quad \text{and} \quad \text{Gal}(E/E^H) = H
$$
$(2)$ This correspondence is order-reversing for inclusion $F \leq K \leq K' \leq E'$. 
$$
\text{Gal}(E/K') \leq \text{Gal}(E/K)
$$
$(3)$ $[E : E^H] = |H|$ and $|\text{Gal}(E/K)| = [E:K]$

$(4)$ $K$ is a normal field extension of $F \iff \text{Gal}(E/K)$ is a normal subgroup of $\text{Gal}(E/F)$   

**Proof:** Left for next class.

<u>Examples:</u> Consider $F \leq E$. 
$$
\mathbb{Q} \leq \mathbb{Q}(\sqrt{2}, \sqrt{3}) = \mathbb{Q}(\sqrt{2} + \sqrt{3}) = \mathbb{Q}[x] / (x^4 - 10x + 1)
$$
We also know that $\text{Gal}(E/F) = K_4 = \{1,\sigma_1, \sigma_2, \sigma_3\}$. 

|            | $\sigma_1$  | $\sigma_2$  | $\sigma_3$  |
| ---------- | ----------- | ----------- | ----------- |
| $\sqrt{2}$ | $-\sqrt{2}$ | $\sqrt{2}$  | $-\sqrt{2}$ |
| $\sqrt{3}$ | $\sqrt{3}$  | $-\sqrt{3}$ | $-\sqrt{3}$ |

- Subgroups of $K_4$: $\langle \sigma_1 \rangle$, $\langle \sigma_2 \rangle$,$ \langle \sigma_3 \rangle$, $\{ 1 \}$, $K_4$ 

We know that $F \leq E$ is a Galois extension. 

| $H$                        | $E^H$                           |
| -------------------------- | ------------------------------- |
| $\{1\}$                    | $\mathbb{Q}(\sqrt{2},\sqrt{3})$ |
| $K_4$                      | $\mathbb{Q}$                    |
| $\langle \sigma_1 \rangle$ | $\mathbb{Q}(\sqrt{3})$          |
| $\langle \sigma_2 \rangle$ | $\mathbb{Q}(\sqrt{2})$          |
| $\langle \sigma_3 \rangle$ | $\mathbb{Q}(\sqrt{6})$          |

