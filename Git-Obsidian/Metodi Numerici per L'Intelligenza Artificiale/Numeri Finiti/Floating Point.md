## Sistema Posizionale a Virgola Mobile Normalizzata
---
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

### Numeri Finiti: Floating Point
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

#### Underflow e Overflow
>Se $p\notin [L,U]$, il numero ***non può essere rappresentato*** nel calcolatore.

Ci sono due casi:

>[!abstract] Underflow
>Se $p<L$ si verifica un ***underflow*** e solitamente si assume lo *zero* come valore approssimato
>>[!warning] Segnalato Mediante Warning

>[!hint] Overflow
>Se $p>U$ si verifica un ***overflow***.
>Non si approssima.
>>[!fail] Si segnala l'evento con un arresto del calcolo

#### Troncamento e Arrotondamento
>Nel caso in cui $p\in[L,U]$, cioè $\alpha$ è rappresentabile nel calcolatore, si possono verificare due casi:

>[!done] Numero Rappresentabile
>Le cifre $a_{i}$, per $i>t$ sono ***tutte nulle***, cioè $\alpha$ è rappresentabile esattamente con un numero finito di $t$ cifre.

>[!caution] Numero Non Rappresentabile
>Le cifre $a_{i}$, per $i>t$ non sono ***tutte nulle***.

>In questo caso la rappresentazione di $\alpha$ sul calcolatore è data da:

$$
fl(\alpha)=\begin{cases}
0 \qquad\quad \ \text{ se } \alpha=0 \\
\pm m_{t}\beta^p \quad \text{se } \alpha\neq0
\end{cases}
$$
Dove:
- $m_{t}=a_{1}\beta^{-1}+a_{2}\beta^{-2}+\dots+\tilde{a}_{t}\beta^{-t}$

>[!info] Troncamento
>Nel caso di ***troncamento***:
>$$\tilde{a}_{t}=a_{t}$$

>[!hint] Arrotondamento
>Nel caso di ***arrotondamento*** (se $\beta$ è *pari*):
>$$\tilde{a}_{t}=\begin{cases}a_{t} \quad \text{se } a_{t+1}< \frac{\beta}{2} \\a_{t}+1 \quad \text{se } a_{t+1}\geq \frac{\beta}{2}\end{cases}$$

##### Arrotondamento ai Pari
>Speciale regola dell'approssimazione per arrotondamento.

Si applica quando un numero reale $\alpha$ è ***esattamente equidistante*** tra due numeri finiti *consecutivi*
- Quando la sua $t+1$ cifra è uguale a $\frac{\beta}{2}$ e le successive cifre sono ***nulle***

>[!example] Rounding to Even
>Il ***rounding to even*** impone di prendere com $fl(\alpha)$ il numero dell'insieme $F$ che ha l'**ultima cifra di mantissa pari**.

- Se la cifra finale $a_{t}$ è **pari**, non si incrementa
- Se la cifra finale $a_{t}$ è **dispari**, si incrementa di $1$

>[!done] Pro
>Riduce la distorsione di arrotondamento.

### Numeri più Piccoli e Grandi Rappresentabili
>Considerando $F(\beta,t,L,U)$

>[!]