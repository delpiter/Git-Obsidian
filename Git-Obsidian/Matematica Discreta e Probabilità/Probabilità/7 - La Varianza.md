>Molto simile alla [[3 - Varianza|Varianza]] in ***statistica***

## Varianza
---
>[!def] Definizione
>La ***varianza*** da una misura della *dispersione* di valori di $X$, tenendo conto delle rispettive ***probabilità***
>$$Var(X)=E[(X-E[X])^2]$$
>Come in *statistica*, la varianza ***non*** si calcola usando la *definizione*
>>[!example] Formula
>>$$Var(X)=E[X^2]-E[X]^2$$

##### Dimostrazione
$$
E[(X-E[X])^2]=E[X^2-2E[X]X+E[X]^2]
$$
- Ora sfrutto la proprietà della [[6 - Valore Atteso#Corollario|somma del valore atteso]]

$$
E[X^2]-2E[X]E[X]+E[X]^2=E[X^2]-E[X]^2
$$

#### Esempi
>$X\sim B(1,p)$

>[!question] $Var(X)?$

- $Var(X)=E[X^2]-E[X]^2=\underbrace{ E[X] }_{ p }-p^2=p(1-p)$

###### Esempio 2
>$X\sim B(2,p)$

- $\displaystyle d_{X}(k)=\binom{2}{k}p^k(1-p)^{2-k}\quad k=0,1,2$

$$
E[X^2]=0^2\cdot  d_{X}(0)+1^2\cdot  d_{X}(1)+2^2\cdot  d_{X}(2)=0+2p(1-p)+4p^2
$$
$$
Var(X)=2p+2p^2-4p^2=2p(1-p)
$$