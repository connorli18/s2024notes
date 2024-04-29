# [4/29] Algebra II

#### Review

**Definition:** An $R$-module $V$ is called free if there is a basis or there exists an isomorphism $R^n \rightarrow^{\cong B} V$. 

**Definition:** We say that an $R$-module is <u>presented</u> by $A \in \text{Mat}_{n \times m} (R)$ if there exists $R^m \rightarrow^A R^n \twoheadrightarrow V$. 
$$
R^m \twoheadrightarrow W \hookrightarrow R^n \twoheadrightarrow V
$$
 where $W$ is an $R$-module of relations. 

<u>Notation</u>: In terms of arrows,

- $\cong$ is an isomorphism
- $\twoheadrightarrow$ is a surjection
- $\hookrightarrow$ is an injection.

In particular, $V \cong R^n / AR^m$. 

<u>Example</u>: $\mathbb{Z} \rightarrow^5 \mathbb{Z} \twoheadrightarrow \mathbb{Z}/5\mathbb{Z}$​

----

**Definition:** $R$ is called Noetherian if every $I \subset R$ is finitely generated. 

<u>Example</u>: Any PID is Noetherian. $\mathbb{Z}, F[x]$ are PID $\implies$ Noetherian.

**Fact:** If $R$ is Noehterian, then every submodule $W$ of a finitely generated $R$-module $V$​ is also finitely generated. 

-----

**Corollary:** Every finitely generated $R$-module for $R$ Noetherian has a presentation by a matrix.

**Theorem:** Let $A \in \text{Mat}_{n \times m} (\mathbb{Z})$, then there exist invertible matrices $Q, P$ (where $Q^{-1}$ are row operations and $P$ are column operations) such that $Q^{-1} AP = $ 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-24 at 3.22.08 PM.png" alt="Screenshot 2024-04-24 at 3.22.08 PM" style="zoom:25%;" />

where $d_i > 0$, such that $d_1 \mid d_2, \; d_2 \mid d_3,\; \dots, \;d_{k-1} \mid d_k$.  

**Idea of Proof:** Gauss-Jordan + division with remainder. See last class for proof!

----

**Definition:** Let $V_1, V_2 \subset V$ be $R$-submodules. We say $V = V_1 + V_2$ if $\forall\; v \in V$ can be written as $v = v_1 + v_2$ where $v_1 \in V_1$ and $v_2 \in V_2$. 

**Definition:** $V$ is called a direct sum if $V = V_1 \oplus V_2$ in addition if $v = 0 \implies v_1 = v_2 = 0$. 

**Theorem:** Let $V$ be a finitely generated $\mathbb{Z}$-modules, then $V \cong C_{d_1} \oplus \cdots \oplus C_{d_k} \oplus \mathbb{Z}^{n-k}$ for $C_{d_i}$ denoting a cyclic abelian group $\mathbb{Z}/d_i\mathbb{Z}$ and $d_i | d_{i+1}$ for all $i$ and $n \geq k$. 

**Proof:** $\mathbb{Z}$ is Noetherian $\implies V$ has a presentation $V \cong \mathbb{Z}^n / A\mathbb{Z}^m $. Diagonalizing $A \implies Q^{-1}AP =$

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-24 at 3.22.08 PM.png" alt="Screenshot 2024-04-24 at 3.22.08 PM" style="zoom:25%;" />

where $Z^m \rightarrow^{A^m} \mathbb{Z}^n \twoheadrightarrow^{B} V$. 

Then, we can write another presentation of $V$ by the matrix $\tilde{A}$ where $\tilde{A}=$ 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-29 at 3.15.15 PM.png" alt="Screenshot 2024-04-29 at 3.15.15 PM" style="zoom:50%;" />

The number of rows in both matrices $A, \tilde{A}$ is $n$. 

Now, consider a $\mathbb{Z}$-module homomorphism $C_{d_1} \oplus \cdots \oplus C_{d_k} \oplus \mathbb{Z}^{n-k} \twoheadrightarrow V$ given by
$$
\phi: ([i_1], \dots, [i_k], i_{k+1}, \dots ,i_{n}) \rightarrow i_1v_1 + \cdots + i_nv_n
$$
 where $v_1, \dots, v_n$ is the generating set $B$. 

----

To determine the kernel of $\phi$, we notice that if $i_1v_1 + \cdots + i_nv_n = 0 \implies (i_1, \dots, i_n)$ is a linear combination of columns of $\tilde{A}$. 
$$
\begin{align*}
 &\implies d_1 \mid i_1, \dots, d_k\mid i_k, \;i_{k+1} = \cdots = i_n = 0 \\
 &\implies [i_1]v_1 + \cdots + [i_k]v_k + i_{k+1}v_{k+1} + \cdots + i_nv_n = 0\\
&\implies 0 \in C_{d_1} \oplus \cdots \oplus C_{d_k} \oplus \mathbb{Z}^{n-k} \\
&\implies \text{ker}(\phi) = 0
\end{align*}
$$
**Remark:** As a result, we have the following two properties.

