## Metodo di Gauss
---
>*Algoritmo semplice ed efficiente per risolvere sistemi lineari*
>*Funziona anche per sistemi dove il numero di equazioni è diverso dal numero di incognite*

>[!tip] Vediamo un esempio

$$
\begin{matrix}
1^a \\
2^a \\
3^a \\
4^a
\end{matrix}
\begin{cases}
2x_{1}-x_{2}+x_{3}+2x_{4}=1 \\
4x_{1}-x_{2}-3x_{3}-x_{4}=-1 \\
-2x_{1}-x_{2}+x_{3}+x_{4} = 1 \\
x_{1}+x_{2}+x_{3}+x_{4} = 2
\end{cases}
$$
>[!example] Primo Step

*Non tocco la prima equazione*
Sommo a ciascuna equazione, dalla $2^a$ in poi, un *multiplo* dilla $1^a$ equazione
- In modo tale che il *coefficiente* di $x_{1}$ **si annulli**

$$
\begin{matrix}
1^a \\
2^a-2\cdot1^a \\
3^a+ 1^a \\
4^a-\frac{1}{2}\cdot 1^a
\end{matrix}
\begin{cases}
2x_{1}-x_{2}+x_{3}+2x_{4}=1 \\
0x_{1}+x_{2}-5x_{3}-5x_{4}=-3 \\
0x_{1}-2x_{2}+2x_{3}+3x_{4} = 2 \\
0x_{1}+\frac{3}{2}x_{2}+\frac{1}{2}x_{3}+0x_{4} = 2
\end{cases}
$$
>[!example] Secondo Step

*Non tocco più la prima e la seconda equazione*.
Sommo a ciascuna equazione, dalla $3^a$ in poi, un *multiplo* dilla $2^a$ equazione
- In modo tale che il *coefficiente* di $x_{2}$ **si annulli**
$$
\begin{matrix}
1^a \\
2^a \\
3^a+2\cdot2^a \\
4^a-\frac{3}{2}2^a
\end{matrix}
\begin{cases}
2x_{1}-x_{2}+x_{3}+2x_{4}=1 \\
0x_{1}+x_{2}-5x_{3}-5x_{4}=-3 \\
0x_{1}-0x_{2}-8x_{3}-7x_{4} = -4 \\
0x_{1}+0x_{2}+8x_{3}+\frac{15}{2}x_{4} = 6
\end{cases}
$$
>[!example] Terzo Step

*Non tocco più la prima, la seconda e la terza equazione*.
Sommo a ciascuna equazione, dalla $4^a$ in poi, un *multiplo* dilla $3^a$ equazione
- In modo tale che il *coefficiente* di $x_{3}$ **si annulli**
$$
\begin{matrix}
1^a \\
2^a \\
3^a \\
4^a+3^a
\end{matrix}
\begin{cases}
2x_{1}-x_{2}+x_{3}+2x_{4}=1 \\
0x_{1}+x_{2}-5x_{3}-5x_{4}=-3 \\
0x_{1}-0x_{2}-8x_{3}-7x_{4} = -4 \\
0x_{1}+0x_{2}+0x_{3}+\frac{1}{2}x_{4} = 2
\end{cases}
$$

>[!done] Step Finale

