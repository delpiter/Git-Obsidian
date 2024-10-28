## Introduzione
---
>[!def] Definizione
>Una [[3 - Variabili Aleatorie|variabile aleatoria]] ***bidimensionale*** è una *coppia* $\underline{X}(X_{1},X_{2})$ di ***variabili aleatorie***
>>[!note] Densità
>>Sia $\underline{X}(X_{1},X_{2})$, la sua densità è:
>>$$d_{\underline{X}}=d_{X_{1},X_{2}}(h,k)=\mathcal{P}(X_{1}=h,X_{2}=k)$$

#### Esempio
>Una urna contiene 2 palline *rosse*, 2 *verdi* e 2 *gialle*

>[!cite] Estraiamo 2 palline senza rimpiazzo

$X_{1}=\#$ di verdi estratti
$X_{2}=\#$ di rossi estratti

>[!question] Determina la densità della coppia $X_{1},X_{2}$

Le coppie di valori possibili sono:
- $\underbrace{ (0,0),(2,0),(0,2) }_{ \text{Stessa densità} }$
- $\underbrace{ (1,0),(0,1),(1,1) }_{ \text{Stessa densità} }$

$d(0,0)=\displaystyle\frac{1}{\binom{6}{2}}=\frac{1}{15}$
$d(1,0)=\displaystyle\frac{4}{15}$

$$
d_{X_{1},X_{2}}(h,k)=\begin{cases}
\frac{1}{15} \quad \text{ se }(h,k)=(0,0),(2,0),(0,2) \\
\frac{4}{15} \quad \text{ se }(h,k)=(1,0),(1,1),(0,1) \\
0 \qquad \text{altrimenti }
\end{cases}
$$