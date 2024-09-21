## Definizioni di Base
---

>[!Def] Prodotto Cartesiano
>Siano $A,B$ insiemi
>$$A\times B=\{ (a,b):a\in A, b\in B \}$$

>Nel caso $A=B$ scriveremo semplicemente $A^2$ al posto di $A\times A$
#### Esempio
>$A=\{ 1,2 \}\quad B=\{ a,3 \}$

$$
A\times B=\{ (1,a),(2,a),(1,3),(2,3) \}
$$
Il *prodotto cartesiano* si può generalizzare al caso di $n$ insiemi
>[!tip] Definizione
>Siano $A_{1},A_{2},\dots,A_{n}$ $n$ insiemi
><u>Allora</u>
>Il loro prodotto cartesiano è dato da:
>$$A_{1}\times\dots A_{n}:=\{ (a_{1},\dots,a_{n}):a_{i}\in A_{i}, \forall i=1,\dots,n \}$$

### Sequenza 
>[!Definizione]
> Ripetendo gli insiemi $A$: $\underbrace{ A\times A\times \dots\times A }_{ n \text{ volte} }$
> Scriveremo anche in questo caso $A^n$
>>[!tip] Sequenza
>>Una ***Sequenza*** finita di lunghezza $n$ di elementi di $A$ è un elemento $(a_{1},a_{2},\dots,a_{n})$ del prodotto cartesiano $A^n$
>
>Gli elementi del prodotto cartesiano $A^n$ si dicono ***sequenze*** in $A$ di ***lunghezza*** $n$

#### Esempio
> $A=\{ 1,3 \}$

- $(1,3,1,1,3)$ sequenza in $A$ di lunghezza $5$
- $(1,1)$ sequenza in $A$ di lunghezza $2$

### Insieme delle Parti
>[!Definizione]
>Sia $A$ un insieme
>Definiamo come ***insieme delle parti*** l'insieme:
>$$\mathcal{P}(A)=\{ B:B\subseteq A \}$$
>È l'insieme i cui elementi sono i sottoinsiemi di $A$, inclusi $\varnothing$ e $A$ stesso

#### Esempio
>Se $A=\{ 1,a,\pi \}$ abbiamo:

$$
\mathcal{P}(A)=\{ \varnothing,\{ 1 \},\{ a \},\{ \pi \},\{  1,a\},\{ 1,\pi \},\{ a,\pi \}, A \}
$$
>[!caution] Osservazione
>Le ***potenze cartesiane*** e ***l'insieme delle parti*** sono correlati

$$
\begin{array}
\ \varnothing \mapsto(0,0,0) \\
\{ 1 \}\mapsto(1,0,0) \\
\{ a \}\mapsto(0,1,0) \\
\{ \pi \}\mapsto(0,0,1) \\
\{  1,a\}\mapsto(1,1,0) \\
\{ 1,\pi \}\mapsto(1,0,1) \\
\{ a,\pi \}\mapsto(0,1,1) \\
A\mapsto(1,1,1)
\end{array}
$$
>*Generalizzando questo argomento:*

>[!info] Proposizione
>Se $A$ è un insieme di $n$ elementi ($|A|=n$)
><u>Allora</u>
>$\exists$ una corrispondenza biunivoca tra:
>$$\mathcal{P}(A) \iff \{ 0,1 \}^n$$
>>[!tip] Osservazione
>>$$|A^n|=|A|^n$$
>>In particolare se $A=\{ 0,1 \} \to |\{ 0,1 \}^n|=|\{ 0,1 \}|^n=2^n$
>>Quindi se $B$ è tale che $|B|=n$ allora $|\mathcal{P}(B)|=|\{ 0,1 \}^n|=2^n$

>[!caution] Osservazioni
>1. Se $A$ e $B$ sono in corrispondenza biunivoca $\implies |A|=|B|$
>2. Sia $f:A\to B$ si dice che $f$ è $k$ a $1$ se:
>	1. $f$ è suriettiva
>	2. $|f^-1(B)|=k$ La *controimmagine* di $B$ ha $k$ elementi
>
>Se esiste $f:A\to B \quad k\text{ a } 1$ allora $|A|=k|B|$

