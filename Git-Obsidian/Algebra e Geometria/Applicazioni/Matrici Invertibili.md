>*Il [[Determinante di una Matrice|determinante]] permette di dire se una matrice $A$ è invertibile*

>[!question] In caso affermativo, come trovo $A^{-1}$?

## Matrice Inversa
---
>[!Teorema]
>$$A^{-1}=\frac{1}{\det(A)}\cdot \text{cof}(A)^T$$
>Dove il ***cofattore*** è definito nel seguente modo:
>$$\text{cof}(A)_{ij}=(-1)^{i+j}\det(A^{ij})$$
>>[!done] A Parole
>>La matrice inversa è definita dall'inverso del [[Determinante di una Matrice|determinante]] moltiplicato per il [[Definizioni_Analisi#Matrice Trasposta|trasposto]] del *cofattore*

#### Esercizio
$$
A=\begin{pmatrix}
3 & 5 \\
2 & 4
\end{pmatrix}
$$
$$
\det(A)=(3\cdot4)-(2\cdot5) = 2\neq0
$$
- $A$ è *invertibile*
$$
\begin{array}
\ \text{cof}(A)=\begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{pmatrix} \\
a_{11}=\det(4)\cdot(-1)^{1+1} \\
a_{21}=\det(2)\cdot(-1)^{2+1} \\
a_{12}=\det(5)\cdot(-1)^{2+1} \\
a_{22}=\det(4)\cdot(-1)^{2+2}
\end{array}
$$
$$
\text{cof}(A)=\begin{pmatrix}
4 & -2 \\
-5 & 3
\end{pmatrix}\implies\text{cof}(A)^T=\begin{pmatrix}
4 & -5 \\
-2 & 3
\end{pmatrix}
$$

Ora moltiplichiamo per l'***inverso del determinante***
$$
A^{-1}=\frac{1}{2}\begin{pmatrix}
4 & -5 \\
-2 & 3
\end{pmatrix}=\begin{pmatrix}
2 & \displaystyle-\frac{5}{2} \\
-1 & \displaystyle \frac{3}{2}
\end{pmatrix}
$$
>[!done] Infatti

$$
A\times A^{-1}=\begin{pmatrix}
3 & 5 \\
2 & 4
\end{pmatrix}\times\begin{pmatrix}
2 & -\frac{5}{2} \\
-1 & \frac{3}{2}
\end{pmatrix}=I_{2}
$$