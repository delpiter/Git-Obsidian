## Successioni esponenziali
- - -
### $a>1$
$$
\lim\limits_{n\to+\infty}a^n = +\infty
$$
![[Pasted image 20231013181132.png]]

#### Dimostrazione
Voglio dimostrare che $\lim\limits_{n\to+\infty}a^n=+\infty, \ \ \ a>1$
- Utilizzo la disugualianza di bernoulli
	- Poichè $a$ è maggiore di $1$ lo posso scrivere come $a=1+h$ con $h>1$
	- $(1+h)^n\geq 1+nh$
		- Conosco già il limite di $1+nh$ e quindi per il teorema del confronto $a^n$ con $a>1$ tende a $+\infty$
### $0<a<1$
$$
\lim\limits_{n\to+\infty}a^n=0
$$
![[Pasted image 20231013181733.png]]

#### Dimostrazione


### $-1<a<0$
$$
\lim\limits_{n\to+\infty}a^n=0
$$
![[Pasted image 20231013182133.png]]

#### Dimostrazione
Voglio dimostrare che $\lim\limits_{n\to+\infty}a^n=0, \ \ \ -1<a<0$
- $|a^n|=|a|^n$
	- Sappiamo già che $|a|^n, 0<a<1$ tende a $0$
	- Quindi anche $|a^n|$ deve tendere a $0$
### $a<-1$
$$
\nexists\lim\limits_{n\to+\infty}
$$
- poichè il valore di $a^n$ con $a<-1$ oscilla costantemente fra $\pm\infty$
- L'insieme dei termini è
$$
\{|a|^{2n}|n\in\mathbb{N}\}\cup\{-|a|^{2n+1}|n\in\mathbb{N}\}
$$
### Riassumendo
$$
\lim\limits_{n\to+\infty}a^n \begin{cases}
+\infty\text{ se }a>1 \\
0 \text{ se }0<a<1 \\
1 \text{ se } a=1 \\
\nexists \text{ se } a\leq-1
\end{cases}
$$
## Ordini di Grandezza
---
>[!tldr] Condizioni
>Siano $p>0$ e $a>1$
>Esistono i seguenti ordini di grandezza:
>$$n^p<a^n<n!<n^n$$

## Successioni Trascurabili
---
>[!info] Definizione
>Siano $(a_{n}),(b_{n})_{n\in\mathbb{N}}$ successioni reali, diciamo che $a_{n}$ è **trascurabile** rispetto a $b_{n}$ se:
> $$
\lim\limits_{n\to+\infty} \displaystyle{\frac{a_{n}}{b_{n}}}=0
>$$
>In tal caso scriviamo:
>$a_{n}=\small_{o}(b_{n})$
>>[!done] In breve
>>La successioni $a_{n}$ è trascurabile rispetto a $b_{n}$ quando il limite del rapporto $\displaystyle{\frac{a_{n}}{b_{n}}}$ è uguale a $0$

### Calcoli con $_{o}(\dots)$
- se $a_{n}=_{o}(b_{n}),c_{n}=_{o}(b_{n}) \implies a_{n}+c_{n}=_{o}()b_{n}$
- se $a_{n}=_{o}(b_{n}),c_{n}=_{o}(d_{n})\implies a_{n}\cdot c_{n}=_{o}(b_{n}\cdot d_{n})$
- se $a_{n}=_{o}(b_{n}),a_{n}\cdot c_{n}=_{o}(b_{n}\cdot c_{n})$
