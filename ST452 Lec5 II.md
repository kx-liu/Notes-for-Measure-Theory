# ST452 Probability and Mathematical Statistics

## Lecture 5 Conditional Expectation

Let $(\Omega,\mathscr{F},\mathbb{P})$ be a probability space. Take $X\in L^1(\Omega,\mathscr{F},\mathbb{P})$, and $\mathcal{G}\sub\mathscr{F}$, where $X$ may not be $\mathcal{G}$-measuable. $\exists\text{a r.v. }Y,\text{s.t.}$

1. $Y\in L^1(\Omega,\mathcal{G},\mathbb{P})$
2. $\mathbb{E}[Y\mathbb{1}_A]=\mathbb{E}[X\mathbb{1}_A],\forall A\in\mathcal{G}$

Moreover, if $\tilde{Y}$ is another r.v. with same properties, $\tilde{Y}=Y,\text{a.s.}$.

#### Proof of uniqueness

$$
\mathbb{E}[(Y-\tilde{Y})\mathbb{1}_A]=0,\qquad\forall A\in\mathcal{G}
$$

Noticing $\{\omega:Y(\omega)-\tilde{Y}(\omega)>0\}\in\mathcal{G}$. 
$$
\mathbb{E}\left[(\tilde{Y}-Y)^+\mathbb{1}_{\{Y-\tilde{Y}>0\}}\right]=0\implies Y=\tilde{Y},\text{ a.s.}
$$

#### Proof of existence

Let $X\in L^2(\Omega,\mathscr{F},\mathbb{P})$. By Orthogonal Projection Theorem, $\exists Y\in\mathcal{K}=L^2(\Omega,\mathcal{G},\mathbb{P}),\text{s.t.}$

$$
\mathbb{E}[(X-Y)^2]=\inf\{\mathbb{E}[(X-W)^2]:W\in\mathcal{K}\}\text{ and }\mathbb{E}[(X-Y)Z]=0(\forall Z\in\mathcal{K})
$$
Let $A\in\mathcal{G},\mathbb{1}_A\in\mathcal{K}$. Therefore, $\mathbb{E}[(X-Y)\mathbb{1}_A]=0$.

General case: $X\in L^1$, wlog, $X\geq0$ since otherwise $X=X^+-X^-, X^{\pm}\in L^1$.

$X_n=X\and n\implies\exists Y_n\in\mathcal{K},\text{s.t. }\mathbb{E}[X_n\mathbb{1}_A]=\mathbb{E}[Y_n\mathbb{1}_A]$, take limit of both sides, and use MCT:
$$
\lim_{n\to\infty}\mathbb{E}[Y_n\mathbb{1}_A]=\mathbb{E}[X\mathbb{1}_A]
$$
Look at 
$$
\mathbb{E}[(Y_{n+1}-Y_n)\mathbb{1}_A]=\mathbb{E}[((X\and n+1)-(X\and n))\mathbb{1}_A]\geq0
$$
$\forall A\in\mathcal{G}:(Y_{n+1}-Y_n)\mathbb{1}_A\geq0,\text{a.s. on }\mathcal{G}\implies Y_{n+1}-Y_n\geq0,\text{a.s. on }\mathcal{G}$. $Y_n$'s are non-decreasing, using MCT in the dominance of a.s.:
$$
Y(\omega)=\lim\sup Y_n(\omega)
$$
Prove the properties of conditional expectation in Section 9.7 in Williams.

### Definition 1 (Characteristic Function)

Let $X\in\mathscr{F}$ on $(\Omega,\mathscr{F},\mathbb{P})$. The characteristic function $\varphi=\varphi_X$ is defined to be the map $\varphi:\mathbb{R}\to\mathbb{C}$, 
$$
\varphi(\theta)=\mathbb{E}[e^{i\theta X}]=\mathbb{E}[\cos(\theta X)+i\sin(\theta X)]=\mathbb{E}[\cos(\theta X)]+i\mathbb{E}[\sin(\theta X)]
$$

### Properties of Characteristic Function

1. $\varphi(0)=1$
2. $|\varphi(\theta)|\leq1$
3. $\theta\to\varphi(\theta)$ is continuous
4. $\varphi_{-X}(\theta)=\varphi_X(\theta)$
5. $\varphi_{aX+b}(\theta)=e^{ib\theta}\varphi_X(a\theta)$