1. If $V$ is finite $\implies n = k$
2. $C_{a \cdot b} = C_a \oplus C_b$ if $(a,b) = 1$ so we can also further write

$$
V \cong C_{p_1^{k_1}} \oplus \cdots \oplus C_{p_\ell^{k_\ell}} \oplus \mathbb{Z}^{n-k}
$$

​	where $p_1, \dots, p_\ell$ are prime and $k_1, \dots, k_\ell > 0$. 

------

#### Field of Polynomials

Now, let us repeat the argument for $R = F[t]$ where $F$ is a field.

**Theorem:** Let $A \in \text{Mat}_{n \times m}\left(F[t]\right)$, then there exists monic polynomials $f_1, \dots, f_k$ such that $f_1 \mid f_2, \dots, f_{k-1} \mid f_k$ and invertible $Q^{-1}, P$ such that $Q^{-1}AP = $

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-24 at 3.22.08 PM.png" alt="Screenshot 2024-04-24 at 3.22.08 PM" style="zoom:25%;" />

where $d_1, \dots, d_k$ are actually $f_1, \dots, f_k$. 

**Proof:** This word-by-word repeats $R = \mathbb{Z}$. (Gauss Jordan algorithm + division with remainder). 

<u>Example</u>: Assume $F = \mathbb{Q}$. 
$$
\begin{align*}
A =& \begin{pmatrix} t^2 - 3t + 1 & t-2 \\ (t-1)^3 & t^2 - 3t + 2\end{pmatrix} \implies \begin{pmatrix} t^2 - 3t + 1 & t-2 \\ t^2 - t & 0\end{pmatrix} \implies \begin{pmatrix} -1 & t-2 \\ t^2 - t & 0\end{pmatrix}\\
\implies& \begin{pmatrix} -1 & 0 \\ t^2 - t & t^3 - 3t^2 + 2t\end{pmatrix} \implies \begin{pmatrix} 1 & 0 \\ 0 & t(t^2 - 3t + 2)\end{pmatrix}
\end{align*}
$$
**Definition:** Let $F$ be a ring, we say $C$ is a <u>cyclic</u> $R$-module if it is generated by one element $\implies C \cong R/I$. 

If $R$ is a PID $\implies C = C_f = R/(f)$ for some $f \in R$. 

**Theorem:** Let $V$ be a finitely generated $F[t]$ module, then 
$$
V \cong C_{f_1} \oplus C_{f_2} \oplus \cdots \oplus C_{f_k} \oplus \left(F[t]\right)^{n-k}
$$
where $f_1 \mid f_2, \dots, f_{k-1} \mid f_k$ are monic polynomials $C_{f_i} = F[t]/(f_i)$ 

**Corollary:** If $(f,g) = 1 \implies C_{f \cdot g} \cong C_f \oplus C_g \implies $​ we can further decompose 
$$
V \cong C_{p_1^{k_1}}\oplus \cdots \oplus C_{p_\ell^{k_\ell}} \oplus \left(F[t]\right)^{n-k}
$$


where $p_i$ are monic irreducibles $k_i > 0$. 

----

Let $V$ be an $F[t]$ module. Then, define
$$
T : V \rightarrow V
$$
given by $v \rightarrow t \cdot v \in V$. Since $V$ is a module,

1. $T(v+ w) = T(v) + T(w)$
2. $T(cv) = cT(v)$, $0 \in F$ 

This implies that $T: V \rightarrow V$ is an $F$-linear operation. Vice versa, given $T: V \to V$ linear, $V$ has a structure of $F[t]$-module by $\left(\sum a_it^i\right) \to \sum_{i} a_iT^i(v) \in V$. 
$$
\{F[t]\text{-modules}\}  = \{\text{linear operators}\; T:V \to V\}
$$
<u>Example</u>: Let $T: F \to F$ be a linear operator on $V$. Then $V \cong C_{p_1^{k_1}} \oplus \cdots \oplus C_{p_\ell^{k_\ell}}$. 

Assume $p_1 = t - \lambda_1, \dots, p_\ell = t - \lambda_\ell$ where $k_1 = \cdots = k_\ell = 1$. 
$$
C_{p_i} = F[t] / (t - \lambda_i)
$$
We have a presentation $F[t]^\ell \rightarrow^{\tilde{A}} F[t]^\ell \rightarrow V$. Choose an $F$-basis of $V$ compatible with the presentation. Then, the $F$-matrix of $T$ is as follows.

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-29 at 3.55.40 PM.png" alt="Screenshot 2024-04-29 at 3.55.40 PM" style="zoom:33%;" />

Assume $F = \mathbb{C} \implies $ any irreducible polynomial is $p_i = t - \lambda_i$. Any f.d. $F[t]$-module is $C_{p_1^{k_1}}  \oplus \cdots \oplus C_{p_\ell^{k_\ell}} $ . 
$$
T = [\text{matrix above}] \quad \quad \text{where each block corresponds to }C_{p_i^{k_i}} 
$$