Ora partendo dall'ultima equazione e salendo troviamo:
$$
\begin{cases}
\frac{1}{2}x_{4} = 2 \implies x_{4}=4 \\
8x_{3}=-4+7x_{4}=-24 \implies x_{3}=-3 \\
x_{2} = 5x_{3}+5x_{4}-3=2 \\
2x_{1} = 1+x_{2}-x_{3}-2x_{4} = -2 \implies x_{1}=-1
\end{cases}
$$
### $\infty$ soluzioni
>Quando ci sono $\infty$ soluzioni, il metodo di gauss mi aiuta a esprimerle in [[Forme Parametriche e Cartesiane#Forme per Descrivere un Sottospazio Vettoriale|forma parametrica]]
#### Esempio
$$
\begin{cases}
x_{1}+x_{2}-3x_{3}+2x_{4}+13x_{5}-8x_{6}=0 \\
0x_{1}+0x_{2}-x_{3}+2x_{4}+x_{5}+x_{6} =0 \\
0x_{1}+0x_{2}+x_{3}-2x_{4}+2x_{5}+11x_{6}=0 \\
0x_{1}+0x_{2}+0x_{3}+0x_{4}+x_{5}+x_{6} =0 \\
0x_{1}+0x_{2}+0x_{3}+0x_{4}-3x_{5}+x_{6}=0 \\
0x_{1}+0x_{2}+0x_{3}+0x_{4}+0x_{5}+7x_{6} =0
\end{cases}
$$

$$
\begin{cases}
x_{1}+x_{2}-3x_{3}+2x_{4}+13x_{5}-8x_{6}=0 \implies x_{1}=s-4t\\
0x_{1}+0x_{2}\cancel{ -x_{3} }+\cancel{ 2x_{4} }+x_{5}+x_{6} =0 x_{2}=s\in\mathbb{R}\\
0x_{1}+0x_{2}+x_{3}-2x_{4}+2x_{5}+11x_{6}=0 \implies x_{3}-2t =0 \implies x_{3}=2t\\
0x_{1}+0x_{2}+0x_{3}+0x_{4}+x_{5}+x_{6} =0 \implies x_{4} = t\in\mathbb{R}\\
0x_{1}+0x_{2}+0x_{3}+0x_{4}-3x_{5}+x_{6}=0 \implies x_{5}=0\\
0x_{1}+0x_{2}+0x_{3}+0x_{4}+0x_{5}+7x_{6} =0 \implies x_{6}=0
\end{cases}
$$
L'insieme delle soluzioni è:
$$
\{ (4t-s,s,2t,t,0,0 ), t,s \in\mathbb{R}\}
$$

## Risoluzione con Matrici
---

>[!abstract] Consideriamo un sistema a $m$ equazioni lineari in $n$ incognite

$$
\begin{cases}
a_{11}x_{1}+a_{12}x_{2}+\dots+a_{1n}x_{n}=b_{1} \\
a_{21}x_{1}+a_{22}x_{2}+\dots+a_{2n}x_{n}=b_{2} \\
\dots \\
a_{m1}x_{1}+a_{m2}x_{2}+\dots+a_{mn}x_{n}=b_{m}
\end{cases}
$$

Dove:
- $(b_{1},b_{2},\dots,b_{m})$ sono i ***termini noti***
- $a_{ij}$ sono i ***coefficienti delle equazioni***

>[!done] Posso scrivere questo sistema nella forma
>$$Ax=b$$
>Dove:
>$A=$ matrice dei ***coefficienti***
>$x=$ vettore delle ***incognite***
>$b=$ vettore dei ***termini noti***

Consideriamo ora un altro metodo di risoluzione
### Metodo di Cramer
>[!Proposizione]
>Sia $Ax=b$ un sistema di $n$ equazioni in $n$ variabili
>- $A\in\mathcal{M}_{n\times n}$
><u>Allora</u>
>- Se $\det(A)=0$ la **soluzione** *non esiste* o *non è unica*
>- Se $\det(A)\neq 0$ la **soluzione** *esiste* ed è *unica* ed è data da:
>$$x=A^{-1}b=\det(A)^{-1}\text{cof}(A)^Tb$$

#### Dimostrazione
>Se $\det(A)=0$, $A$ non è ***invertibile***

- L'applicazione $x\mapsto A$ non è ***biunivoca***

Se non è ***biunivoca***:

>[!abstract] Non è suriettiva
>Non esiste $x:Ax=b$
><u>Ovvero</u>
>La soluzione ***non esiste***

*Oppure*

>[!abstract] Non è iniettiva
>Per qualche $b$ esistono $x,x':Ax=b=Ax'$
><u>Ovvero</u>
>La soluzione ***non è unica***

>Se $\det(A)\neq 0$

- $A$ è ***invertibile***, $A^{-1}=\det(A)^{-1}\text{cof}(A)^T$

$$
Ax=b\implies x=A^{-1}b
$$
È l'***unica soluzione*** del *sistema lineare*

##### Esercizio 1
$$
\begin{cases}
x-2y=3 \\
-2x+4y = 7
\end{cases}\implies\det\begin{pmatrix}
1 & -2 \\
-2 & 4
\end{pmatrix}=0
$$
- Il sistema *non ha soluzione* poiché la prima equazione equivale a:
	- $-2(x-2y)=-2\cdot3=-6\neq 7$

##### Esercizio 2
$$
\begin{cases}
x-2y=3 \\
-2x+4y =-6
\end{cases}\implies\det\begin{pmatrix}
1 & -2 \\
-2 & 4
\end{pmatrix}=0
$$
- Il sistema ha *infinite soluzioni*
	- Tutti gli $(x,y):x=3+2y$
