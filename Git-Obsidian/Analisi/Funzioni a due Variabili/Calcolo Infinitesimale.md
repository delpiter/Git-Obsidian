## Limiti
---
>[!info] Definizioni
>>[!example] Definizione con successione
>>Diciamo una successione
>>$\{ (x_{n},y_{n}) \}_{n\in\mathbb{N}}$ in $\mathbb{R}^2$ tende a $c=(x_{0},y_{0})$ se:
>>$$|(x_{n},y_{n})-(x_{0},y_{0})|=\sqrt{ (x_{n}-x_{0})^2+(y_{n},y_{0})^2 }\to 0$$
>>>[!done] In breve
>>> La distanza dei punti deve tendere a $0$ da qualsiasi direzione

### Definizione di Intorno
>[!info] Definizione
>Sia $(x_{0},y_{0})\in\mathbb{R}^2$, diciamo che:
>$\mathrm{U}_{(x_{0},y_{0})}$ è un intorno di $(x_{0},y_{0})$ se è della forma:
>$$\mathrm{U}_{(x_{0},y_{0})} = \{ (x,y)\in\mathbb{R}^2 : |(x,y)-(x_{0},y_{0})|<\delta\}$$
>>[!done] In Breve
>> Tutti i punti all'interno di una circonferenza di raggio $\delta$

### Definizione di Limite per $\mathbb{R}^3$
>[!info] Definizione
>>[!example] Definizione con Successione
>>Sia $f:\mathbb{R}^2 \to\mathbb{R}$ Sia $(x_{0},y_{0})\in\mathbb{R}^2,l\in\overline{\mathbb{R}}$
>>Diciamo che:
>>$$\lim\limits_{(x,y)\to (x_{0},y_{0})}f(x,y) = l$$
>>Se $\forall$ successione $\{ (x_{n},y_{n}) \}\in\mathbb{R}^2:$
>>$$(x_{n},y_{n})\to(x_{0},y_{0})$$
>>si ha:
>>$$\lim\limits_{n\to +\infty}f(x_{n},y_{n}) = l$$
>
>Alternativa Equivalente
>
>>[!example] Definizione con Intorno
>>Sia $f:\mathbb{R}^2\to\mathbb{R}$, sia $(x_{0},y_{0})\in\mathbb{R}^2,l\in\overline{\mathbb{R}}$
>>Diciamo che $$\lim\limits_{(x,y)\to (x_{0},y_{0})}f(x,y)=l$$
>>Se $\forall$ intorno $\mathrm{U}_{l}$ di $l$
>>$\exists$ un intorno $\mathrm{U}_{x_{0},y_{0}}:$
>>$$\forall(x,y)\in\mathrm{U}_{(x_{0},y_{0})}$$
>>si ha: 
>>$$f(x,y)\in\mathrm{U}_{l}$$

