# [4/24] Algebra II Notes

#### Modules Over Rings

**Definition:** Let $R$ be a ring, $V$ is called an $R$-module if it is an abelian group and there is an operation $\mu : R \times V \to V$ satisfying the natural associativity and distributivity conditions.

----

**Definition:** Let $\{v_1, \dots, v_n\} \subset V$. We can define a module homomorphism 
$$
\phi: R^n \to V \quad \quad \quad \phi(\underbrace{c_1, \dots, c_n}_{\in R^n}) = \sum_{i=1}^n \underbrace{c_iv_i}_{\in V}
$$

- We say $\{v_1, \dots, v_n\}$ <u>generates</u> $V$ if $\phi$ is <u>surjective</u>. 
- $\{v_1, \dots, v_n\}$ are <u>independent</u> if $\phi$ is <u>injective</u>
- $\{v_1, \dots, v_n\}$ is a <u>basis</u> of $V$ if $\phi$ is <u>bijective</u>.

**Remark**: Not every module has a basis even if there is a finite set of generators. 

<u>Example:</u> $\mathbb{Z}/n\mathbb{Z}$ is a $\mathbb{Z}$-module with generator $1$, but
$$
\phi: \mathbb{Z} \rightarrow \mathbb{Z}/n\mathbb{Z} \text{ is not injective}
$$
**Definition:** We say that $V$ is a <u>free module</u> if it has a basis.

**Proposition:** The cardinality of any basis of a free module is called the <u>rank</u> of $V$. Every basis has the same cardinality!

**Proposition:** Every $R$ module homomoprhism from $R^m$ to $R^n$ is given by multiplication by a matrix.

<u>Example</u>: Let $\phi: V \to W$ be a homomorphism of free $R$-modules of ranks $m$ and $n$ respectively. 

Let $B = \{v_1, \dots, v_m\}$ be a basis of $V$ and $C = \{w_1, \dots w_n\}$ be a basis of $W$. 

Then, we can represent the transformation $\phi$ by an $n \times m$ matrix with coefficients in $R$. 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-23 at 12.24.49 PM.png" alt="Screenshot 2024-04-23 at 12.24.49 PM" style="zoom:50%;" />
$$
\text{composition of }R\text{-modules homomorph} \implies A = C^{-1}\phi B
$$
**Change of Basis:** Consider the following diagram where $P, Q$ are invertible $m \times m$ or $n\times n$ matrices.

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-23 at 12.58.58 PM.png" alt="Screenshot 2024-04-23 at 12.58.58 PM" style="zoom:50%;" />

$A'$ is a matrix at transformation $A$ under the changes of basis $P$ in the domain and $Q$ in the range.
$$
\underbrace{A' = Q^{-1}AP}_{\text{Systems of Equations in }R\text{-modules}}
$$

----

#### Solving Particulars

Let $V,W$ be a $R$-modules and $\phi: V \to W$ be a homomorphism. Consider the following equation
$$
\phi(x) = b \quad \quad \text{ where }x \in V, b \in W
$$

- Any solution to $\phi(x) = b$ is given by a combination of a partial solution to $\phi(x) = b$ and the general solutiuon to $\phi(x) = 0$ 
  - $\phi(x) = 0$, Set of solutions forms a submodule of $V$ call $\text{Ker} \;\phi$ 
  - Set of all $b$ such that $\exists \;x \in V$ where $\phi(x) = b$ is called the image of $\phi$ and is a submodule of $W$ 

From now on, let's assume $R = \mathbb{Z}$ and $V,W$ are free $\mathbb{Z}$-modules (free abelian groups). By choosing bases for $V, W$, we can assume that $V \cong \mathbb{Z}^m$, $W = \mathbb{Z}^n$. Then, $\phi$ is represented by a matrix
$$
A \in \text{Mat}_{n\times m}(\mathbb{Z})
$$
and we can rewrite our equation as $Ax = b$, $x \in \mathbb{Z}^m,\; b \in \mathbb{Z}^n$. 

**Row and Column Reductions:** (for matrices with integral coefficients) Recall, if $A \in \text{Mat}_{n \times m}(\mathbb{R})$, then one can always reduce it to RREF by elementary row operations. 

1. Multiplication by a non-zero scalar
2. Switching the rows
3. Add $c \cdot (\text{one row})$​ to another
4. Invert any of the 3 above operations

For $R$-modules, 1) has to be replaced by multiplication by invertible elements. 2),3) are unchanged!

For real-valued matrices RREF has the following form.

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-23 at 1.20.59 PM.png" alt="Screenshot 2024-04-23 at 1.20.59 PM" style="zoom:50%;" />

For matrices with coefficients in a ring, RREF is not always achievable.

<u>Example:</u> $A = \begin{pmatrix} 1 & 2 & 3  \\ 4 &5 &6 \end{pmatrix} \in \text{Mat}_{2 \times 3}(\mathbb{Z})$ 
$$
\begin{pmatrix}
	1 & 2 & 3 \\
	0 & -2 & -6
\end{pmatrix} \to \begin{pmatrix}
	1 & 2 & 3 \\
	0 & 2 & 6
\end{pmatrix} \to \begin{pmatrix}
	1 & 0 & -3 \\
	0 & 2 & 0
\end{pmatrix}
$$
The issue with the above is that $2$ is not invertible in $\mathbb{Z}$. 

**Proposition:** Any $n \times m$ matrix with real coefficients can be reduced ot the form 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-23 at 1.24.55 PM.png" alt="Screenshot 2024-04-23 at 1.24.55 PM" style="zoom:50%;" />

 where $k = \text{rank} \; A$ (linear algebra).

**Remark:** We can write $A'$ as follows such that
$$
A' = Q^{-1}AP
$$
where $Q^{-1}$ is a composition of elementary matrices of row operations and $P$ is a composition of column operations. 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-23 at 1.27.27 PM.png" alt="Screenshot 2024-04-23 at 1.27.27 PM" style="zoom:50%;" />

**Theorem:** Let $A \in \text{Mat}_{n \times m}(\mathbb{Z})$. Then, by integral row and column operations, we can reduce it to the form 

<img src="/Users/connorli/Library/Application Support/typora-user-images/Screenshot 2024-04-23 at 1.28.52 PM.png" alt="Screenshot 2024-04-23 at 1.28.52 PM" style="zoom:50%;" />

where $k = \text{rank} \; A$ and $d_1, \dots, d_k \in \mathbb{Z}$ such that $d_i | d_2, \;d_2 | d_3,\dots, \;d_{k-1}| d_k$. 

<u>Example:</u> $A = \begin{pmatrix} 2 & 5 & -2 \\ 3 & 2 & 4 \end{pmatrix}$
$$
\begin{pmatrix} 2 & 5 & -2 \\ 3 & 2 & 4 \end{pmatrix} \to \begin{pmatrix} 2 & 5 & -2 \\ 1 & -3 & 6 \end{pmatrix} \to 
\begin{pmatrix} 1 & -3 & 6 \\ 2 & 5 & -2 \end{pmatrix} \to
\begin{pmatrix} 1 & -3 & 6 \\ 0 & 11 & -14 \end{pmatrix}
$$

$$
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 11 & -14 \end{pmatrix} \to 
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 11 & -3 \end{pmatrix} \to \begin{pmatrix} 1 & 0 & 0 \\ 0 & -3 & 11 \end{pmatrix} \to \begin{pmatrix} 1 & 0 & 0 \\ 0 & -3 & -1 \end{pmatrix}
$$

$$
 \to
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 3 \end{pmatrix}  \to 
\begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \end{pmatrix} 
$$

