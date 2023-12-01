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
#### $0\leq l<1$
Dato che $l < 1$
$$
\exists\ m : l<m<1
$$
Applichiamo il [[Limiti di Successioni#Teorema della permanenza dei segni|teorema di permanenza del segno]] a $\large\frac{a_{n+1}}{a_{n}}-m$ ottenendo
$$
\large \exists\ \overline{n} \in \mathbb{N} : \frac{a_{n+1}}{a_{n}} < m, \forall  n\geq \overline{n} 
$$
In particolare:
$$
\begin{align}
& n=\overline{n}: \frac{a_{\overline{n}+1}}{a_{\overline{n}}}<m \iff a_{\overline{n}+1}<ma_{\overline{n}} \\
& n=\overline{n}+1: \frac{a_{\overline{n}+2}}{a_{\overline{n}+1}}<m \iff a_{\overline{n}+2}< m\underbrace{ a_{\overline{n}+1} }_{ \displaystyle{< ma_{\overline{n}}} } <m^{2}a_{\overline{n}}
\end{align}
$$
Generalizzando $k > 0$
$$
\large n=\overline{n}+k-1 \implies a_{\overline{n}+k}<m^{k}a_{\overline{n}}
$$
Scrivibile anche come 
$$
n=\overline{n}+k: a_{n}<m^{n-\overline{n}}\cdot a_{\overline{n}} = 
m^{n}\cdot \frac{a_{\overline{n}}}{m^{\overline{n}}}
$$
Riassumendo
$$
\large 0<a_{n}<m^{n} \frac{a_{\overline{n}}}{m^{\overline{n}}}
$$
Siccome $0<m<1$ 
$$
\underset{ n\rightarrow  +\infty }{ m^{n}\frac{a_{\overline{n}}}{m^{\overline{n}}} \rightarrow  0 }
$$
Dimostrando quindi per il [[Limiti di Successioni#Teorema dei due Carabinieri|teorema dei carabinieri]]
$$
\large \underset{ n\rightarrow +\infty }{ a_{n}\rightarrow 0 }
$$
#### $l>1$
Si risolve [[#$0 leq l<1$|analogamente]] con
$$
\large m \mid 1>m>l
$$
#### $l=1$
Non si può prevedere in maniera rigorosa