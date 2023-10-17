## Limiti per funzioni Variabile Reale
---
### Intorni
>[!info] Definizione
>Dato $c\in\mathbb{R}$, chiamiamo intorno del punto $c$ un qualsiasi [[Introduzione Funzioni#Intervallo|intervallo]] della forma
>$$(c-r,c+r)$$
>Chiamiamo invece intorno di $+\infty$ un qualsiasi intervallo della forma 
>$$(a,+\infty)$$
>Chiamiamo invece intorno di $-\infty$ un qualsiasi intervallo della forma
>$$(a,-\infty)$$

#### Osservazione
>$U$ è un intorno di $c$ se $$\exists r>0:U=(c-r,c+r)$$
- Cioè $x\in U \Leftrightarrow |x-c|<r$

>$U$ è un intorno di $+\infty$ se $$\exists a>0:U=(a,+\infty)$$
- Cioè $x\in U \Leftrightarrow a<+\infty$

>$U$ è un intorno di $-\infty$ se $$\exists b>0:U=(-\infty,b)$$
- Cioè $x\in U \Leftrightarrow b>-\infty$

### Definizione Limite
>[!info] Definizioni
>Elenchiamo di seguito 2 definizioni uguale di limite
>>[!example] Definizione con definizione di [[Limiti di Successioni#Definizioni|successione]]
>>Sia $I$ un [[Introduzione Funzioni#Intervallo|intervallo]] o un [[Introduzione Funzioni#Intervallo Forato|intervallo forato]]
>>Sia $f:I\to \mathbb{R},c\in[inf(I),sup(I)]$ ([[Insiemi Numerici#Insiemi Limitati|limitazioni]]),$l\in\overline{\mathbb{R}}$
>>Diciamo che $\exists\lim\limits_{x\to+\infty}f(x)=l$ se:
>>$$\forall(a_{n})_{n\in\mathbb{N}}\text{ successione in }I\setminus\{ c \}:\lim\limits_{n\to+\infty}a_{n}=c$$
>>Si ha
>>$$\lim\limits_{n\to +\infty}=l$$
>>>[!done] In breve
>>>Comunque io scelga una successione di punti che tende a $c$, quando ad $a_{n}$ applico la funzione il valore deve tendere a $l$
>
>>[!example] Definizione 2
>>Sia $I$ un [[Introduzione Funzioni#Intervallo|intervallo]] o un [[Introduzione Funzioni#Intervallo Forato|intervallo forato]]
>>Sia $f:I\to \mathbb{R},c\in[inf(I),sup(I)]$ ([[Insiemi Numerici#Insiemi Limitati|limitazioni]]),$l\in\overline{\mathbb{R}}$
>>Diciamo che $\exists\lim\limits_{x\to+\infty}f(x)=l$ se:
>>$$\forall \mathrm{V} \text{ intorno di } l, \exists \mathrm{U}_{\mathrm{V}}\text{ intorno di }c: \forall x\in\mathrm{U}_{\mathrm{V}}\setminus\{c\}$$
>>Si ha: $f(x)\in\mathrm{V}$

#### Teorema del "ponte"
- Il teorema del ponte enuncia che le due definizioni precedenti sono equivalenti
##### Esempio
###### Caso $l,c\in\mathbb{R}$
$$
\forall\mathcal{E}>0,\exists \delta_{\mathcal{E}}>0:\text{ se }|x-c|<\delta_{\mathcal{E}} \text{ si ha }|f(x)-l|<\mathcal{E}, x\neq c
$$
###### Caso $l,c\in\overline{\mathbb{R}}$


#### Esercizio