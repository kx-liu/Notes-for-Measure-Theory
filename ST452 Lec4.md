# ST452 Probability and Mathematical Statistics

## Lecture 4 $L^p$ Spaces

### Jensen's Inequality

Let $\varphi:\mathscr{G}\to\mathbb{R}$, $\mathscr{G}\sub\mathbb{R}$ is an open interval, $\varphi$ is convex. Then if $X,\varphi(X)\in L^1(\Omega,\mathscr{F},\mathbb{P})$, then
$$
\mathbb{E}(\varphi(X))\geq\varphi(\mathbb{E}(X))
$$
provided $\mathbb{P}(X\in\mathscr{G})=1$.

### Definition 1 ($L^p$ norm)

If $X\in L^p(\Omega,\mathscr{F},\mathbb{P})$, that is $\mathbb{E}[|X|^p]<\infty$, then
$$
||X||_p=\left\{\mathbb{E}(|X|^p)\right\}^{\frac{1}{p}}
$$

### Proposition

For $1\leq p\leq r<\infty$, if $Y\in L^r$, then $Y\in L^p$ and $||Y||_p\leq||Y||_r$

#### Proof of proposition

Let $(|Y|\and n):=\min\{|Y|,n\}$. Define $X_n:=(|Y|\and n)^p,\forall n$, which is a bounded r.v.. Therefore, $X_n,X_n^{r/p}\in L^1$. $\varphi(X)=X^{r/p}$ is a convex function. Using the Jensen's inequality, 
$$
[\mathbb{E}(X_n)]^{\frac{r}{p}}\leq\mathbb{E}[X_n^{\frac{r}{p}}]\leq\mathbb{E}[|Y|^r]
$$
Using MCT, 
$$
[\mathbb{E}(\lim X_n)]^{\frac{r}{p}}=\mathbb{E}[|Y|^p]\leq\mathbb{E}[|Y|^r]
$$

### Holder's Inequality

If $p>1,f\in L^p,g\in L^q,\frac{1}{p}+\frac{1}{q}=1$, then
$$
||f\cdot g||_1\leq||f||_p||g||_q
$$

#### Proof of Holder's Inequality

Let $(\Omega,\mathscr{F})$, assume $f,g\geq0$, 
$$
\mathbb{Q}(A):=\frac{\mathbb{E}[f^p\mathbb{1}_A]}{||f||_p^p}
$$
is a probability measure (**Prove it!!**).  Suppose
$$
u:=\frac{g}{f^{p-1}}\mathbb{1}_{\{f>0\}}\\
$$
Since $q>1$, Jensen's inequality yields
$$
\frac{\mathbb{E}\left[\frac{g^q}{f^{q(p-1)}}\mathbb{1}_{\{f>0\}}f^p\right]}{||f||_p^p}
\geq\frac{\left(\mathbb{E}[\frac{g}{f^{p-1}}\mathbb{1}_{\{f>0\}}f^p]\right)^q}{||f||_p^{pq}}
$$
Noticing $\frac{1}{p}+\frac{1}{q}=1\implies p+q=pq\implies p+q-pq=0$, we have
$$
\mathbb{E}[g^q]\cdot||f||_p^q\geq (\mathbb{E}[g\cdot f])^q
$$

### Corollary

If $f,g\in L^p$, then
$$
||f\cdot g||_1\leq||f||_2||g||_2
$$

### Minkowski's Inequality

If $f,g\in L^p$, then $||f+g||_p\leq||f||_p+||g||_p$.

#### Proof of Minkowski's Inequality

If $p=1$, obvious.

If $p>1$, $|f+g|^p=|f+g||f+g|^{p-1}\leq|f+g|^{p-1}(|f|+|g|)$. Set $q:\frac{1}{p}+\frac{1}{q}=1$, 
$$
\begin{aligned}
||f+g||_p^p&=\int|f+g|^p\mathrm{d}\mathbb{P}\\
&\leq||f||_p\left(\int|f+g|^{(p-1)q}\mathrm{d}\mathbb{P}\right)^\frac{1}{q}+||g||_p\left(\int|f+g|^{(p-1)q}\mathrm{d}\mathbb{P}\right)^\frac{1}{q}\\
&=\left(||f||_p+||g||_p\right)\left(\int|f+g|^{p}\mathrm{d}\mathbb{P}\right)^\frac{1}{q}\\
&=\left(||f||_p+||g||_p\right)||f+g||_p^{p/q}
\end{aligned}
$$
Remark: Minkowski's inequality shows that $||\cdot||_p$ is a norm:

