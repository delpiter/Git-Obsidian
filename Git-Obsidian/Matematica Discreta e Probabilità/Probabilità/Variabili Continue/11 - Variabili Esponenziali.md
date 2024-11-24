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