## Prodotto Condizionato
---
>[!Definizione]
>Diciamo che $S$ è un ***prodotto condizionato*** di tipo $(a_{1},a_{2},\dots,a_{n})$ se soddisfa queste condizioni:
>1. La prima coordinata di un elemento di $S$ si può scegliere in $a_{1}$ modi
>2. La seconda coordinata di un elemento di $S$ si può scegliere in $a_{2}$ modi
>3. $\dots$
>4. La $n$-*esima* coordinata di un elemento di $S$ si può scegliere in $a_{n}$
 modi

>Osserviamo che se $S$ è un prodotto condizionato di tipo $(m,n,r)$ allora la [[0 - Introduzione#Cardinalità|cardinalità]] di $S$: $\mid S\mid = m\cdot n\cdot r$

#### Esempio
>Consideriamo $S=\{ (a,b,c):a,b,c\in \mathbb{N},\quad a\leq 10 ,\ 0\leq b-a\leq 10,\ 0\leq c-a-b\leq 10\}$$

Posso scegliere la coordinata $a$ in $11$ modi
- da $0$ a $10$
Posso scegliere la coordinata $b$ in $11$ modi
- In base al valore di $a$: se $a=2 \implies 2\leq b\leq 12$
Posso scegliere la coordinata $c$ in $11$ modi
- In base ai valori di $a$ e $b$

>[!done] $S$ è un prodotto condizionato di tipo $(11,11,11)$
>$|S|=11^3=1331$

## Disposizioni
---
>[!Definizione]
>Sia $A$ un insieme, una ***disposizione*** in $A$ di ***lunghezza*** $n$ $(a_{1},\dots,a_{n})$ è una [[#Sequenza|sequenza]] in $A$ di ***lunghezza*** $n$ se gli elementi $a_{1},\dots,a_{n}$ sono tutti distinti tra di loro
>>[!done] In altre Parole
>>$$a_{i}\neq a_{j} \quad\forall i\neq j$$

#### Esempio
>$A=\{ 1,2,3,4,5 \}$

- $(1,5,4)\implies$ È disposizione in $A$ di lunghezza $3$
- $(1,5,1)\implies$ Non è disposizione, ma è sequenza in $A$
### Domanda
>[!question] Quante sono le disposizioni di lunghezza $n$?

>Sia $|A| = m$

$$(a_{1},a_{2},\dots,a_{n})$$
1. Posso scegliere $a_{1}$ in $m$ modi
2. Posso scegliere $a_{1}$ in $m-1$ modi
3. $\vdots$
4. Posso scegliere $a_{n}$ in $m-n+1$ modi

>[!done] Conclusione
>Le disposizioni di lunghezza $n$ in $A$ con $|A|=m$ formano un ***prodotto condizionato*** di tipo $(m,m-1,m-2,\dots,m-n+1)$
>Quindi tali disposizioni sono $m\cdot(m-1)\cdot(m-2)\cdot \dots \ \cdot (m-n+1)$
>Questo prodotto si chiama fattoriale discendente e si indica:
>$$(m)_{n}=m\cdot(m-1)\cdot(m-2)\cdot \dots \ \cdot (m-n+1)$$


#### Esempio
$(12)_{5}=12\cdot 11\cdot 10\cdot 9\cdot 8$

## Permutazioni
---
>[!Definizione]
>Una ***permutazione*** è una *particolare disposizione* di lunghezza $|A|$ in $A$
>>[!tip] Le permutazioni di $A$, se $|A|=n$ sono:
>>$$(n)_{n}=n\cdot(n-1)\cdot(n-2)\cdot \dots \ \cdot 2\cdot1=n! $$

#### Esempio
- $A=\{ 1,2,3,4,5 \}$

$$
\text{ Sono due Permutazioni}
\begin{cases}
(1,4,5,3,2) \\
(5,3,1,2,4)
\end{cases}
$$

## Combinazioni
---
>[!Definizione]
>Una combinazione di lunghezza $a$ in $A$ è un sottoinsieme di $a$ elementi
>>[!question] Sia $|A|=n$, quanti sono i sottoinsiemi con $a$ elementi?
>
>>[!tip] Proposizione
>>Siano $a,b>0:a+b=n$ Allora abbiamo una corrispondenza biunivoca tra:
>>- Sottoinsiemi di $\{ 1,2,\dots,n \}$ con $a$ elementi
>>- Sequenze binarie con $a$ volte $1$ e $b$ volte $0$
>>- Sequenze binarie con $a$ volte $0$ e $b$ volte $1$
>>- Sottoinsiemi di $\{ 1,2,\dots,n \}$ con $b$ elementi
>>Questi insiemi hanno:
>>$$\displaystyle{\frac{(n)_{a}}{a!}}=\displaystyle{\frac{(n)_{b}}{b!}}=\displaystyle{\frac{n!}{a!b!}}$$

### Dimostrazione
$$
\begin{array}
\ \{ 1,2,3 \} \iff (1,1,1,0,0) \iff (0,0,0,1,1)\iff\{ 4,5 \} \\
\vdots \\
\{ 2,3,5 \}\iff(0,1,1,0,1)\iff(1,0,0,1,0)\iff\{ 1,4 \} \\
\vdots
\end{array}
$$
>[!tip] Osservazione
>Osserviamo che esiste una funzione che va dalle [[#Disposizioni]] di lunghezza $a$ ai sottoinsiemi con $a$ elementi
>- La funzione $f$ è $a! \text{ a }1$ perché ad ogni sottoinsieme con $a$ elementi *corrispondono le permutazioni* dei suoi elementi

Quindi il numero di sottoinsiemi con $a$ elementi è uguale al numero di disposizioni di lunghezza $a$ diviso $a!$
$$
\displaystyle{\frac{(n)_{a}}{a!}}
$$
>Inoltre

$$
\displaystyle{\frac{(n)_{a}}{a!}}=\displaystyle{\frac{n\cdot(n-1)\cdot\ \dots\ \cdot(n-a+1)}{a!}}=\displaystyle{\frac{n\cdot(n-1)\cdot\ \dots\ \cdot(b+1)}{a!}}\cdot \displaystyle{\frac{b(b-1)\cdot \ \dots \ \cdot1}{b(b-1)\cdot \ \dots \ \cdot1}}=\displaystyle{\frac{n!}{a!b!}}
$$

>[!caution] Coefficiente Binomiale
>Questo numero: $\displaystyle{\frac{(n)_{a}}{a!}}=\displaystyle{\frac{(n)_{b}}{b!}}=\displaystyle{\frac{n!}{a!b!}}$ si indica con: $\displaystyle\binom{n}{a}=\displaystyle\binom{n}{b}=\displaystyle\binom{n}{a\ b}$
>[[Definizioni_Analisi#Coefficiente Binomiale|Coefficiente Binomiale]]

### Tipi di Combinazione
>[!Definizioni]
>>[!tip] $(a,b)$
>>Una combinazione di tipo $(a,b)$ in $A$, con $|A|=n=a+b$ è una coppia ordinata di sottoinsiemi di $A$ $(S_{1},S_{2})$ con $|S_{1}|=a\quad|S_{2}|=b$
>>$$S_{1}\cup S_{2}=A$$
>
>>[!hint] $(a,b,c)$
>>Una combinazione di tipo $(a,b,c)$ in $A$, con $|A|=n=a+b+c$ è una terna ordinata di sottoinsiemi di $A$ $(S_{1},S_{2},S_{3})$ con $|S_{1}|=a\quad|S_{2}|=b\quad|S_{3}|=c$
>>$$S_{1}\cup S_{2}\cup S_{3}=A$$

#### Esempio
>$A=\{ 1,2,3,\dots,10 \}$

- $(\{ 1,3,6 \},\{ 2,5,8,9 \},\{ 4,7,10 \})$ è una combinazione di tipo $(3,4,3)$
