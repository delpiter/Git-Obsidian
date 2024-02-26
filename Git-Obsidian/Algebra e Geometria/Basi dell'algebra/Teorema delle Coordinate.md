## Teorema
---
>[!info] Enunciato
>Un insieme di vettori $v_{1},\dots,v_{n}$ è una [[Campi e Spazi Vettoriali#Base|base]] di $V\Leftrightarrow$ Ogni $v\in V$ si scrive in modo unico come [[Campi e Spazi Vettoriali#Combinazioni Lineari|combinazione lineare]]
>Cioè:
>$$\forall v\in V \exists!(a_{1},\dots,a_{n}),a_{i}\in \mathbb{K}:v=a_{1}v_{1}+\dots+a_{n}v_{n} $$
>In tal caso $a_{1},\dots,a_{n}$ sono dette le **coordinate del vettore** $v$ nella base $a_{1},\dots,a_{n}$

### Dimostrazione
> $\implies$

Siano $v_{1},\dots,v_{n}$ una base di $V$, cioè *generano* $V$ e sono *linearmenre indipendenti*
- Dunque $\forall v\in V, \exists a_{1},\dots,a_{n}:v=a_{1}v_{1}+\dots,a_{n}v_{n}$

>[!tip] Vediamo perchè $a_{1},\dots,a_{n}$ sono unici

Supponiamo che esistano anche $b_{1},\dots,b_{n}, b_{n}\in \mathbb{K}:V=b_{1}v_{1}+\dots,b_{n}v_{n}$
- Oltre a $v=a_{1}v_{1}+\dots+a_{n}b_{n}$
$$\underline{0}=v-v=(a_{1}-b_{1})v_{1}+\dots+(a_{n}-b_{n})v_{n}$$
Ma poichè $v_{1},\dots,v_{n}$ sono linearmente indipendenti, ciò implica che 
$$a_{1}-b_{1}=0,\dots,a_{n}-b_{n}=0$$
- L'unica combinazione che da il vettore nullo è mettere tutti i coefficienti a $0$
Quindi:
- $a_{1}=b_{1},\dots,a_{n}=b_{n}$

>$\impliedby$

Siano $v_{1},\dots,v_{n}$ tali che $\forall v\in V,\exists! a_{1},\dots,a_{n}\in \mathbb{K}:v=a_{1}v_{1}+\dots+a_{n}v_{n}$
- Dunque $v_{1},\dots,v_{n}$ *generano* $V$ 
- Poichè dato $\underline{0}\in V$ gli unici  $a_{1},\dots,a_{n}\in\mathbb{K}:a_{1}v_{1}+\dots+a_{n}v_{n}=\underline{0}$ sono $a_{1}=0,\dots,a_{n}=0$

$v_{1},\dots,v_{n}$ sono *linearmente indipendenti* dunque sono una **base**

### Esempi
>[!tip] Siano $v_{1}=(-1,0),v_{2}=(2,0)\in V=\mathbb{R}^2$

Non sono nè generatori ne linearmente indipendenti
- In effetti in $\mathbb{R}^2$ ci sono *vettori* che non sono combinazione lineare di $v_{1},v_{2}$ ad esempio:
	- $u =(2,3)$
- E ci sono vettori che sono combinazione lineare di $v_{1},v_{2}$ in infiniti modi, ad esempio:
	- $w_{1}=(4,0)=2v_{2}=v_{2}-2v_{1}=-4v_{1}=\dots$

>[!tip] Siano $v_{1}=(2,1),v_{2}=(1,-1)\in V = \mathbb{R}^2$

>[!question] È vero che ogni $v\in\mathbb{R}^2$ è loro combinazione lineare?

Cioè che:
$$
\forall v=(x,y)\in\mathbb{R}^2,\ \exists !a_{1},a_{2}\in\mathbb{R}:a_{1}v_{1}+a_{2}v_{2}=v 
$$
- $(2a_{1}+a_{2},a_{1}-a_{2})=(x,y)$
$$
\begin{cases}
2a_{1}+a_{2} = x \\
a_{1}-a_{2} = y
\end{cases}
\Leftrightarrow
\begin{cases}
3a_{1}=x+y \\
3a_{2}=x-2y
\end{cases}
\Leftrightarrow\begin{cases}
a_{1}=\displaystyle{\frac{x+y}{3}} \\
a_{2}=\displaystyle{\frac{x-2y}{3}}
\end{cases}
$$
>[!done] Si, è vero

$\forall v\in V$ gli scalari $a_{1},a_{2}$ esistono e sono unici
- $v_{1},v_{2}$ è una base

>[!tip] $v_{1}=(1,1),v_{2}=(2,2)$

>[!question] È vero che $\forall v = (x,y)\in \mathbb{R}^2, \exists !a_{1},a_{2}\in\mathbb{R}:v=a_{1},a_{1}+a_{2}v_{2}$?

$$
(x,y)=(a_{1}+2a_{2},a_{1}+2a_{2})
$$
$$
\begin{cases}
a_{1}+2a_{2} =x \\
a_{1}+2a_{2} =y
\end{cases}
\begin{cases}
a_{1}=x-2a_{2} \\
0=x-y
\end{cases}
$$
>[!danger] Non ho soluzione per tutti i vettori $(x,y)$

Ma solo per quelli che hanno le due coordinate uguali
- $v_{1},v_{2}$ non generano $\mathbb{R}^2$

