>[!info] Concetto Importante
>$$\int e^{ -at } \, dt =\frac{e^{ -at }}{-a}$$

## Variabile Esponenziale Continua
---
>[!def] Definizione
>Consideriamo $a>0$

$$f(s)=\begin{cases}
ae^{ -as }\quad \ \text{se } s>0 \\
0\qquad\quad\text{se } s<0
\end{cases}$$

![[Densita Esponenziale.png]]

>Verifichiamo la Correttezza

$$
\int_{-\infty}^\infty f(s) \, ds=\int_{0}^\infty ae^{ -as } \, ds=[-e^{ -as }]_{0}^\infty=0-(-1)=1  
$$

>[!question] $F_{X}(t)$ ?

>Consideriamo $t>0$

$$
F_{X}(t)=\int_{0}^t f(s)\, ds=[-e^{ -as }]_{0}^t =-e^{ -at }+1 = 1-e^{ -at }
$$

![[F di Ripartizione Esponenziale.png]]

### Mancanza di Memoria
>Ricordiamo la [[3 - Variabili Aleatorie#Mancanza di Memoria|mancanza di memoria]] fatta in precedenza

>[!info] Controlliamo se vale
>$$\mathcal{P}(X\geq t+m|X\geq m)=\mathcal{P}(X\geq t)$$

##### Dimostrazione
$$
\mathcal{P}(X\geq t)=1-F_{X}(t)=1-(1-e^{ -at })
$$

$$
\displaystyle{\frac{\mathcal{P}(X\geq t+m)}{\mathcal{P}(X\geq m)}}=\displaystyle{\frac{e^{ -a(t+m) }}{e^{ -am }}}=e^{ -at }
$$

#### Utilizzo
>[!info] Se $X$ ha densità ***esponenziale***
>Allora possiamo scrivere:
>$$X\sim Exp(a)$$

>[!question] Quando si usa?

Tipicamente viene usata per ***tempi di attesa*** che per la loro natura hanno *mancanza di memoria*

### Valore Atteso

>[!abstract] Formula
>$$E[X]=\int_{-\infty}^\infty sf_{X}(s) \, ds =\int_{0}^\infty sae^{ -as } \, ds$$

>Utilizziamo l'[[Calcolo Integrale#Integrazione per Parti|Integrazione per Parti]]

- $s=f\quad ae^{ -as }=g'$
	- $g=-e^{ -as }$

$$
=\underbrace{ [-se^{ -as }]_{0}^\infty-\int _{0}^\infty }_{ 0 } -e^{ -as }\, ds = \int _{0}^\infty e^{ -as }\, ds = \frac{1}{a}\underbrace{ \int _{0}^\infty ae^{ -as }\, ds }_{ 1 }=\frac{1}{a}  
$$

##### Esempio
>Supponiamo che mediamente passa una ***porche*** ogni 4 ore

>[!question] Qual è la probabilità che passi una porche entro 3 ore?

- $X\sim Exp\left( \frac{1}{4} \right)$

$$
\mathcal{P}(X\leq 3) = F_{X}(3)=1-e^{ -3/4 }=0.527
$$

### Varianza 
>[!abstract] Formula
> $$Var(X)=E[X^2]-E[X]^2$$

$$
E[X^2]=\int_{0}^\infty s^2ae^{ -as } \, ds
$$
>Utilizziamo l'[[Calcolo Integrale#Integrazione per Parti|Integrazione per Parti]]

- $s=f\quad ae^{ -as }=g'$
	- $g=-e^{ -as }$

$$
=\underbrace{ [-s^2e^{ -as }]_{0}^\infty }_{ 0 }-\int _{0}^\infty-2se^{ -as } \, ds=\frac{2}{a}\underbrace{ \int _{0^\infty} ase^{ -as }\, ds }_{ 1/a } =\frac{2}{a}\cdot \frac{1}{a}
$$

>Quindi, per concludere:

$$
Var(X)=E[X^2]-E[X]^2=\frac{2}{a^2}-\frac{1}{a^2} = \frac{1}{a^2}
$$
