>[!info] Definizione
>Sia $a\neq 0$ chiamiamo successione in $A$ una qualsiasi funzione
> $$
f: \mathbb{N}\to A
>$$
## Notazione
$$
\underbrace{a_{n}}_{\text{termine n-esimo}} := a(n)
$$
- $n$ anche detto l'indice della successione
##### Es
- $a_{n}=k, \ k\in\mathbb{R}$
![[Pasted image 20231013094149.png]]

- $a_{n}=(-1)^n$
![[Pasted image 20231013095115.png]]

## Successioni infinitesime
- - -
>[!info] Definizione
>Sia $(a_{n})_{n\in\mathbb{N}}$ una successione in $\mathbb{R}$ diciamo che la mia successione è infinitesima (che tende a $0$) per $n \to +\infty$ se
>$$
\forall \mathcal{E} \in \mathbb{R}^+\setminus\{0\}, \exists m_{\mathcal{E}}\in \mathbb{N} : \forall n \geq m_{\mathcal{E}} \text{ si ha } |a_{n}|\leq\mathcal{E}
>$$

![[Pasted image 20231013110411.png]]
### Es
- $a_{n}=\displaystyle{\frac{1}{n}}$
- Verifichiamo che $\lim\limits_{n\to+\infty} \displaystyle{\frac{1}{n}} =0$
###### Infatti
$\forall \mathcal{E} \in \mathbb{R}^+\setminus\{0\}, \exists m_{\mathcal{E}}\in\mathbb{N} : \forall n\geq m_{\mathcal{E}} \text{ si ha } |\displaystyle{\frac{1}{n}}|\leq\mathcal{E}$
$$
\ |\displaystyle{\frac{1}{n}}|\leq\mathcal{E} \Leftrightarrow \displaystyle{\frac{1}{n}}\leq\mathcal{E}\Leftrightarrow n\geq \displaystyle{\frac{1}{\mathcal{E}}}
$$
- Posso scegliere come $m_{\mathcal{E}}=\lfloor \displaystyle{\frac{1}{\mathcal{E}}}\rfloor+1$
## Successione Monotona
- - -
>[!info] Definizione
>Sia $(a_{n})_{n\in\mathbb{N}}$ una successione in $\mathbb{R}$ diciamo che $(a_{n})$ è [[Introduzione Funzioni#Crescente|crescente]] se
> $$
a_{n\leq a_{n+1}}
>$$
>Sia $(a_{n})_{n\in\mathbb{N}}$ una successione in $\mathbb{R}$ diciamo che $(a_{n})$ è [[Introduzione Funzioni#Decrescente|decrescente]] se
> $$
a_{n\geq a_{n+1}}
>$$
>Analogamente strettamente crescente e strettamente decrescente

#### Esempi
- $a_{n}=n \nearrow$
- $a_{n}=\frac{1}{n} \searrow$
- $a_{n}=2^n \nearrow$
- $a_{n}=(\frac{1}{2})^n \searrow$
### Osservazione
> Se $a_{n}$ è una successione crescente allora $a_{n}$ è inferiormente limitata e $inf(a_{n})=a_{0}$
> Se $a_{n}$ è una successione decrescente allora $a_{n}$ è superiormente limitata e $sup(a_{n})=a_{0}$

## Limiti di Successioni Monotone
- - -
>[!info] Teorema
>Sia $(a_{n})_{n\in\mathbb{N}}$ successione in $\mathbb{R}$ monotona, allora $a_{n}$ è regolare
>Più precisamente
>$$
\begin{array}
\ \text{se }a_{n}\nearrow \implies\lim\limits_{n\to+\infty}a_{n}=sup(a_{n}) \\
\text{se }a_{n}\searrow \implies\lim\limits_{n\to+\infty}a_{n}=inf(a_{n})
\end{array}
>$$

## Criterio del Rapporto
- - -
>[!info] Teorema
>Sia $(a_{n})_{n\in\mathbb{N}}$ successione in $\mathbb{R}^+\setminus\{0\}$ e supponiamo che $\displaystyle{\frac{a_{n+1}}{a_{n}}}$ sia regolare
> $$
\lim\limits_{n\to+\infty} \displaystyle{\frac{a_{n+1}}{a_{n}}}= \begin{cases}
\text{se }l>1 \implies \lim\limits_{n\to+\infty}a_{n}=+\infty \\
\text{se }0\leq l<1 \implies \lim\limits_{n\to+\infty}a_{n}=0
\end{cases}
>$$
### Dimostrazione