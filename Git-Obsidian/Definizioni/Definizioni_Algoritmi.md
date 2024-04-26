## Probe
---
>[!info] Definizione
>Per eseguire un **inserimento** utilizzando l'*open addressing*, si devono ***esaminare successivamente*** le celle di una tabella hash affinchè non trovi uno **slot vuoto** dove mettere la nuova chiave.
>Invece di essere inseriti in *ordine*, $0,1,\dots,m-1$, la sequenza di posizioni ***probed*** dipende dalla *chiave inserita*

## Problema di Ottimizzazione
---
>[!info] Definizione
>Un *problema di ottimizzazione* è un problema in cui *alcune soluzioni* sono *preferibili ad altre*

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