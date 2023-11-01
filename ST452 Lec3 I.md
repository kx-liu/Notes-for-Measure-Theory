# ST452 Probability and Mathematical Statistics

## Lecture 3 Independence

Let $(\Omega,\mathscr{F},\mathbb{P})$ be a probability space.

### Definition 1 (Independent $\sigma$-algebras)

$\mathscr{G}_i\subset\mathscr{F}$ are independent if whenever $G_i\in\mathscr{G}_i$, and $i_1,\dots,i_n$ are distinct, 
$$
\mathbb{P}(G_{i_1}\cap G_{i_2}\cap\cdots\cap G_{i_n})=\prod_{k=1}^n\mathbb{P}(G_{i_k})
$$

### Definition 2 (Independent r.v.)

RVs $(X_i)$ are independent if $\sigma(X_i)$ are independent.

#### Example

$A_1,\dots,A_n$ are independent iff $\mathbb{1}_{A_1},\dots,\mathbb{1}_{A_n}$ are independent.

### Lemma 1 (Expanding from $\pi$-system)

$\mathscr{G}\subset\mathscr{F},\mathscr{H}\subset\mathscr{F}$, such that exists $\pi$-system $\mathcal{I}$ and $\mathcal{J}$ with $\sigma(\mathcal{I})=\mathscr{G},\sigma(\mathcal{J})=\mathscr{H}$. Then, $\mathscr{G}$ and $\mathscr{H}$ are independent iff $\mathcal{I}$ and $\mathcal{J}$ are independent, in the sense that 
$$
\mathbb{P}(A\cap B)=\mathbb{P}(A)\mathbb{P}(B),\quad \forall A\in\mathcal{I},\forall B\in\mathcal{J}
$$

#### Proof of Lemma 1

Suppose $\mathcal{I},\mathcal{J}$ are independent. On $(\Omega,\mathscr{H})$ define two probability measures:
$$
\mathbb{P}_1(H)=\mathbb{P}(A\cap H)\\
\mathbb{P}_2(H)=\mathbb{P}(A)\mathbb{P}(H)
$$
We have $\mathbb{P}_1(\Omega)=\mathbb{P}_2(\Omega)=1$. For $B\in\mathcal{J}$, $\mathbb{P}_1(B)=\mathbb{P}(A\cap B)=\mathbb{P}(A)\mathbb{P}(B)=\mathbb{P}_2(B)$. Hence, $\mathbb{P}_1=\mathbb{P}_2$ on $\mathscr{H}$, that is $\mathbb{P}(A\cap H)=\mathbb{P}(A)\mathbb{P}(H),\forall H\in\mathscr{H}$. Therefore, $\mathbb{P}(\cdot\cap H)=\mathbb{P}(\cdot)\mathbb{P}(H)$ on $\mathcal{I}$, and $\mathbb{P}(\cdot\cap H)=\mathbb{P}(\cdot)\mathbb{P}(H)$ on $\mathscr{G}$, thus $\mathbb{P}(A\cap H)=\mathbb{P}(A)\mathbb{P}(H),\forall A\in\mathscr{G},\forall H\in\mathscr{H}$.

### Corollary

$$
X_i,\text{r.v.},i\in\mathcal{I}\text{ are independent}\iff \mathbb{P}(X_k\leq x_k,1\leq k\leq n)=\prod_{k=1}^n\mathbb{P}(X_k\leq x_k)
$$

### Lemma 2 (Second Borel-Cantelli Lemma)

If $(E_n)$ is a sequence of independent events, then
$$
\sum_{n=1}^\infty\mathbb{P}(E_n)=\infty\implies\mathbb{P}(E_n,\text{i.o.})=\mathbb{P}(\lim\sup E_n)=1
$$

#### Proof of Lemma 2

