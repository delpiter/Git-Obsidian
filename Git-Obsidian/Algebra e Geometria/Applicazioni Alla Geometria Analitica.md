## Retta Passante per Due Punti
---
>*Sia $p_{1}=(x_{1},y_{1}), p_{2}=(x_{2},y_{2}), p_{1}\neq p_{2}$*

>[!question] Trovare la retta che passa per $p_{1}$ e $p_{2}$

Una retta in $\mathbb{R}^2$ è data da un'equazione:
$$
ax+by=c
$$
- Voglio trovare $a,b,c$

>[!tldr] Osservazione
Se $ax+by=c$ è un'equazione della retta, anche $2ax+2bx=2c$ lo è
>- $a,b,c$ non sono ***univocamente determinati***

$$
p_{1}=(1,3),p_{2}=(3,2)
$$
$$
\begin{cases}
a+3b=c \\
3a+2b=c
\end{cases}
$$
Utilizzo [[Risoluzione di Sistemi#Metodo di Gauss|Gauss]]:
$$
\begin{cases}
a+3b=c \\
-7b=-2c
\end{cases}
$$

$S=\left\{  \left( \frac{1}{7}t, \frac{2}{7}t, t \right), t \in \mathbb{R}  \right\}$

>[!warning] La terna $(a,b,c)$ *non è unica*, ma la ***retta*** lo è


## Piano Passante per Tre Punti
---
>*Sia $\mathcal{P}\implies ax+by+cz=d$*

$$
p_{1}=(1,0,0), p_{2}=(0,1,1), p_{3}=(2,0,-1)
$$

$$
\begin{cases}
a=d \\
b+c=d \\
2a-c=d
\end{cases}
\iff
\begin{cases}
a=t \\
b=d-c=0 \\
c=-d+2a = t \\
d=t
\end{cases}
$$

$S=\{ (t,0,t,t),t\in\mathbb{R} \}$
- Un equazione del *piano* è: $x+z=1$

>[!tldr] Osservazione
>$\mathcal{P}$ è un sottospazio affine di $\text{dim}=2$ di $\mathbb{R}^3$

$S$ è un sottospazio affine di $\text{dim}=1$ di $\mathbb{R}^4$

