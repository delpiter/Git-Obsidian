## Partizioni di un Insieme
---
>[!Definizione]
>Una ***partizione*** di un insieme $A$ è una *suddivisione* di $A$ in sottoinsiemi $A_{1},A_{2},\dots$ detti ***blocchi*** della partizione
>I blocchi devono rispettare le seguenti condizioni:
>- $A_{i} \neq \varnothing \quad \forall i$
>- $A_{i}\ \cap A_{j} = \varnothing \quad \forall i\neq j$
>- $A_{1}\cup A_{2} \cup\dots = A$

![[Pasted image 20241002184937.png]]
>[!warning] L'ordine dei blocchi non è rilevante

#### Esempio

$A:\{ 1,2 \}$
- $A_{1}:\{1  \}\quad A_{2}:\{ 2 \}\implies$ Partizione a 2 ***blocchi***
- $A_{1}:\{ 1,2 \}\implies$ Partizione a 1 ***blocco***


$A:\{ 1,2,3 \}$
- 3 ***blocchi*** da 1: $\{ 1 \},\quad\{ 2 \},\quad\{ 3 \}$
- 1 ***blocco*** da 3: $\{ 1,2,3 \}$
- 3 ***partizioni*** da:
	- 1 ***Blocco*** da 2
		- $\{ 1,2 \},$
	- 1 ***Blocco*** da 1
		- $\{ 3 \}$

>[!done] Per un totale di 5 partizioni

### Generalizzazione
>[!summary] Definizione
>$\forall n \geq 0$ Poniamo:
>$B_{n}= \#$ di partizioni di $\{ 1,\dots,n \}$ se $n>0$
>- $B_{0}=1$
>>[!info] Questi numeri si dicono numeri di ***Bell***

- $B_{0}=1,\quad B_{1}=1,\quad B_{2}=2,\quad B_{3}=5$


>[!Proprietà]
>$\forall n>0 \quad B_{n}=\displaystyle\sum_{h=0}^n-1 \binom{n-1}{h}\cdot B_{h}$

