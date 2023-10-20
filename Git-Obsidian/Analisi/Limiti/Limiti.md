## Limiti per funzioni ad una Variabile Reale
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
###### Spiegazione grafica
![[Pasted image 20231020102454.png]]
Fissato un $\mathcal{E} >0$, esiste un $\delta>0$
- Tale che $\forall x$ nell'intervallo $(c-\delta,c+\delta)$ si ha che $f(x)$ deve cadere nell'intervallo $(l-\mathcal{E},l+\mathcal{E})$
###### Caso $l,c\in\overline{\mathbb{R}}$
?
#### Esercizio

## Proprietà dei limiti
---
- Le proprietà dei limiti di funzione sono analoghe a quelle per le successioni
### Unicità del limite
>[!info] Definizione
>Sia $I$ un [[Introduzione Funzioni#Intervallo|intervallo]] o un [[Introduzione Funzioni#Intervallo Forato|intervallo forato]]
>Sia $f:I\to \mathbb{R},c\in[inf(I),sup(I)]$ ,$m,l\in\overline{\mathbb{R}}$
>Se $$\lim\limits_{x\to c}f(x)=l \text{ e } \lim\limits_{x\to c}f(x)=m$$
><u>Allora</u>
>$l=m$

### Teorema della permanenza del segno
>[!info] Definizione
>Sia $I$ un [[Introduzione Funzioni#Intervallo|intervallo]] o un [[Introduzione Funzioni#Intervallo Forato|intervallo forato]]
>Sia $f:I\to \mathbb{R},c\in[inf(I),sup(I)]$ ,$l\in\overline{\mathbb{R}}$
>Supponiamo che $$\lim\limits_{x\to c}f(x)=l$$
><u>Allora</u>
>Se $l>0$
>$$\exists \text{ un intorno }\mathrm{U} \text{ di c }:f(x)>0\ \ \forall x\in\mathrm{U}\cap I \setminus\{ c \}$$
>Se $l<0$
>$$\exists \text{ un intorno }\mathrm{U} \text{ di c }:f(x)<0\ \ \forall x\in\mathrm{U}\cap I \setminus\{ c \}$$

### Teorema dei due Carabinieri
>[!info] Definizione
>Sia $I$ un [[Introduzione Funzioni#Intervallo|intervallo]] o un [[Introduzione Funzioni#Intervallo Forato|intervallo forato]]
>Sia $f,g,h:I\to \mathbb{R},c\in[inf(I),sup(I)]$ ,$l\in\mathbb{R}$
>Se $$\lim\limits_{x\to c}f(x)=l,\ \ \lim\limits_{x\to c}=h(x)=l$$
>E $$\exists \text{ un intorno } \mathrm{U}\text{ di c }:f(x)\leq g(x) \leq h(x), \forall x \in \mathrm{U}\cap\setminus\{ c \}$$
><u>Allora</u>
>$$\lim\limits_{x\to c}g(x)=l$$

### Limiti unilateri
>[!info] Definizione
>Sia $I$ un [[Introduzione Funzioni#Intervallo|intervallo]] o un [[Introduzione Funzioni#Intervallo Forato|intervallo forato]]
>Sia $f:I\to \mathbb{R},c\in[inf(I),sup(I)]\cap\mathbb{R}$ ,$l\in\overline{\mathbb{R}}$
>Diciamo che $f$ ha limite per $x\to c$ da sinistra (scriviamo $x\to c^-$)
>Se ([[Definizioni_Analisi#Notazione Restrizione del dominio|notazione]]) $$\lim\limits_{x\to c}f(x)_{\displaystyle{|_{I\cap(-\infty,c)}}}=l$$
>>[!example] Teorema
>>$$\exists \lim\limits_{x\to c}f(x)\Leftrightarrow \begin{cases}\exists \lim\limits_{x\to c^-}f(x)\\ \lim\limits_{x\to c^+}f(x)\end{cases}$$
>>Tali limiti coincidono

