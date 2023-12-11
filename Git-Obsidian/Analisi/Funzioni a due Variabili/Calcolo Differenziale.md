## Derivata Parziale
---
>[!info] Definizione
>Sia $A\subseteq\mathbb{R}^2$,$f:A\to\mathbb{R}$, $A$ insieme [[Elementi di Algebra Lineare e Geometria Analitica#Insiemi Aperti e Chiusi|aperto]]
>>[!example] Su $x$
>>Diciamo che $f$ è derivabile rispetto ad $x$ nel punto $(x_{0},y_{0})\in A$ se esiste
>>$$\lim\limits_{x\to x_{0}} \displaystyle{\frac{f(x,y_{0})-f(x_{0},y_{0})}{x-x_{0}}}=\lim\limits_{h\to 0} \displaystyle{\frac{f(x_{0}+h,y_{0})-f(x_{0},y_{0})}{h}}\in\mathbb{R}$$
>
>>[!example] Su $y$
>>Analogamente diciamo che $f$ è derivabile rispetto ad $x$ nel punto $(x_{0},y_{0})\in A$ se esiste
>>$$\lim\limits_{y\to y_{0}} \displaystyle{\frac{f(x_{0},y)-f(x_{0},y_{0})}{y-y_{0}}}=\lim\limits_{h\to 0} \displaystyle{\frac{f(x_{0},y_{0}+h)-f(x_{0},y_{0})}{h}}\in\mathbb{R}$$

### Notazioni
- Per indicare la derivata parziale di una funzione di due variabili si posso usare diverse notazioni
$$
\displaystyle{\frac{\partial f}{\partial x}},\displaystyle{\frac{d f}{d x}},f_{x},\partial_{x}f |\displaystyle{\frac{\partial f}{\partial y}},\displaystyle{\frac{d f}{d y}},f_{y},\partial yf
$$
#### Es
- $f(xy)=2xe^{xy}$
$$
\displaystyle{\frac{df}{dx}}(x,y)=2e^{ xy }+ye^{ xy }2x
$$
$$
\displaystyle{\frac{df}{dy}}(x,y)2x^2e^{ xy }
$$
### Derivabilità
>[!tip] Definizione
>Diciamo che $f$ è derivabile in $(x_{0},y_{0})$ se esistono le due derivate parziali:
>$$\displaystyle{\frac{df}{dx}}, \displaystyle{\frac{df}{dy}}$$

#### Osservazione
Sia $f$ derivabile in $(x_{0},y_{0})$ non implica che $f$ sia continua

### Gradiente
>[!info] Definizione
>$$\nabla f(x_{0},y_{0}) = \left( \displaystyle\frac{ \partial f }{ \partial x }(x_{0},y_{0}) ,\displaystyle\frac{ \partial f }{ \partial y }(x_{0},y_{0})  \right)$$
>
# Differenziabilità
## Richiamo
---
![[Derivate#Teorema di Caratterizzazione delle Funzioni Derivabili]]

- Il concetto è equivalente anche per funzioni a due variabili reali
> Qual è l'unico oggetto che è tangente ad una funzione a due variabili in un punto?

## Trovare il Piano Tangente al Grafico
---
#### Primo Passo
- Determinare, nel caso ci sia, l'equazione del piano tangente al grafico di una funzione $f$ nel punto $(x_{0},y_{0})$
>[!info] Svolgimento
>>[!tip] Intersezione Piano $y=y_{0}$
>>Seziono (o interseco) il grafico della funzione con il piano $y=y_{0}$
>>Individuo così la curva descritta da
>>$$z=f(x,y_{0})$$
>
>>[!tip] Intersezione Piano $x=x_{0}$
>>Seziono (o interseco) il grafico della funzione con il piano $x=x_{0}$
>>Ottenendo così la curva descritta da:
>>$$z=f(x_{0},y)$$
>
>![[Untitled-removebg-preview.png]]

#### Passo 2
Mi scrivo le equazioni delle rette tangenti:
$$
z =f(x,y_{0})
$$
$$
\begin{cases}
z=f(x_{0},y_{0})+ \displaystyle{\frac{df}{dx}}(x_{0},y_{0})(x-x_{0}) \\
y=y_{0}
\end{cases}
$$
$$
z=f(x_{0},y)
$$
$$
\begin{cases}
z=f(x_{0},y_{0})+ \displaystyle{\frac{df}{dy}}(x_{0},y_{0})(y-y_{0}) \\
x=x_{0}
\end{cases}
$$
![[pngegg.png]]
#### Il Piano
Esiste un piano che contiene entrambe le rette:

>[!info] Definizione
>Se $f$ ammette un piano tangente nel punto $(x_{0},y_{0},f(x_{0},y_{0}))$, esso ha necessariamente l'equazione:
>$$
z=f(x_{0},y_{0})+ \displaystyle{\frac{df}{dx}}(x_{0},y_{0})(x-x_{0})+ \displaystyle{\frac{df}{dy}}(x_{0},y_{0})(y-y_{0})
>$$

## Funzione Differenziabile
---
>[!info] Definizione
>Sia $f:\mathbb{R}^2\to\mathbb{R}$ o $f:A\to\mathbb{R}, A\subseteq\mathbb{R}^2 \text{ Aperto}$
>Sua $(x_{0},y_{0})\in\mathbb{R}^2$, supponiamo $f$ sia derivabile
>Diciamo che $f$ è differenziabile in $(x_{0},y_{0})$ se:
>$$f(x,y)=f(x_{0},y_{0})+\displaystyle{\frac{df}{dx}}(x_{0},y_{0})(x-x_{0})+ \displaystyle{\frac{df}{dy}}(x_{0},y_{0})(y-y_{0})+ \underbrace{ \circ(|(x,y)-(x_{0},y_{0})|) }_{\displaystyle \circ( \sqrt{ (x-x_{0})^2 +(y-y_{0})^2}) }$$
>Per $(x,y)\to (x_{0},y_{0})$

- Si può scrivere anche con l'incremento:
>[!tip] Equivalente
>$$f(x_{0}+h,y_{0}+k)=f(x_{0},y_{0})+\displaystyle{\frac{df}{dx}}(x_{0},y_{0})h+ \displaystyle{\frac{df}{dy}}(x_{0},y_{0})k+ \circ(\sqrt{ h^2+k^2 })$$
>Per $(h,k)\to(0,0)$
>a
>>[!example] Differenziale
>>Chiamo differenziale di $f$ nel punto $(x_{0},y_{0})$
>>La funzione lineare
>>$$\begin{array}
\ df_{(x_{0},y_{0})}:\mathbb{R}^2\to\mathbb{R} \\
(h,k) \mapsto \displaystyle{\frac{df}{dx}}(x_{0},y_{0})h+ \displaystyle{\frac{df}{dy}}(x_{0},y_{0})k
\end{array}
$$

### Funzione Differenziabile 2 volte
>[!info] Definizione
>Diciamo che $f$ è derivabile $2$ volte in $(x_{0},y_{0})$ se $f$ è derivabile e $\partial xf$ e $\partial yf$ sono [[#Derivabilità|derivabili]]
>E le indico come:
>>[!tip] Notazione
>>$$\displaystyle\frac{ \partial^2 f }{ \partial x^2 } = \displaystyle\frac{ \partial  }{ \partial x } \left( \displaystyle\frac{ \partial f }{ \partial x }  \right) \ \ \ |\ \ \ \displaystyle\frac{ \partial^2 f }{ \partial y^2 } = \displaystyle\frac{ \partial  }{ \partial y } \left( \displaystyle\frac{ \partial f }{ \partial y }  \right) \ \ \ |\ \ \ \displaystyle\frac{ \partial^2 f }{ \partial x \partial y } = \displaystyle\frac{ \partial  }{ \partial x } \left( \displaystyle\frac{ \partial f }{ \partial y }  \right) \ \ \ |\ \ \ \displaystyle\frac{ \partial^2 f }{ \partial x \partial y } = \displaystyle\frac{ \partial  }{ \partial y } \left( \displaystyle\frac{ \partial f }{ \partial x }  \right) 
>$$

 ### Matrice Hessiana 
>[!info] Definizione
>Chiamiamo [[Elementi di Algebra Lineare e Geometria Analitica#Matrici su $ mathbb{R}$ di tipo $(m,n)$|matrice]] Hessiana di $f$ in $(x_{0},y_{0})$ la matrice:
>$$H_{f}(x_{0},y_{0})\begin{pmatrix}
\displaystyle\frac{ \partial^2 f }{ \partial x^2 }(x_{0},y_{0})  & \displaystyle\frac{ \partial^2 f }{ \partial x \partial y }(x_{0},y_{0}) \\
\displaystyle\frac{ \partial^2 f }{ \partial y^2 }(x_{0},y_{0})  & \displaystyle\frac{ \partial^2 f }{ \partial y \partial x }(x_{0},y_{0})
\end{pmatrix}
>$$

### Teorema di Schwartz
>[!info] Teorema
>Sia $A\subseteq\mathbb{R}^2$, $f:A\to\mathbb{R}$, $f\in C^2(A,\mathbb{R})$
><u>Allora</u>
>$$\displaystyle\frac{ \partial^2 f }{ \partial x \partial y }(x,y) =
\displaystyle\frac{ \partial^2 f }{ \partial y^2 }(x,y)$$
## Relazione funzione Differenziabile e Continua
---
>[!info] Teorema
>Se $f$ è differenziabile in $(x_{0},y_{0})$
><u>Allora</u>
>$f$ è continua in $(x_{0},y_{0})$

### Dimostrazione
Passo al limite nella definizione di differenziabilità
>$$f(x,y)=f(x_{0},y_{0})+\displaystyle{\frac{df}{dx}}(x_{0},y_{0})(x-x_{0})+ \displaystyle{\frac{df}{dy}}(x_{0},y_{0})(y-y_{0})+ \underbrace{ \circ(|(x,y)-(x_{0},y_{0})|) }_{\displaystyle \circ( \sqrt{ (x-x_{0})^2 +(y-y_{0})^2}) }$$
>Per $(x,y)\to (x_{0},y_{0})$

$$
\lim\limits_{(h,k)\to (0,0)}f(x_{0}+h,y_{0}+k)=f(x_{0},y_{9})
$$
#### Esercizi Esempio
Determinare l'equazione del piano tangente al grafico di $f$ nel punto $(P_{0},f(P_{0}))$
- $f(x,y)=x^3-2x^2y-5xy^2+y^3$
	- $f(x_{0},y_{0})=f(0,1) = 1$
	- $\displaystyle\frac{ \partial f }{ \partial x }(x,y)=3x^2-4xy-5y^2\to \displaystyle\frac{ \partial f }{ \partial x }(0,1)=-5$
	- $\displaystyle\frac{ \partial f }{ \partial y }(x,y)=-2x^2-10xy+3y^2\to \displaystyle\frac{ \partial f }{ \partial y }(0,1)=3$

$$
z=1-5x+3(y-1) = -5x+3y-2
$$
Determinare il differenziale di $f$ all'origine
- $f(x,y)=x^2+x(y-1)+2y$
	- $\displaystyle\frac{ \partial f }{ \partial x }(x,y)=2x+y-1 \to \displaystyle\frac{ \partial f }{ \partial x }(0,0)=-1$
	- $\displaystyle\frac{ \partial f }{ \partial y }(x,y)=x+2\to \displaystyle\frac{ \partial f }{ \partial y }(0,0)=2$

$$
df_{(0,0)}(h,k)=-h+2k
$$
>[!info] Teorema
>Sia $f:\mathbb{R}^2\to\mathbb{R}$, Sia $(x_{0},y_{0})\in\mathbb{R}^2$
>Se $f\in C^1(\mathbb{R}^2,\mathbb{R})=\left\{  f:\mathbb{R}^2\to\mathbb{R} \text{ derivabili, con } \displaystyle\frac{ \partial f }{ \partial x } ,\displaystyle\frac{ \partial f }{ \partial y }\text{ continue }\right\}$
><u>Allora</u>
>$f$ è differenziabile

### Riassumendo
$$f\in C^1 \implies f \text{ differenziabile } \implies f \text{ continua}$$
- Ma:
$$
f \text{ derivabile} \cancel{ \implies } f \text{ continua}
$$
## Derivata Direzionale
---
>[!info] Definizione
>Sia $(x_{0},y_{0})\in\mathbb{R}^2, \underbrace{ V }_{ Versore }=1(cos(\theta),sin(\theta)), \theta \in[o,2\pi]$
>Data $f:\mathbb{R}^2\to\mathbb{R}$
>
>>[!done] A Parole
>>Voglio vedere come varia $f$ lungo la direzione $V$
>
>Considero il rapporto incrementale di $f$
>$$\displaystyle{\frac{f(x_{0}+tcos(\theta),y_{0}+tsin(\theta))-f(x_{0},y_{0})}{t}}$$
>a
>>[!done] In Breve
>>Se esiste il limite per $t\to0$ del rapporto incrementale ed è in $\mathbb{R}$ dico che $f$ è derivabile lungo la direzione $V$ nel punto $(x_{0},y_{0})$
>$$\lim\limits_{h\to 0}\displaystyle{\frac{f(x_{0}+tcos(\theta),y_{0}+tsin(\theta))-f(x_{0},y_{0})}{t}} = 0$$

- Indichiamo la derivata direzionale di $f$ lungo $V$ con:
$$
D_{V}f\text{ oppure }\delta_{V}f
$$

## Teorema del Gradiente
--- 
>[!info] Teorema
>Sia $f:A\to\mathbb{R}$, $A\subseteq\mathbb{R}^2$ Aperto, sia $(x_{0},y_{0})\in A$
>Sia $V=(cos(\theta),sin(\theta))$
>Se $f$ è differenziabile in $(x_{0},y_{0})$
><u>Allora</u>
>$$D_{v}f(x_{0},y_{0})= \nabla f(x_{0},y_{0})\cdot V$$

### Dimostrazione
Considero la definizione di derivata direzionale:
$$
\displaystyle{\frac{f(x_{0}+\overbrace{tcos(\theta)}^{h},y_{0}+\overbrace{tsin(\theta)}^{k})-f(x_{0},y_{0})}{t}}
$$
- Uso la definizione di differenziabilità:
$$
\displaystyle{\frac{\cancel{ f(x_{0},y_{0}) }+\partial xf(x_{0}+tcos(\theta),y_{0})\cancel{ t }cos(\theta)+\partial yf(x_{0},y_{0}+tsin(\theta))\cancel{ t }sin(\theta)-\cancel{ f(x_{0},y_{0}) }+\circ(t)}{\cancel{ t }}}
$$
- Passo al limite per $t\to0$
$$D_{v}f(x_{0},y_{0})=\partial xf(x_{0},y_{0})cos(\theta)+\partial yf(x_{0},y_{0})sin(\theta) = \nabla f(x_{0},y_{0})\cdot V$$
#### Osservazione
Da tale formula si osserva che $D_{v}f(x_{0},y_{0})$ è massima quando $V=D_{v}f(x_{0},y_{0})$
>[!done] In Breve
>$\nabla f(x_{0},y_{0})$ indica la direzione di massima crescita

#### Osservazione
Se guardo la variazione di $f$ lungo un vettore $V$ tangente ad una [[Funzioni di due Variabili Reali#Curva di Livello|linea di livello]] "vedo" una $f$ costante e dunque:
$$
D_{v}f(x_{0},y_{0}) = 0 = \nabla f(x_{0},y_{0})\cdot V \Leftrightarrow \nabla f(x_{0},y_{0}) \perp V
 $$