$(\lim\sup E_n)^c=\lim\inf E_n^c$. Let $p_n:=\mathbb{P}(E_n)$.
$$
\begin{aligned}
\mathbb{P}\left(\bigcap_{n\geq m}E_n^c\right)&=\lim_{r\to\infty}\mathbb{P}\left(\bigcap_{n=m}^rE_n^c\right)\\
&=\lim_{r\to\infty}\prod_{n=m}^r\mathbb{P}(E_n^c)\\
&=\prod_{n=m}^\infty(1-p_n)\\
&\leq\prod_{n=m}^\infty e^{-p_n}\\
&=\exp\left\{-\sum_{n=m}^\infty p_n\right\}\\
&=0
\end{aligned}
$$
To come up with the Kolmogorov's 0-1 law, we need to define tail $\sigma$-algebra first.

### Definition 3 (Tail $\sigma$-algebra)

Let $X_1,X_2,\dots$ be r.v.'s. Define
$$
\mathcal{T}_n=\sigma(X_n,X_{n+1},\dots),\quad\mathcal{T}:=\bigcap_n\mathcal{T}_n
$$
$\mathcal{T}$ is called the tail $\sigma$-algebra of $(X_n)_{n\geq1}$.

#### Examples

- $\{\omega:\lim_n X_n(\omega)\text{ exists}\}\in\mathcal{T}$
- $\{\omega:\sum_n X_n(\omega)<\infty\}\in\mathcal{T}$
- $\{\omega:\lim_n n^{-1}\sum_{i=1}^nX_i(\omega)\text{ exists}\}\in\mathcal{T}$

### Theorem 1 (Kolmogorov's 0-1 Law)

Let $(X_n)_{n\geq1}$ be a seqence of independent r.v.'s. Then $\mathcal{T}$ is trivial:

1. $E\in\mathcal{T}\implies\mathbb{P}(E)=0\text{ or }1$
2. If $\xi$ is a r.v. and is $\mathcal{T}$-measuable, then $\mathbb{P}(\xi=c)=1$ for some $c\in[-\infty,\infty]$

The independence of r.v.s is not required.

#### Proof of Theorem 1 (Part 1)

Introduce another $\sigma$-algebra $\mathcal{X}_n:=\sigma(X_1,\dots,X_n)$

- Step 1: To show that $\mathcal{X}_n$ and $\mathcal{T}_{n+1}$ are independent:

  Let $\mathcal{K}$ be the class of events $\mathcal{K}:=\{\omega:X_j(\omega)\leq x_j,n+1\leq j\leq n+r\}$, where $r\in\mathbb{N},x_j\in\mathbb{R}\cup\{\infty\}$. $\mathcal{K}$ is a $\pi$-system generating $\mathcal{T}_{n+1}$; Let$\mathcal{J}$ be the class of events $\mathcal{J}:=\{\omega:X_i(\omega)\leq x_i,1\leq i\leq n\}$, where $r\in\mathbb{N},x_i\in\mathbb{R}\cup\{\infty\}$. $\mathcal{K}$ is a $\pi$-system generating $\mathcal{X}_n$. By assumption, $\mathcal{K}$ is independent from $\mathcal{J}$, so $\mathcal{X}_n$ and $\mathcal{T}_{n+1}$ are independent.
  
- Step 2: To show that $\mathcal{X}_n$ and $\mathcal{T}$ are independent:

  Since $\mathcal{T}=\bigcap_n\mathcal{T}_n\subseteq\mathcal{T}_{n+1}$,  $\mathcal{X}_n$ and $\mathcal{T}$ are independent.
  
- Step 3: To show that $\mathcal{X}_\infty:=\sigma(X_n:n\in\mathbb{N})$ and $\mathcal{T}$ are independent:

  $\mathcal{X}_\infty$ is generated by $\bigcup_n\mathcal{X}_n$, which is a $\pi$-system and we know from step 2 that each $\sigma$-algebra in the $\pi$-system is indenpendent from $\mathcal{T}$, that is $\bigcup_n\mathcal{X}_n$ is independent from $\mathcal{T}$.
  
- Step 4: It is trivial that $\mathcal{T}$ and $\mathcal{T}$ are independent.

- Step 5: If $E\in\mathcal{T},\mathbb{P}(E)=\mathbb{P}(E\cap E)=\mathbb{P}(E)\mathbb{P}(E)$, that is $\mathbb{P}(E)\in\{0,1\}$.
