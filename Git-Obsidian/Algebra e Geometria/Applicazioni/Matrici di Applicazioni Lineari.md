>*Abbiamo visto che se $f,g$ sono [[Applicazioni Lineari#Applicazione Lineare|lineari]], anche la loro composizione $g_{o}f$ è lineare*

>[!question] Che relazione c'è fra la matrice di $g_{o}f$ e le matrici di $g$ e $f$?

## Prodotto Riga $\times$ Colonna
---
>[!info] Introduzione
>Siano $V,U,W$ spazi vettoriali su $\mathbb{K}$ con [[Campi e Spazi Vettoriali#Base|basi]]:
>$(v_{1},\dots,v_{n}),(u_{1},\dots,u_{m}),(w_{1},\dots,w_{l})$
>E siano $f:V\to U$ e $g:U\to W$ [[Applicazioni Lineari#Applicazione Lineare|applicazioni lineari]]
>Sia $A$ la matrice di $f$ e $B$ la matrice di $g$ in tali basi
>>[!tip] Vogliamo calcolare la matrice dell'applicazione lineare $g_{o}f_:V\to W$
>
>$f(v_{i})=\displaystyle\sum_{j}a_{ji}u_{j}$
>$g(u_{j})=\displaystyle\sum_{h}b_{jh}w_{h}$
>$$(g_{o}f)(v_{i})=g\left( \sum_{j}a_{ji}u_{j} \right)=\sum_{j}a_{ji}g(u_{j})=\sum_{j}\sum_{h}a_{ji}b_{hj}w_{h}$$

Il coefficiente di $w_{h}$ in questa somma è:
$$
\sum_{j\in\{ 1,\dots,m \}}b_{jh}a_{jh}
$$
Abbiamo scoperto che la *matrice* di $g_{o}f$ in *tali basi* è la matrice che ha,
- Alla $h$-esima ***riga*** e $i$-esima ***colonna***, il numero

>[!definizione] Prodotto Riga $\times$ Colonna
>Definiamo "*prodotto riga $\times$ colonna di $B$ e $A$*"
>come la matrice $BA$ che ha come elemento
>$(BA)_{hi}$ il numero:
>$$\sum_{j\in\{ 1,\dots,m \}}b_{jh}a_{jh}$$
>>[!done] A parole
>>Abbiamo scoperto che la *matrice* di $g_{o}f$ in *tali basi* è la matrice che ha,
>>alla $h$-esima ***riga*** e $i$-esima ***colonna***, il numero descritto dalla *sommatoria*

### Esempio
>*Sia* $V=U=W$ *con base* $e_{1}=(1,0),e_{2}=(0,1)$ *e* $g(x,y)=(2x-y,-x+3y),f(x,y)=(5x+2y,-2x+y)$

Troviamo le matrici di $g$ e $f$
- $g(e_{1})=(2-0,-1+0)=(2,-1)$
- $g(e_{2})=(0-1,-0+3)=(-1,3)$
- $f(e_{1})=(5+0,-2+0)=(5,-2)$
- $f(e_{2})=(0+2,-0+1) = (2,1)$

Otteniamo così le *matrici*:
$$
\text{matrice di }g\to B=\begin{pmatrix}
2 & -1 \\
-1 & 3
\end{pmatrix},
\text{matrice di }f\to A=\begin{pmatrix}
5 & 2 \\
-2 & 1
\end{pmatrix}
$$
Ora facciamo il prodotto *riga* $\times$ *colonna* $B\times A$
$$
BA=\begin{pmatrix}
2 & -1 \\
-1 & 3
\end{pmatrix}\times
\begin{pmatrix}
5 & 2 \\
-2 & 1
\end{pmatrix}
=\begin{pmatrix}
2\cdot5+(-1)\cdot(-2) & 2\cdot2+(-1)\cdot(1) \\
(-1)\cdot5+3\cdot(-2) & (-1)\cdot2+3\cdot 1
\end{pmatrix}=
$$
- Ottenendo così la *matrice*:
$$
\begin{pmatrix}
12 & 3 \\
-11  & 1
\end{pmatrix}
$$
> Ora controlliamo:

$$
\begin{array}
\ (g_{o}f)(x,y)=g(5x+2y,-2x+y) \\
=(2(5x+2y)-(2x+y),-(5x+2y)+3(-2x+y))= \\
=(12x+3y,-11x+y)
\end{array}
$$