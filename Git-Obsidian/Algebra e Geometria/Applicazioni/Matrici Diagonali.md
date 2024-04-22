>*Sia $f$ un [[Isomorfismo#Endomorfismo|endomorfismo]] abbiamo visto che data una base $v_{1},\dots,v_{n}$ di $V$ possiamo associare ad $f$ una matrice $n\times n$ che dipende dalla base scelta*

>[!question] Possiamo scegliere la base di $V$ in modo che la matrice di $f$ sia particolarmente semplice?

## Matrice Diagonale
---
>[!info] Definizione
>Una *matrice* $D_{n\times n}$ è ***diagonale*** se:
>$$d_{ij}=0, \forall i\neq j$$

$$
D=\begin{pmatrix}
d_{1} & 0 & \dots & 0 & 0 \\
0 & d_{2} & \dots & 0 & 0 \\
0 & 0 & \dots & 0 & 0 \\
\dots  & \dots & \dots & \dots & \dots \\
0 & 0 & \dots & d_{n-1} & 0 \\
0 & 0 & \dots & 0 & d_{n}
\end{pmatrix}
$$

>[!tldr] Osservazione
>Due *matrici diagonali* sono semplici da moltiplicare tra loro!

Infatti, se:
$$
D=\begin{pmatrix}
d_{1} & 0 & \dots & 0 & 0 \\
0 & d_{2} & \dots & 0 & 0 \\
0 & 0 & \dots & 0 & 0 \\
\dots  & \dots & \dots & \dots & \dots \\
0 & 0 & \dots & d_{n-1} & 0 \\
0 & 0 & \dots & 0 & d_{n}
\end{pmatrix},
E=\begin{pmatrix}
e_{1} & 0 & \dots & 0 & 0 \\
0 & e_{2} & \dots & 0 & 0 \\
0 & 0 & \dots & 0 & 0 \\
\dots  & \dots & \dots & \dots & \dots \\
0 & 0 & \dots & e_{n-1} & 0 \\
0 & 0 & \dots & 0 & e_{n}
\end{pmatrix}
$$
$$
D\times E=\begin{pmatrix}
d_{1}e_{1} & 0 & \dots & 0 & 0 \\
0 & d_{2}e_{2} & \dots & 0 & 0 \\
0 & 0 & \dots & 0 & 0 \\
\dots  & \dots & \dots & \dots & \dots \\
0 & 0 & \dots & d_{n-1}e_{n-1} & 0 \\
0 & 0 & \dots & 0 & d_{n}e_{n}
\end{pmatrix}
$$
>[!done] Ottengo una *matrice diagonale*

>***Inoltre***, $\forall m\in \mathbb{Z}$


$$
D^m=\begin{pmatrix}
d_{1}^m & 0 & \dots & 0 & 0 \\
0 & d_{2}^m & \dots & 0 & 0 \\
0 & 0 & \dots & 0 & 0 \\
\dots  & \dots & \dots & \dots & \dots \\
0 & 0 & \dots & d_{n-1}^m & 0 \\
0 & 0 & \dots & 0 & d_{n}^m
\end{pmatrix}
$$

>[!tldr] Osservazione
>Calcolare il [[Determinante di una Matrice#Determinante|determinante]] è *estremamente banale*

$$
\det(D)=d_{1}\cdot d_{2}\cdot ...\cdot d_{n}
$$
>[!tldr] Osservazione
>Se il $\det(D)\neq 0$, la ***matrice inversa*** è *estremamente banale* da calcolare

$$
D^{-1}=\begin{pmatrix}
d_{1}^{-1} & 0 & \dots & 0 & 0 \\
0 & d_{2}^{-1} & \dots & 0 & 0 \\
0 & 0 & \dots & 0 & 0 \\
\dots  & \dots & \dots & \dots & \dots \\
0 & 0 & \dots & d_{n-1}^{-1} & 0 \\
0 & 0 & \dots & 0 & d_{n}^{-1}
\end{pmatrix}
$$
>***Inoltre***

$$
D\begin{pmatrix}
d_{1} & 0 & \dots & 0 & 0 \\
0 & d_{2} & \dots & 0 & 0 \\
0 & 0 & \dots & 0 & 0 \\
\dots  & \dots & \dots & \dots & \dots \\
0 & 0 & \dots & d_{n-1} & 0 \\
0 & 0 & \dots & 0 & d_{n}
\end{pmatrix}
\times
D^{-1}\begin{pmatrix}
d_{1}^{-1} & 0 & \dots & 0 & 0 \\
0 & d_{2}^{-1} & \dots & 0 & 0 \\
0 & 0 & \dots & 0 & 0 \\
\dots  & \dots & \dots & \dots & \dots \\
0 & 0 & \dots & d_{n-1}^{-1} & 0 \\
0 & 0 & \dots & 0 & d_{n}^{-1}
\end{pmatrix}=
I_{n}
$$

>[!done] Le matrici diagonali sono *MERAVIGLIOSE*

## Autovettore e Autovalore
---
>[!info] Definizioni
>>[!abstract] Autovettore
>>Sia $f:V\to V$ un [[Isomorfismo#Endomorfismo|endomorfismo]] un ***autovettore*** è un vettore
>>$$v\in V, v\neq 0:\exists \lambda \in \mathbb{K}:f(v)=\lambda v$$
>
>>[!abstract] Autovalore
>>Un numero $\lambda\in\mathbb{K}$ è detto ***autovalore*** se
>>$$\exists v\in V,v\neq 0:f(v)=\lambda v$$

#### Esempio
>*Sia $f:\mathbb{R}^2\to \mathbb{R}^2:f(x,y)=(2y,2x)$*

- $e_{1}$ non è un *autovettore* $\implies f(e_{1})=2e_{2}$
- $e_{2}$ non è un *autovettore* $\implies f(e_{2})=2e_{1}$
