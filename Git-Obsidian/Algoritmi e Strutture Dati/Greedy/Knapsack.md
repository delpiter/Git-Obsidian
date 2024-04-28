## Knapsack
---

>[!info] Problema
>>[!abstract] Knapsack 0-1
>>Un ladro che sta rapinando un negozio vuole prendere "***carico con più valore***" caricato in uno zaino capace di trasportare un peso di $W$.
>>Il ladro può scegliere di prendere un ***qualsiasi sottoinsieme*** di $n$ oggetti nel negozio.
>>- L'oggetto $i$-esimo vale $v_{i}$ e pesa $w_{i}$, dove $v_{i}$ e $w_{i}$ sono interi
>>
>>>[!caution] 0-1 poiché il ladro può o prendere o lasciare l'oggetto, non può prenderne una parte frazionaria
>
>>[!tldr] Fractional Knapsack
>>La situazione è la stessa del *Knapsack 0-1*, ma il ladro è in grado di prendere una parte frazionaria degli oggetti
>>>[!caution] Knapsack è una generalizzazione di *Knapsack 0-1*

>[!question] Quali oggetti deve rubare per massimizzare il guadagno?

### Sottostruttura del Problema
>*Entrambi i problemi soddisfano la proprietà di [[Definizioni_Algoritmi#Sottostruttura Ottimale|sottostruttura ottima]]*

Supponiamo che il ladro *possa rubare* un peso totale di $W'$ non maggiore di $W$ e di valore massimo $V$
Se togliamo dallo zaino l'oggetto $j$ otteniamo la ***soluzione ottima*** del sotto problema in cui lo zaino può ***contenere al massimo*** $W-w_{j}$ ottenuti mettendo insieme oggetti da un insieme di $n-1$
- È stato tolto l'oggetto $j$-esimo

### Soluzione Greedy
>*Il knapsack frazionario si può risolvere tramite [[Gli Algoritmi Greedy|algoritmi Greedy]]*

>[!Idea]
>Il ladro prende la *quantità più grande possibile* dell'oggetto $i$ tale per cui $v_{i}/w_{j}$ (valore per unità di peso) è ***massimo***
>Se c'è *ancora posto* nello zaino, ***ripeti l'operazione***

![[knapsack Example.png]]

>[!done] Soluzione

![[knapsack Solution.png]]

>[!fail] Il knapsack 0-1 non è risolvibile tramite un *algoritmo greedy*

