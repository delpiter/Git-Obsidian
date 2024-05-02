## Forma Bilineare
---
>[!info] Definizione
>Sia $\mathbb{K}$ un [[Campi e Spazi Vettoriali#Campo|campo]] e $V$ uno [[Campi e Spazi Vettoriali#Spazio Vettoriale|spazio vettoriale]] si $\mathbb{K}$
>Una ***forma bilineare*** su $V$ è un'applicazione $\beta$:
>$$\begin{array}\ V\times V \to \mathbb{K} \\ (v,u)\mapsto \beta(v,u) \end{array}$$
>Che è [[Applicazioni Lineari#Applicazione Lineare|lineare]] in ciascuno degli argomenti
>>[!done] In Breve
>>$\forall v,v',u,u'\in V, \forall a\in\mathbb{K}$
>>1. $\beta(v+v',u)=\beta(v,u)+\beta(v',u)$
>>2. $\beta(v,u+u')=\beta(v,u)+\beta(v,u')$
>>3. $\beta(av,u)=a\beta(v,u)=\beta(v,au)$

#### Eesempio
>$V=\mathbb{R}^2,\mathbb{K}=\mathbb{R}, v=(x_{1},x_{2}), u=(y_{1},y_{2})$

$$
\beta(v,u)=2x_{1}y_{1}+x_{1}y_{2}+3x_{2}y_{1}-x_{2}y_{2}
$$
>[!quesiton] $\beta$ è lineare?

>*Sia $v'=(x_{1}',x_{2}')$*

>[!abstract] Somma

$$
\begin{array}
\ \beta(v+v',u)=\beta((x_{1}+x_{1}',x_{2}+x_{2}'),(y_{1},y_{2}))= \\
=2(x_{1}+x_{1}')y_{1}+(x_{1}+x_{1}')y_{2}+2(x_{2}+x_{2}')y_{1}(x_{2}+x_{2}')y_{2} = \\
\beta(v,u)+\beta(v',u)
\end{array}
$$
- Analogo per il ***secondo vettore***

>[!abstract] Prodotto

$$
\begin{array}
\ \beta(av,u)=\beta((ax_{1},ax_{2}),(y_{1},y_{2}))= \\
=2ax_{1}y_{1}+ax_{1}y_{2}+3ax_{2}y_{1}-ax_{2}y_{2}= \\
=a(2x_{1}y_{1}+x_{1}y_{2}+3x_{2}y_{1}-x_{2}y_{2}) = a\beta(v,u)
\end{array}
$$
- Analogamente si mostra $\beta(v,au)$

>[!done] $\beta$ è *bilineare*


#### Esempio
>*Sia $V=\mathbb{R}^2$,  $\mathbb{K}=\mathbb{R}$,  $v=(x_{1},x_{2})$,  $u=(y_{1},y_{2})$*

$$
\beta(v,u)=x_{1}x_{2}+y_{1}y_{2}
$$
>[!abstract] Prodotto

$$
\begin{array}
\ \beta(av,u)=(ax_{1})(ax_{2})+y_{1}y_{2}=a^2x_{1}x_{2}+y_{1}y_{2}\neq \\
\neq ax_{1}x_{2}+ay_{1}y_{2}=a\beta(v,u)
\end{array}
$$

>[!fail] $\beta$ non è bilineare

## Tipi di Forme Bilineari
---
>[!info] Simmetrica
>Una [[#Forma Bilineare]] $\beta$ su $V$ è ***simmetrica*** se:
>$$\beta(v,u)=\beta(u,v)$$
>$\forall v,u\in V$

>[!info] Antisimmetrica
>Una [[#Forma Bilineare]] $\beta$ su $V$ è ***antisimmetrica*** se:
>$$\beta(v,u)=-\beta(u,v)$$
>$\forall v,u\in V$

#### Esempi
>*Sia $V=\mathbb{R}^2$, $v=(x_{1},x_{2})$, $u=(y_{1},y_{2})$*

>[!summary] 1. $\beta_{1}(v,u)=2x_{1}y_{1}-3x_{1}y_{2}-3x_{2}y_{1}+4x_{2}y_{2}$

- $\beta_{1}(u,v)=2x_{1}y_{1}-3x_{2}y_{1}-3x_{1}y_{2}+4x_{2}y_{2}$

>[!caution] Simmetrica

>[!summary] 2. $\beta_{2}(v,u)=x_{1}y_{2}-x_{2}y_{1}$

- $\beta_{2}(u,v)=y_{1}x_{2}-y_{2}x_{1}=-\beta_{2}(v,u)$

>[!attention] Antisimmetrica

>[!summary] 3. $\beta(v,u)=2x_{1}y_{2}-3x_{2}y_{1}$

- $\beta((1,0),(1,1))=2$
- $\beta((1,1),(1,0))=-3$

>[!fail] Ne *simmetrica* ne *antisimmetrica*

>[!summary] 4. Può esistere una forma sia simmetrica che antisimmetrica?

- $\beta(v,u)\underset{ S }{ = } \beta(u,v)\underset{ A }{ = }-\beta(v,u)$
$$
\beta(v,u)=0 ,\ \ \ \ \ \ \forall v,u \in V
$$
>[!done] Esiste ma è unicamente $\beta=0$


