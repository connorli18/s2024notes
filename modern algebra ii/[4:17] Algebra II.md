# [4/17] Algebra II

#### Modules Over Rings

**Definition:** Let $R$ be a ring (communtative, with $1$). 

An abelian group $V$ is called an $R$-module if there is a multiplication map $\mu : R \times V \rightarrow V$ satisfying $\forall\;a,b \in R$ and $\forall \;v,w \in V$: 

1. $(a+b)v = av + bc$, $a(v+w) = av + aw$ 
2. $(ab)v = a(bv)$ 
3. $1 \cdot v = v$ 

**Examples:** Take the following examples of modules over rings. 

- $R$ is an $R$-module
- $R^n = \underbrace{R \times \cdots \times R}_{n\text{-times}}$ is an $R$-module where multiplication is component-wise. Also, $\overline{a} = (a_1, \dots, a_n) \in R^n $ 
- Any ideal $I \subset R$ is an $R$-module
- $R/ I$ is an $R$-module, i.e. $\mathbb{Z}/n\mathbb{Z}$ is an $\mathbb{Z}$-module
- Any abelian group is a $\mathbb{Z}$-module and vice versa.
  - **Proof:** Any $\mathbb{Z}$-module is an abelian group by definition. Let's define a $\mathbb{Z}$-module structure for any abelian group $V$. If $n > 0$ and $n \in \mathbb{Z}$, then $\mu(n,v) = \underbrace{v + \cdots + v}_{n\text{-times}}$ and if $n < 0$, $\mu(n,v) = \underbrace{(-v) + \cdots + (-v)}_{n\text{-times}}$ . Now, just check the axioms.
- Let $F$ be a field and $R = F[x]$. Also, let $V$ be an $F$-vector space and $A : V \to V$ be a linear operator. This implies that $V$ is an $R$-module where $f \in R= F[x]$ and 

$$
\mu(f, v) = \underbrace{f(A)}_{\sum_{i=0}^n c_iA^i \text{ if }f = \sum_{i=0}^{n} c_ix^i} \cdot v
$$

<u>Example:</u> $V = \mathbb{R}^2$, $A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$, $f = x^2 - 1$ 
$$
\mu\left(f,\begin{pmatrix} x \\ y \end{pmatrix}\right) = \left(A^2 - \text{Id}\right) \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 0 & 4 \\ 0 & 0\end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 4y \\ 0\end{pmatrix}
$$
Later, we will put the above 2 examples on equal footing to prove classification of $fg$ abelian groups and generalization of Jordan normal form for matrices.

-----

**Definition:** $U \subset W$ is a <u>submodule</u> if it is an abelina subgroup closed under multiplication by $R$​. 

**Definition:** Let $V,W$ be $R$-modules.

We say $\phi : V \to W$ is a homomorphism (like a linear map) of $R$-modules if 

- $\phi$ is an abelian group homomorphism, $\phi(a+b) = \phi(a) + \phi(b)$ 
- $\phi(ab) = \phi(a)\phi(b)$ 

<u>Exercise:</u> 

- $\text{Ker} (\phi) = \{v \in V \;:\; \phi(v) = 0\}$ is a submodule of $V$. 
- $\Im(\phi) = \{w \in W\;:\; \exists \;v\;; \phi(v) = w\}$ is a submodule of $W$. 

**Proposition:** Coset $W/\Im(\phi)$ is an $R$-module.

----

**Theorem:** (First Homomorphism Theorem)
$$
\Im(\phi) \cong \frac{V}{\text{Ker}(\phi)}
$$
**Proof:** Two modules are isomoprhic iff there exists an invertible homomorphism. Also, first homomorphism theorem for groups.

----

#### Free Modules & Matrices

**Remark:** Let $R \neq \{0\}$. 

Consider module homorphisms, $f : R^m \to R$. 

Example of such homomorphisms are given by matrices.
$$
\text{Mat}_{n\times m} (R) = \{a_{ij} \in R \text{ such that }  1 \leq i \leq n, \; 1 \leq j \leq m\}
$$

$$
v \in R^m  \implies A \cdot V \in R^m
$$

