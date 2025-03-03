## Numeri in un Sistema Posizionale
---
>Sistema numerico in cui il valore di una cifra *dipende dalla sua posizione*

>[!hint] Numeri reali in base $\beta$
>Un ***numero reale*** in *base* $\beta$ può essere rappresentato come:
>$$\pm(a_{n}a_{n-1}\dots a_{0}.b_{1}b_{2}\dots)_{\beta}=\pm\left(  \sum_{k=0}^n a_{k}\beta^k +\sum_{k=1}^\infty b_{k}\beta^-k \right)$$
>
>Dove:
>$a_{n}a_{n-1}\dots a_{0}$ sono le cifre della **parte intera**
>$b_{1}b_{2}\dots$ sono le cifre della **parte frazionaria**
>$\beta$ è la ***base del sistema numerico***

## Virgola Mobile e Virgola Fissa
---
>[!info] Concetti
>I sistemi di numerazione posizionale a ***virgola fissa*** e a ***virgola mobile*** sono due modalità di rappresentare i numeri reali utilizzando un *sistema numerico posizionale*, che **differiscono** nel modo in cui la ***virgola è trattata***.

### Sistema a Virgola fissa
>[!summary] Concetto
>Nel sistema a ***virgola fissa***, la *posizione* della virgola è **predefinita**, cioè la *parte frazionaria* del numero ha una **lunghezza costante** di `BIT`

>[!done] Velocità di Calcolo

Le operazioni sono ***generalmente più rapide***
- Non è necessario spostare la virgola durante le operazioni

>[!fail] Intervallo Limitato

La gamma di numeri che può essere rappresentata è ***limitata dalla posizione della virgola***

### Sistema a Virgola Mobile
>[[Numeri Floating-Point]]

>[!summary] Concetto
>Nei sistemi a ***virgola mobile*** (***floating point***) il numero di cifre dedicate alla parte intera e frazionaria *non è fisso*, ma dipende dall’**esponente**.
>- Permette di rappresentare numeri molto grandi o molto piccoli con la **stessa quantità di memoria**. 

Il numero è rappresentato come un prodotto di:
- Un ***numero significativo*** (**mantissa**)
- Un ***esponente*** che determina la *posizione della virgola*.

#### Sistema Posizionale a Virgola Mobile Normalizzata
>[!cite] Teorema
>Sia $\alpha\in\mathbb{R}\setminus\{0\}$, scelta una base $\beta$
><u> Allora </u>
>E una rappresentazione univoca di $\alpha$ in base $\beta$
>$$\alpha=\pm 0.a_{1}a_{2}a_{3}\dots \ \cdot\beta^p= \pm\left( \sum_{i=1}^\infty a_{i}\beta^{-i} \right)\cdot\beta^p=\pm m\cdot\beta^p$$
>
>Dove:
>- $p\in\mathbb{Z}$
>- Le cifre $a_{i}$ sono numeri interi tali che:
>$$0\leq a_{i}\leq \beta-1,\quad i=1,2,\dots, \quad a_{1}\neq 0$$
>
>>[!example] Mantissa
>>Il numero $m$ si chiama ***Mantissa*** e soddisfa la condizione:
>>$$\beta^{-1}\leq m<1$$
>
>>[!hint] Esponente
>>$\beta^p$ si definisce ***parte esponente*** di $\alpha$ e $p$ si chiama esponente di $\alpha$

##### Numeri Finiti: Floating Point
>Un numero reale è caratterizzato da **segno**, **esponente** e **mantissa**

In un *calcolatore* ognuna di queste parti deve essere ***limitata***

>[!def] Definizione dell'Insieme di numeri Floating Point
>Per un calcolatore che utsa:
>- Base di rappresentazione $\beta$
>- $t$ cifre per la *mantissa*
>- Esponenti *minimi* e *massimi*: $L$ e $U$ ($L<0, \quad U>0$)
>
>L'insieme ***Floating Point***è definito come l'insieme dei numeri reali rappresentabili.
>- $F(\beta,t,L,U)=$
>$$\{ 0 \}\cup \left\{ \alpha \in\mathbb{R}\setminus\{0\}:\alpha=sign(\alpha)0.a_{1}a_{2}\dots a_{t}\cdot\beta^p=sign(\alpha)\left( \sum_{i=1}^\infty a_{i}\beta^{-i} \right)\cdot\beta^p \right\}$$
>
>>[!caution] Condizioni
>>$$0\leq a_{i} \leq \beta-1, \quad i=1,2,\dots,\quad a_{1}\neq0, \quad L\leq p \leq U, \quad L<0, \quad U>0$$

L'insieme dei ***numeri macchina*** include *tutti* i numeri che possono essere rappresentati **esattamente** usando la *base* $\beta$, $t$ cifre per la *mantissa* e gli *esponenti* $L$ e $U$

###### Underflow e Overflow
>Se $p\notin$

>[!abstract] Underflow
