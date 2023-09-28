> Siano $A$ e $B \neq \varnothing$  chiamiamo funzione da $A$ a $B$ una legge che ad ogni elemento di $A$ associa uno ed un solo elemento di $B$
 
$$f:A\rightarrow B$$
- Dove $A$ rappresenta il dominio della funzione e $B$ il codominio
$$\forall x \in A, \exists y \in B : y = f(x)$$
## Dominio e Codominio e Immagine
#### Dominio
>L'insieme dei valori possibili che la variabile $x$ può assumere
- L'insieme su cui è definita la funzione.
#### Codominio
>È l'insieme dove sono contenute tutte le immagini della funzione

#### Immagine
>Il sottoinsieme di $y$ costituito dai valori effettivamente assunti dalla funzione $f$ è invece detto immagine
$$f(A)=\{y\in B\;|\;\exists; x\in A:f(x)=y\}$$
---
## Grafico di una Funzione
>Siano $A$ e $B \neq \varnothing$, sia $f: A \rightarrow B$ chiamiamo grafico di $f$, l'insieme 
$$y_f =\{(a,b) \in A\times B \; | b=f(a)\}$$


```functionplot
---
title: Piano Cartesiano
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: false
grid: true
---

```

#### Iniettività e surriettività
###### Surriettività $[f\;su]$
>Diciamo che $f$ è surriettiva se $f(A)=B$
>>Cioè se per ogni elemento del codominio, c'è almeno un elemento del domino associato
$$\forall x \in B, \exists \; x \in A | f(x)=y$$
- Tutte le funzioni possono essere surriettive
	- Basta restringere il codominio
###### Iniettività $[f\;1-1]$
>Diciamo che $f$ è iniettiva se:
>>Ogni elemento del dominio ha una immagine distinta
$$\forall y \in f(A), \exists! \;x \in A | f(x)=y$$
- Oppure se $f(x_1) = f(x_2) \Rightarrow x_1=x_2$
###### Funzione invertibile
>Diciamo che $f$ è invertibile (Biettiva o Biunivoca) se è sia iniettiva che surriettiva

###### Funzione inversa
> Sia $f:A\rightarrow B$ invertibile chiamiamo funzione inversa di $f$ la funzione
$$f^-1:B\rightarrow A$$
- Definita come segue
	- $\forall y\in B,f^-1(y)$ è l'unica soluzione dell'equazione $f(x)=y$

## Composizione
>Siano $f:A\rightarrow B, \;g:C\rightarrow D$
>Supponiamo che $f(A)\subseteq C$ (se $f(x)$ esce dal dominio di $g$ non è possibile)
>chiamiamo funzione composta
>$$g_of \;A\rightarrow D$$
>La funzione:
$$(g_of)(x)=g(f(x))$$
- Importante l'ordine con cui si compongono
	- Non è sempre detto sia possibile farlo in entrambi i versi ($g_of$ e $f_og$)
	- E anche se fosse possibile in generale $g_of\neq f_og$

#### Funzione Identità
>La funzione identità è una particolare funzione che associa ad ogni $x$ la $x$ stessa
$$Id_a: A\rightarrow A$$
$$x\mapsto x$$

```functionplot
---
title: Funzione Identità
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: false
grid: true
---
y=x
```

###### Osservazione
- Sia $f$ una funzione invertibile allora
$$(f_of^{-1})(x) = x \;\; \forall x \in B$$
$$(f^{-1}_of)(x) = x \;\; \forall x \in A$$

## Intervallo
- - -
>Diciamo che $I \subseteq \mathbb{R}$ è un intervallo se $\forall x,y \in I$ ($x>y$) e $\forall z \in \mathbb{R}: x<z<y$
>si ha $z \in I$
>	Presi due numeri $x\; e \;y$ all'interno dell'insieme si dice intervallo se per ogni $z$ preso fra $x$ e $y$
>	anche $z$ è interno all'insieme
###### Es
- È un intervallo:
$$
I={x \in \mathbb{R} | 1<x<52}
$$
- Non è un intervallo
$$
A={x \in \mathbb{R} | x<1 \vee x > 7}
$$

### Notazioni
> Dati $a,b \in \mathbb{R}$
- $]a,b[ = \{x \in \mathbb{R} | a<x<b\}$
- $[a,b] = \{x \in \mathbb{R} | a\leq x\leq b\}$
	- Intervallo chiuso
- È possibile mischiare le notazioni
- $]a,b] = \{x \in \mathbb{R} | a<x\leq b\}$
- $+ \infty$ non è un numero reale è solo una notazioni
	- Per convenzione quindi è escluso dalla notazione
	- $[a,+\infty[ = \{x \in \mathbb{R} | x\geq a\}$

## Limitazioni
- - -
>Siano $A \subseteq \mathbb{R}, \;f:A\to\mathbb{R}$ diciamo che $f$ è limitata superiormente o inferiormente se lo è $f(A)$ (l'immagine)
###### Es
$$
\begin{array}
/f:\mathbb{R}\to\mathbb{R}, f(x)=x^2 \\
f(\mathbb{R})=\mathbb{R}^+=\{x \in \mathbb{R}|x\geq 0\}
\end{array}
$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: false
grid: true
---
f(x)=x^2
```

- $f$ è limitata inferiormente ma non superiormente
### Estremi superiori e inferiori
- Nelle funzioni esistono e sono sempre unici gli estremi superiori e inferiori
	- A differenza dei punti di minimo e di massimo
##### Superiore
>Definiamo l'estremo superiore come
$$
\sup\limits_{A}f:=supf(A)
$$
##### Inferiore
>Definiamo l'estremo inferiore come
$$
\inf\limits_{A}f:=inff(A)
$$
### Massimo e minimo
- Non è sempre possibile che ci sia un punto di massimo o di minimo
>Diciamo che $f$ ammette un massimo, se $f(A)$ ammette il massimo
$$
\max\limits_{A}f:=maxf(A)
$$
>Analogamente diciamo che $f$ ammette un minimo, se $f(A)$ ammette il minimo
$$
\min\limits_{A}f:=minf(A)
$$
###### Es
$$
\begin{array}
/f:\mathbb{R}\to\mathbb{R} \\
x \mapsto (x-2)^2
\end{array}
$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-2,5,-2,5]
disableZoom: false
grid: true
---
f(x)=(x-2)^2
```
$$
\begin{array} \\

\sup\limits_{\mathbb{R}}f:=+\infty \\
\inf\limits_{\mathbb{R}}f:=0 \\
x=2\text{ Punto di minimo di }f
\end{array}
$$