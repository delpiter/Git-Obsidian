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