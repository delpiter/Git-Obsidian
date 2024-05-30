## Forme per Descrivere un Sottospazio Vettoriale
---

>[!info] Tipologie
>Sia $V$ uno spazio vettoriale di dimensione $n$ e $U$ un sottospazio vettoriale di dimensione $d,(0\leq d\leq n)$
>>[!example] Forma Parametrica
>>$U$ è descritto in funzione di $d$ parametri
>
>>[!example] Forma cartesiana
>>$U$ è individuato da $n-d$ equazioni cartesiane su $V$

#### Esempio
>$V=\mathbb{R}^5, v_{1}=(1,2,0,0,1),v_{2}=(0,0,1,0,-1)$

Forma Parametrica
- $U= <v_{1},v_{2}> =\{ tv_{1}+sv_{2}, ts \in\mathbb{R} \}= \{ (t,2t,s,0,t-s), t,s\in \mathbb{R} \}$
- $U$ è descritta al variare di 2 parametri $t,s$

Forma Cartesiana
- $U=\{ (x_{1},x_{2},x_{3},x_{4},x_{5})\in \mathbb{R}^5:x_{2}=2x_{1},x_{4}=0,x_{5}=x_{1}-x_{3} \}$
- $U$ è individuato da $3=5-2$ equazioni cartesiane

>[!info] Dimensione di $U = 2$ perchè $v_{1}v,v_{2}$  è una sua base

#### Esercizio
>[!tip] Sia $V=\mathbb{R}^3$ calcolare $U \cap W$

$U = <(1,1,0),(0,0,1)> =\{ t(1,1,0)+s(0,0,1) \}=\{ (t,t,s), t,s \in\mathbb{R} \}$
$W= <(1,0,0),(0,1,-1)> =\{ a(1,0,0)+b(0,1,-1) \}=\{ (a,b,-b), a,b\in\mathbb{R} \}$

Per calcolare l'intersezione, li metto in forma cartesiana

$U=\{ (x,y,z)\in\mathbb{R}^3 :x=y\}, W=\{ (x,y,z)\in\mathbb{R}^3:y=-z \}$
$$
U \cap W=\left\{ (x,y,z)\in\mathbb{R}^3 :
\begin{cases}
x=y \\
y=-z
\end{cases} \right \} = \{ (t,t,-t),t\in\mathbb{R} \}
$$

>[!question] Chi è una base di $U\cap W$?

Una base di $U \cap W$ è un qualsiasi vettore della tipologia $\{ t(1,1,-1), t\in\mathbb{R} \}$
- Quindi per esempio una base per il sottospazio $U \cap W$ è data dal vettore $(1,1,-1)$
