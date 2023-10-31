## Estremante Locale
---
>[!info] Definizione
>Sia $I$ intervallo di $\mathbb{R}$, $f:I \to\mathbb{R}$
>Sia $c\in I$
>
>>[!tldr] Minimo
>>Diciamo che $c$ è un punto di minimo locale per $f$ se:
>>$$\exists \delta>0:\forall x \in(c-\delta,c+\delta)\cap I$$
>>E si ha $f(c)\leq f(x)$
>
>>[!tldr] Massimo
>>Diciamo che $c$ è un punto di massimo locale per $f$ se:
>>$$\exists \delta>0:\forall x \in(c-\delta,c+\delta)\cap I$$
>>E si ha $f(c)\geq f(x)$

### Dimostrazione Grafica
![[Pasted Image 202304523.jpg]]

## Teorema di Fermat
---
>[!info] Teorema
>Sia $I$ intervallo di $\mathbb{R}$, $f:I \to\mathbb{R}$
>Sia $c$ [[Definizioni_Analisi#Punto interno in un Intervallo|punto interno]] di $I$
>Supponiamo che $f$ sia derivabile in $c$ e $c$ è estremante locale
><u>Allora</u>
>$f'(c)=0$

### Dimostrazione
Sia $c$ punto di minimo locale
$$
\exists \delta>0:f(c)\leq f(x) \forall x \in(c-\delta,c+\delta)\cap I
$$
>[!done] Alternativa
>Scegliendo $\delta$ sufficientemente piccolo posso supporre che $(c-\delta,c+\delta)\subset I$ poichè $c$ è un punto interno di $I$

##### Considerando il [[Derivate#Rapporto Incrementale|rapporto incrementale]]:
$$
\displaystyle{\frac{f(x)-f(c)}{x-c}}
$$
###### Abbiamo 2 casi:
- $f(x)-f(c)\geq0$ poichè $c$ è un punto di minimo
- Con $\forall x \in(c,c+\delta)$
	- $x-c\geq 0$
	- Quindi il rapporto incrementale è sempre $\geq 0$
- Con $\forall x \in(c-\delta,c)$
	- $x-c\leq 0$
	- Quindi il rapporto incrementale è sempre $\leq0$

###### Passando al Limite

$\lim\limits_{x\to c^+} \displaystyle{\frac{f(x)-f(c)}{x-c}}\geq0$
e
$\lim\limits_{x\to c^-} \displaystyle{\frac{f(x)-f(c)}{x-c}}\leq0$

E poichè $f$ è derivabile $$f'(c) = \lim\limits_{x\to c} \displaystyle{\frac{f(x)-f(c)}{x-c}}=0$$
- Si può fare un ragionamento analogo anche per $c$ punto di massimo locale
### Esempio di $c$ interno ipotesi necessaria
Prendiamo $f(x)=x$ nell'intervallo $[0,1]$
- In questo caso $0$ è punto di minimo, tra l'altro anche assoluto, ma la sua derivata vale $1$
- Il punto $1$ è un punto di massimo, anche assoluto, ma la sua derivata vale $1$

## Teorema di Rolle
---

