# [4/10] Algebra II Notes

#### Symmetric Polynomials

**Note:** For today, $F$ is a perfect field. 

**Statement:** Let $E$ be a splitting field of $f \in F[x]$ where $F = E(\alpha_1, \dots, \alpha_n)$ where $\alpha_1, \dots, \alpha_n$ are roots of $f$. $F \leq E$ is a Galois extension, 
$$
E^{\text{Gal}(E/F)} = F
$$
Any $\sigma \in \text{Gal}(E/F)$ permutes the roots. In fact, we have an injective homomorphism $\text{Gal}(E/F) \leq S_n$. 

**Corollary:** Any symmetric expression in $\{\alpha_i\}^{n}_{i=1}$ is an element in $F$. That is, if $g \in F[\alpha_1, \dots, \alpha_2]^{S_n} \implies g \in F$. 

<u>Notation:</u> $F[\alpha_1, \dots, \alpha_n]^{S_n}$ is the set of all elements in $F[\alpha_1, \dots, \alpha_n]$ that is fixed by $S_n$. 
$$
\{h \in F[\alpha_1,\dots,\alpha_n] \text{ such that } h(\alpha_1,\dots,\alpha_n) = h(\alpha_{\sigma(1)}, \dots, \alpha_{\sigma(n)} \text{ for all }\sigma \in S_n\}
$$
**Definition:** $f \in F[x_1, \dots, x_n]$ is called a <u>symmetric polynomial</u> if $f \in F[x_1, \dots, x_n]^{S_n} \leq F[x_1, \dots, x_n]$. 

<u>Example:</u> Take $F = \mathbb{Z}$. We can determine the following $f(x_1, x_2) = $ 

- $x_1 + x_2$ is symmetric
- $x_1x_2$ is symmetric 
- $x_1 - x_2$ is not!

**Corollary:** Consider homorphism $\psi: F[x_1, \dots, x_n]^{S_n} \to E$ given by $h \to h(\alpha_1, \dots, \alpha_n)$. Then,
$$
\Im (\psi ) = F \leq E
$$
 If $f$ is monic, then 
$$
\begin{align*}
f &= \prod_{i=1}^n (x- \alpha_i) \\
&= (x-\alpha_1) \cdots (x-\alpha_n)\\
&= x^n - \left(\sum_{i=1}^{n} a_i\right) x^{n-1} + \left(\sum_{i < j} \alpha_i\alpha_j\right)x^{n-2} + \cdots + (-1)^n \prod_{i=1}^{n}\alpha_i\\
&= \sum_{i=1}^n (-1)^{n-i} \cdot x^i \cdot S_{n-1} (\alpha_1, \dots, \alpha_n) 
\end{align*}
$$
where $S_i(\alpha_1, \dots, \alpha_n) = \sum_{k_1 < k_2 < \cdots < k_i} \alpha_{k_1} \alpha_{k_2} \cdots \alpha_{k_i}$. 

1. $S_i(x_1, \dots, x_n)$ are symmetrical polynomials
2. $S_i(\alpha_1, \dots, \alpha_n)$ are coefficients of $f \implies S_1(\alpha_1, \dots, \alpha_n) \in F$  

**Definition:** $S_1, \dots, S_n$ are called <u>elementary symmetricy polynomials</u> in $n$ variables. 

**Theorem:** $\psi : F[S_1, \dots, S_n] \rightarrow F[x_1, \dots, x_n]^{S_n}$ also known as
$$
\underbrace{S_i}_{\text{formal variable}} \rightarrow \underbrace{S_i(x_1, \dots, x_n)}_{\text{polynomial in }x}
$$
is an isomorphism of rings!

<u>Example:</u> $x_1^2 + x_2^3 \in \mathbb{Q}[x_1, x_2]^{S_2}$ 

We have $S_1(x_1, x_2) = x_1 + x_2$ and $S_2(x_1, x_2) = x_1x_2$. 
$$
x_1^2 + x_2^2 = S_1^2 - 2S_2
$$

----

#### Discriminant

**Definition:** Give $f \in F[x]$ and $E$ is a splitting field of $f$, we can define the <u>discriminant</u> of $f$ by
$$
\Delta(f) = \prod_{1 \leq i < j} (\alpha_i - \alpha_j)^2
$$

- $\Delta(f) = 0 \iff $ f has a double root
- $\Delta(f) \in F$ 

**Proof (2):** $\Delta(f) \in F[\alpha_1, \dots, \alpha_n]^{S_n}$ 

- The discriminant has a square root $\sqrt{\Delta}(f) = \prod_{i \leq i < j \leq n} (\alpha_i - \alpha_j) \in E$

**Proposition:** $\sqrt{\Delta}(f) \in F \leq E \iff \text{Gal}(E/F) \leq A_n \leq S_n$. Moreover, if $\sigma\left(\sqrt{\Delta}(f)\right) = \sqrt{\Delta}(f)$ where $\sigma \in S_n \implies \sigma \in A_n$. 

**Proof:** Let $\sigma \in S_n$, then 
$$
\begin{align*}
\sigma \left(\sqrt{\Delta}(f)\right) &= \prod_{i < j} \left(\alpha_{\sigma(i)} - \alpha_{\sigma(j)}\right) \\
&= (-1)^{\text{sign}(\sigma)} \prod_{i<j} (\alpha_i - \alpha_j)\\
&= (-1)^{\text{sign}(\sigma)} \sqrt{\Delta}(f)
\end{align*}
$$
The above proves the claim in parentheses since $A_n = \{0 \in S_n \text{ such that sign}(\sigma) = 0\}$. 

Now, $\sqrt{\Delta}(f) \in F \iff \sqrt{\Delta}(f) \in E^{\text{Gal}(E/F)} \iff $ for all $\sigma \in \text{Gal}(E/F)$. This is also to say that $\sigma(\sqrt{\Delta}(f)) = \sqrt{\Delta(f)} \iff \sigma \in A_n$ for every $\sigma \in \text{Gal}(E/F)$. 

**Note:** Let $f = x^2 + bx + c = (x-\alpha_1)(x-\alpha_2) = x^2 - (\alpha_1 + \alpha_2)x + \alpha_1\alpha_2$ 
$$
\Delta(f) = (\alpha_1 - \alpha_2)^2 = \alpha_1^2 - 2\alpha_1 \alpha_2 + \alpha_2^2 = (\alpha_1 + \alpha_2)^2 - 4 \alpha_1 \alpha_2 = b^2 - 4c
$$
Let $f \in \mathbb{R}[x]$. $\text{Gal}(E/\mathbb{R}) \leq S_2; A_2 = \{\text{id}\}$. By the proposition, $\sqrt{\Delta}(f) = \sqrt{b^2 - 4ac} \in \mathbb{R} \iff \text{Gal}(E/\mathbb{R}) \leq A_2 = \{\text{id}\}$. If $\alpha_1, \alpha_2 \in \mathbb{C}$, then the $\text{Gal}(E/\mathbb{R}) = S_2 = \mathbb{Z}/2\mathbb{Z} = \{\text{id}, z \rightarrow \overline{z}\} $. 

**Note:** Let $f = x^3 + ax^2 + bx + c \in F[x]$ where $F$ is characterstic $0$. We can simplify by $x \mapsto x-a$ with result
$$
f = x^3 + px + q
$$
**Proposition:** $\Delta(f) = -4p^3 + 27q^2$ 

**Proof:** Computation-heavy proof!

- Any cubic polynomial has a real root. If $\Delta(f) = 0 \iff $ there is a double root $\implies f$ has $2$ real roots, one is a double root.

**Lemma:** $\Delta(f) > 0 \iff$ there are $3$ real distinct roots, $\Delta(f) < 0 \iff 1$ real and $2$ complex

**Proof:** $\Delta(f) < 0 \iff \sqrt{\Delta(f)} \in \mathbb{C} \backslash \mathbb{R}$, so $\text{Gal} \cancel{\leq} A_3$ and, in particular, has an element of order $2$.

$\Delta(f) > 0 \iff \text{Gal}(E/\mathbb{R})$  has no element of order $2 \implies$ all $3$ roots are real. 

- If there is a complex root, then $\Delta(f) < 0$. 
