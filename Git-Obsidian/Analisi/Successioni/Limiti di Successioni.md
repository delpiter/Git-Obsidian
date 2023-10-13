>[!info] Definizione Limite
>Sia $(a_{n})_{n\in\mathbb{N}}$ una successione reale, sia $l\in \mathbb{R} diciamo che $\lim\limits_{n\to+\infty}a_{n}=l$ se :
>$$
\forall\mathcal{E}>0, \exists m_{\mathcal{E}}\in\mathbb{N} : |a_{n}-l|\leq\mathcal{E} \ \forall n\geq m_{\mathcal{E}}
>$$
##### Es
$a_{n}=\displaystyle{\frac{2n+1}{n+2}}$
- Verifica che $\lim\limits_{n\to+\infty}a_{n}=2$
- Dato $\mathcal{E}>0$
$$
\begin{array}
\ |a_{n}-l|=|\displaystyle{\frac{2n+1}{n+2}}-2|\leq \mathcal{E} \\
| \displaystyle{\frac{2n+1-2n-4}{n+2}}|\leq\mathcal{E} \\
\displaystyle{\frac{3}{n+2}}\leq\mathcal{E} \Leftrightarrow n+2\geq \displaystyle{\frac{3}{\mathcal{E}}} \\
n\implies \displaystyle{\frac{3}{\mathcal{E}}}-2
\end{array}
$$
#### Osservazione
> Non tutte le successioni hanno un limite
##### Es
- $a_{n}=(-1)^n$
![[Pasted image 20231013095115.png]]
- Oscilla fra $1$ e $-1$

## Unicità del Limite
- - -
>[!info] Teorema
>Sia $(a_{n})_{n\in\mathbb{N}}$ in $\mathbb{R}$, siano $l,m \in \mathbb{R}$ supponiamo
>$$
\begin{array}
\ \lim\limits_{n\to+\infty}a_{n}=l \\
\lim\limits_{n\to+\infty}a_{n}=m
\end{array}
>$$
>Allora $l=m$

### Dimostrazione
- Per ipotesi ho che
$$
\begin{array}
\ \forall \mathcal{E}>0,p_{\mathcal{E}}\in\mathbb{R}:|a_{n}-l|\leq\mathcal{E} \forall n\geq p_{\mathcal{E}} \\
\forall \mathcal{E}>0,q_{\mathcal{E}}\in\mathbb{R}:|a_{n}-m|\leq\mathcal{E} \forall n\geq q_{\mathcal{E}}
\end{array}
$$
- Sia $n\geq max\{p_{\mathcal{E}},q_{\mathcal{E}}\}$
$$
\begin{array}
\ | l-m | =   | l-a_{n}+a_{n}-m | \leq \underbrace{| l-a_{n} |}_{\leq\mathcal{E}} +   \underbrace{| a_{n}-m |}_{\leq\mathcal{E}} \\
|l-m|\leq 2\mathcal{E}
\end{array}
$$
- Da ciò si deduce che deve essere necessariamente $l=m$
- Infatti
	- Se fosse $|l-m|>0$, potrei trovare $\mathcal{E}>0$ (per esempio $\displaystyle{\frac{|l-m|}{2}}$) : $|l-m|>\mathcal{E}$

## Valore assoluto del Limite
- - -
>Sia $(a_{n})n\in\mathbb{R}:\lim\limits_{n\to+\infty}a_{n}=l$
>Allora
>$\lim\limits_{n\to+\infty}|a_{n}|=|l|$
### Dimostrazione
- Per ipotesi ho che
$$
\forall\mathcal{E}>0,\exists m_{\mathcal{E}}\in\mathbb{N}:|a_{n}-l|\leq\mathcal{E} \ \forall n\geq m_{\mathcal{E}}
$$
- Allora
$$
\forall\mathcal{E}>0,\exists m_{\mathcal{E}}\in\mathbb{N}:||a_{n}|-|l||\leq\mathcal{E} \ \forall n\geq m_{\mathcal{E}}
$$
- E ciò è sempre vero poichè per la disugualianza triangolare
$$
||a_{n}|-|l||\leq|a_{n}-l|
$$