1. $||\alpha f||_p=\alpha||f||_p,\alpha\in\mathbb{R}$
2. $||f||=0\implies f=0,\text{a.s.}$

$||\cdot||_p$ is a norm on the equivalence classes of $L^p(\Omega,\mathscr{F},\mathbb{P})$. We say $f$ and $g$ belong to the same equivalence class if $f=g,\text{a.s.}$

### Definition 2 (Cauchy Sequence)

$(f_n)\sub L^p(\Omega,\mathscr{F},\mathbb{P})$ is a Cauchy sequence if $\forall\epsilon>0,\exists M,\text{s.t. }\forall n,m\geq M,||f_n-f_m||_p\leq\epsilon$

### Theorem 1

If $1\leq p<\infty,L^p(\Omega,\mathscr{F},\mathbb{P})$ is a complete normed space; in particular, this meas that it is Banach space.

### Theorem 2 (Orthogonal Projection Theorem)

Let $\mathcal{K}\sub L^2(\Omega,\mathscr{F},\mathbb{P})$ be a closed subspace of $L^p(\Omega,\mathscr{F},\mathbb{P})$; i.e. if $f,g\in\mathcal{K}\implies\alpha f\in\mathcal{K},\forall \alpha\in\mathbb{R}$, and if $(f_n)\sub\mathcal{K},f_n\to f$ in $L^2$, then $f\in\mathcal{K}$. Then given $X\in L^2(\Omega,\mathscr{F},\mathbb{P}),\exists Y\in\mathcal{K},\text{s.t.}$:

1. $||X-Y||_2:=\Delta:=\inf\{||X-W||:W\in\mathcal{K}\}$
2. $X-Y\perp Z\ (\forall Z\in\mathcal{K})\iff\mathbb{E}(X-Y)Z=0\ (\forall Z\in\mathcal{K})$

#### Proof of Orthogonal Projection Theorem

1. $\Delta$ is the distance of $X$ to the subspace $\mathcal{K}\implies$ exists a sequence $(Y_n)\sub\mathcal{K}:||X-Y_n||_2\to\Delta$
   $$
   ||X-Y_n||_2^2+||X-Y_m||_2^2=2||X-\frac{1}{2}(Y_n+Y_m)||^2_2+2||\frac{1}{2}(Y_n-Y_m)||_2^2
   $$
   The first term of the r.h.s $\geq\Delta$ since it is a linear vector space. Considering the second term, the distance between $X$ and $Y_m$ are both converging to $\Delta$, 
   $$
   2||\frac{1}{2}(Y_n-Y_m)||_2^2=||X-Y_n||_2^2+||X-Y_m||_2^2-2||X-\frac{1}{2}(Y_n+Y_m)||_2^2\leq2(\Delta^2+\epsilon^2)-2\Delta^2=2\epsilon^2
   $$
   That is $Y_n$ is a Cauchy sequence in $L^2$; but since $L^2$ is complete, therefore $(Y_n)$ converges to an element of $L^2$, and $Y\in\mathcal{K}$. 
   $$
   ||X-Y||_2\leq||X-Y_n||_2+||Y_n-Y||_2\to\Delta
   $$
   Therefore, $||X-Y||_2\leq\Delta$. To sum up, $||X-Y||_2=\Delta$

2. Take $Z\in\mathcal{K}:Y+tZ\in\mathcal{K},t\in\mathbb{R}$
   $$
   ||X-(Y+tZ)||_2\geq\Delta=||X-Y||_2\implies||X-(Y+tZ)||_2^2\geq||X-Y||_2^2
   $$

   $$
   ||X-(Y+tZ)||_2^2=||X-Y||_2^2+t^2||Z||_2^2-2t\mathbb{E}[(X-Y)Z]\geq||X-Y||_2^2
   $$

   Therefore, $t^2||Z||^2_2-2t\mathbb{E}[(X-Y)Z]\geq0$. Let $t=r\text{sgn}(\mathbb{E}[(X-Y)Z]),r>0$. If $\mathbb{E}[(X-Y)Z]>0$, $-r\mathbb{E}[(X-Y)Z]+r^2||Z||_2^2\geq0$. Let $r\to0$, $-2\mathbb{E}[(X-Y)Z]\geq0$, therefore, $\mathbb{E}[(X-Y)Z]=0$.

