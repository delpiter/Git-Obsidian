## Rapporto Incrementale
---
>[!info] Definizione
>Sia $f:(a,b)\to\mathbb{R}$, siano $c,d\in(a,b)$
>Chiamiamo il rapporto incrementale di $f$ tra $c$ e $d$:
>$$\displaystyle{\frac{f(d)-f(c)}{d-c}}$$
>>[!done] In breve
>>È il rapporto fra la differenza di due punti nell'asse delle $x$ e i corrispettivi valori della funizione

### Osservazione Geometrica
La retta passante per i punti $(c,f(c))$ e $(d,f(d))$ ha come equazione:
$$
\displaystyle{\frac{y-f(d)}{f(d)-f(c)}} = \displaystyle{\frac{x-d}{d-c}} \implies \underbrace{\displaystyle{\frac{f(d)-f(c)}{d-c}}}_{\displaystyle{\text{Rapporto Incr.}}}\cdot(x-c)+f(c)
$$
>[!done] In breve
>Il rapporto incrementale è il coefficiente angolare della retta secante passante per i due punti $(c,f(c))$ e $(d,f(d))$ 

![[Pasted image 20231027100008.png]]
## Derivata
---
>[!info] Definizione
>Sia $f:(a,b)\to\mathbb{R}$, sia $c\in(a,b)$ diciamo che $f$ è derivabile in $c$ se
>$$\exists \lim\limits_{x\to c} \displaystyle{\frac{f(x)-f(c)}{x-c}} \in \mathbb{R}$$
>E in tal caso indichiamo tale [[Limiti#Definizione Limite|limite]] con $f'(c)$ come  derivata di $f$ in $c$
>>[!done] Significato Geometrico
>>La derivata è il coefficente angolare della retta tangente al grafico di $f$ nel punto $(c,f(c))$

### Osservazione sul grafico
- Con $c$ che tende sempre di più al valore di $x$ la retta secante fra i due punti tenderà smpre di più a diventare la tangente
![[Pasted image 20231027102103.png]]

### Teorema di Caratterizzazione delle Funzioni Derivabili
>[!info] Teorema
>Sia $f:I\to\mathbb{R}$, sia $c\in I$
><u>Allora</u>
>Le due seguenti affermazioni sono equivalenti
>$f$ è derivabile in $c$
>$\exists l\in\mathbb{R}:f(x)=f(c)+l(x-c)+\circ(x-c) \text{ per }x\to c$
>e si ha: $l = f'(c)$
>>[!done] In breve
>>Quando $x$ è "molto vicina" a $c$ la funzione è "molto vicina" ad un polinomio di primo grado più un errore trascurabile

#### Dimostrazione
Voglio mostrare che $1\Leftrightarrow 2$
$$
\begin{array}
\ \lim\limits_{x\to c} \displaystyle{\frac{f(x)-f(c)}{x-c}}=l \Leftrightarrow \lim\limits_{x\to c} \displaystyle{\frac{f(x)-f(c)}{x-c}}-l = 0 \\
f(x)-f(c) = l(x-c)+\circ(x-c) \text{ per } x\to c \\
f(x) = l(x-c)+\circ(x-c) \text{ per } x\to c
\end{array}
$$