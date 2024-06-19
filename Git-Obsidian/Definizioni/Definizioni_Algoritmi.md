## Probe
---
>[!info] Definizione
>Per eseguire un **inserimento** utilizzando l'*open addressing*, si devono ***esaminare successivamente*** le celle di una tabella hash affinchè non trovi uno **slot vuoto** dove mettere la nuova chiave.
>Invece di essere inseriti in *ordine*, $0,1,\dots,m-1$, la sequenza di posizioni ***probed*** dipende dalla *chiave inserita*

## Problema di Ottimizzazione
---
>[!info] Definizione
>Un ***problema di ottimizzazione*** è un problema in cui *alcune soluzioni* sono *preferibili ad altre*
>Ogni soluzione possibile ha ***associato un valore***
>- Si vuole trovare la soluzione con il *valore ottimale* (che sia ***max*** o ***min***)

## Traveling Salesman Problem
---
>[!info] Descrizione
>>[!abstract] Input
>>Un ***grafo non diretto*** $G=(V,E)$ con pesi non negativi interi associati ad ogni arco $(u,v)$
>
>>[!caution] Output
>>L'obbiettivo è quello di trovare un ***ciclo hamiltoniano*** con la *somma dei pesi minima*
>>- Un ciclo dove si visitano ***tutti i nodi del grafo*** 

### Metodi di Soluzione
>$n$ nodi $\implies (n-1)!$ possibili *tour*

- *Enumerazione completa*
- IP: *Branch and Bound*
- *Programmazione dinamica*
- *Algoritmi approssimati*
- *Algoritmi euristici* (***Greedy***)
## Algoritmi Euristici
---
>[!info] Definizione
>Algoritmi che fanno il ***meglio che possono*** con le *risorse a disposizione*

## Sottostruttura Ottimale
---
>[!info] Definizione
>Una ***sottostruttura ottimale*** è quando una *soluzione ottimale ad un problema* contiene ***soluzioni ottimali di sottoproblemi***

## Tabular Method
---
>[!info] Definizione
>Il ***tabular method*** è uno dei metodi più basilari usati per *analizzare dei dati* sotto forma di tabella

## Conjunctive Normal Form
---
>[!info] Definizione
>Una ***CNF*** è una formula booleana del tipo:
>$$(x_{1,1} + x_{1,2} + \dots + x_{1,k_{1}})\cdot(x_{2,1} + x_{2,2} + \dots + x_{2,k_{2}})\cdot_{\dots}\cdot(x_{n,1} + x_{n,2} + \dots + x_{n,k_{n}})$$
>- $\underbrace{ (x_{1,1} + x_{1,2} + \dots + \underbrace{ x_{1,k_{1}} }_{ \text{Letterale} })U }_{ \text{Congiunto} }$

### K-CNF
>[!caution] $k$-CNF
>Una forma booleana del tipo:
>$$(x_{1,1} + x_{1,2} + \dots + x_{1},k)\cdot(x_{2,1} + x_{2,2} + \dots + x_{2},k)\cdot_{\dots}\cdot(x_{n,1} + x_{n,2} + \dots + x_{n},k)$$
>>[!done] In breve 
>>Una ***CNF*** dove in ogni congiunto ci sono lo ***stesso numero di letterali***

