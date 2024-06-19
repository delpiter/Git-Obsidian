## Problemi P e NP
---
>[!abstract] Classe P
>Un [[Completezza NP#Problemi Decisionali|problema decisionale]] è nella classe $P$ se esiste un algoritmo che ***risolve*** qualsiasi istanza del problema $P$ in tempo polinomiale
>>[!done] In breve
>> $P$ è la classe dei problemi risolti in tempo polinomiale

>[!abstract] Classe NP
>Un [[Completezza NP#Problemi Decisionali|problema decisionale]] è nella classe $NP$ (*Non deterministico Polinomiale*) se esiste un algoritmo che, data una istanza $i$ e una sua possibile soluzione $s$, ***verifica la correttezza della soluzione*** $s$ in tempo polinomiale
>>[!done] In breve
>> ***Potrebbe esistere*** un algoritmo che risolve il problema in tempo polimoniale come ***potrebbe non esistere***
>> Esiste sicuramente un algoritmo di verifica di correttezza in tempo polinomiale

Più formalmente, un problema è in $NP$ se esiste un ***algoritmo non deterministico*** che lo risolve in tempo polinomiale
- In questo contesto, *non deterministico* è un algoritmo che può usare una istruzione di salto "***magica***" che trasferisce l'esecuzione sempre all'istruzione che ***minimizza il tempo di completamento del processo***

```Assembly
...
goto(L1,L2,L3) //Scelta "magica"
L1: Gestisci il primo caso
L2: Gestisci il primo caso
L3: Gestisci il primo caso
```

>[!info] Ovviamente
>$$P\subseteq NP$$
>>[!danger] Non è noto se
>>$$P=NP$$

### NP Completo
>[!info] Definizione
>$f:N\to\{ 0,1 \}$ è $NP$-***Completo*** se e solo se
>- $f\in NP$
>- $\forall g\in NP$ si ha $g\leq_{p}f$
>Cioè è possibile individuare una [[Completezza NP#Riducibilità Polinomiale|riduzione polinomiale]]

>[!Teorema]
>Se un qualunque problema in $NPC$ è risolvibile in tempo polinomiale allora
>>[!done] $$P=NP$$
>
>>[!warning] Equivalentemente
>>Se un qualunque problema in $NP$ non è risolvibile in tempo polinomiale, allora tutti i problemi in $NPC$ non sono risolvibili in tempo polinomiale