and the map is a homomorphism. 

**Definition:** (Invertible Matrices)

Set of all $n \times n$ invertible matrices with coefficients $\in R$ is denoted
$$
GL_n(R) \quad \quad \quad  \text{ general linear group}
$$

- It is a group with respect to multiplication

<u>Exercise:</u> There are no invertible $n \times m$ matrices where $n \neq m$ 

**Definition:** Let $A \in \text{Mat}_{n \times m}(R)$, then its determinant is $\det(A)  = \sum_{\sigma \in S_n} \text{sign}(\sigma) \cdot a_{1 \cdot \sigma(1)} \cdots a_{n \cdot \sigma(n)}$. 

----

**Proposition:** $\det(AB) = \det(A)\det(B)$ 

**Proof:** (word by word from Linear Algebra)

**Corollary:** $\det: \text{GL}_n(R) \to R^*$ is a group homomorphism where $R^*$ is a group of elements with multiplicative inverse. 

---

**Proposition:** $A \in GL_n(R) \iff \det(A)$ is invertible in $R$ ($\det (A) \in R^*$) 

**Proof:** $A$ is invertible $\implies A^{-1} \cdot A = \text{Id}_n$. 
$$
\det(A^{-1})\det(A) = \det(\text{Id}_n) = 1 \implies \det(A) \text{ is invertible}
$$
Recall, that for any matrix $A$, we can form $\text{adj} (A) = \text{cof}(A)$ which is constructed only by addition and multiplication constructed by addition and multiplication. 
$$
\text{adj}(A) \cdot A = \det(A) \cdot \text{Id}_n \implies A \text{ is invertible iff }\exists\;\delta \text{ s.t.} \;\delta \cdot \det(A) = 1 \in R \implies A^{-1} = \delta \cdot \text{adj}(A)
$$
<u>Example:</u> Let $A \in \text{Mat}_{n \times n}\mathbb{Z}$, then $A \in GL_n(\mathbb{Z}) \iff \det(A) = \pm 1$. 

**Remark:** There are still many invertible matrices, e.g. any upper triangular matrix is invertible over any ring.

----

#### Basis and Free Modules

**Definition:** We say $\{v_i\}_{i = 1}^n$ <u>generate</u> (<u>span</u>) an $R$-module $V$ if any $v \in V = a_1v_1 + \cdots + a_nv_n$ for some $a_1, \dots, a_n \in R$. 

**Definition:** We say that $v_1, \dots, v_n$ are <u>independent</u> if for any relation $a_1v_1 + \cdots + a_nv_n = 0 \implies a_1, \dots, a_n = 0$. 

**Definition:** $\{v_i\}_{i=1}^n$ is a basis of $V$ if it generates $V$ and is independent. 

**Remark:** Any set $\{v_1, \dots, v_k\} \subset V$ defines an $R$-module homomorphism 
$$
\phi: R^k \to V
$$

$$
\phi(a_1, \dots, a_n) \to a_1v_1 + \cdots + a_nv_n
$$

- $\{v_1, \dots, v_k\}$ generates $V \iff \phi$ is surjective.
- $\{v_1, \dots, v_k\}$ are independent $\iff \phi$ is injective.
- $\{v_1, \dots, v_k\}$ is a basis $\iff \phi$ is bijective (isomorphism)

**Definition:** An $R$-module $V$ is called a <u>free module</u> if it has a basis, $V \cong R^n$ for some $n$. 

<u>Exercise:</u> Every basis has the same $\#$ of elements, this number of elements in a basis of a free module is called <u>rank</u>. (Dimension of vector-space)

**Proposition:** Let $f : R^m \to R^n$ be a homomorphism of free modules, then $F(v) = Av$ for some $A \in \text{Mat}_{n \times m}(R)$. 

**Proof:** $f(v) = f(v_1c_1 + \cdots + v_mc_m) = v_1f(c_1) + \cdots v_mf(c_m) = \begin{pmatrix} f(c_1) & \cdots & f(c_m)\end{pmatrix}\begin{pmatrix} v_1 \\ \vdots \\ v_m\end{pmatrix}$.  



