## Disuguaglianza di Chebyshev
---
>Sia $X$ una ***variabile aleatoria discreta***

>[!info] $\forall\varepsilon>0$
>$$\mathcal{P}(|X-E[X]| >\varepsilon)\leq \displaystyle{\frac{Var(X)}{\varepsilon^2}}$$

##### Esempio
>$X\quad E[X]=2\quad Var(X)=\frac{1}{100}$

Scelgo $\varepsilon=1$

$$
\mathcal{P}(|X-2| >1)\leq \frac{1}{100}
$$
Scelgo $\varepsilon=\frac{1}{2}$

$$
\mathcal{P}\left( |X-2| > \frac{1}{2} \right)\leq \frac{\frac{1}{100}}{\frac{1}{4}}=\frac{4}{100}
$$
### Dimostrazione
>$A=\{ \mid X-E[X]\mid> \varepsilon \}$

$$
\chi_{A}=\begin{cases}
1 \quad \text{se } A \text{ accade} \\
0 \quad \text{se } A \text{ non accade}
\end{cases}
$$
- $\chi_{A}=B(1,\mathcal{P}(A))$

>[!abstract] Ora considero

$Y=\varepsilon^2 \chi_{A}$ e $Z=(X-E[X])^2$

>Confrontiamo $Y$ e $Z$, in particolare, *mostriamo* che $Y\leq Z$

>[!example] Due Casi
>>[!note] $A$ ***non*** accade
>>$Y=\varepsilon^2\cdot 0 = 0$
>>$Z\geq 0$, poiché un qualsiasi valore$^2$ è $\geq 0$
>
>>[!asd] $A$ ***accade***
>>$Y=\varepsilon^2$
>>$Z\geq \varepsilon^2$

>Deduciamo quindi, che:

$$
E[Y]\leq E[Z]
$$
$$
\varepsilon^2\cdot\mathcal{P}(A)\leq Var(X)
$$

### Esempio
>Lanciamo una moneta "***tante volte***"

- $n=\#$ ***lanci della moneta***

$$
X\sim B\left( n, \frac{1}{2} \right)
$$
- $X=\#$ teste su $n$ *lanci*

>[!question] Cosa possiamo dire sulla quantità: $\frac{X}{n}$ ?

>[!attention] Ad intuito
>$$\begin{array}\ n\to \infty \\\displaystyle\frac{X}{n}\to \frac{1}{2}\end{array}$$
>Ci aspettiamo che per $n$ *grandi* si avvicini ad $\frac{1}{2}$


>Fissiamo $0.51$ (un po' più di $\frac{1}{2}$)

