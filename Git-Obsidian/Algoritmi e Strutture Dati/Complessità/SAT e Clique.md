## Prove di $NP$ Completezza
---
>[!attention] Tentativo Facile
>Mostrare che una *funzione* $f$ è in $NP$, quindi mostrare che $g\leq_{p}f$ per ***qualche problema*** $g$ che è già noto essere $NP$-***Completo***

### Circuit-SAT

>[!info] Problema
>Trovare un assegnamento alle variabili di ingresso, che rende vera l'uscita
>>[!done] Intuitivamente
>>È più o meno come dire che è possibile rappresentare il problema con un circuito elettrico binario

#### Esempi di Prove
>*Dati un grafo $G$ e un intero $n$ stabilire se esiste un sottografo completo di $G$ di $n$ vertici*

>[!caution] Prova di $NP$-*Completezza*

Si parte da ***SAT***  e si assume di sapere già che ***SAT*** è $NP$-***Completo***
##### Clique
>[!info] Problema
>Dato un grafo $G=(V,E)$, un sottoinsieme $S$ dei suoi vertici forma una ***clique*** se ogni coppia di vertici $S$ è connessa

###### 3-SAT $\leq_{p}$ Clique
>[!abstract] Parametri
>Formula $\phi=C_{1}\wedge C_{2}\wedge\dots\wedge C_{k}$, $k$ clausole
>***3 Disgiunti*** per ogni clausola: $(x_{1}\vee x_{2}\vee ¬x_{3})\wedge\dots$
>*Grafo*:
>- Un ***vertice per ogni letterale*** di ogni clausola
>- Un arco fra due vertici se corrispondenti a:
>	- Letterali di ***clausole diverse***
>	- Variabili ***Compatibili***

![[3sat-Clique.png]]
>[!Teorema]
>$\phi$ è soddisfacibile $\iff G$ ha una clique di $k$ vertici
>>[!abstract] Dimostrazione
>>>$\implies$
>>Se $\phi$ è soddisfacibile, allora $\forall C_{r},\exists \mathcal{l}_{i}^r$, un letterale che vale $1$
>>Il letterale $\mathcal{l}_{i}^r$ corrisponde a un vertice $v_{i}^r$
>><u>Allora</u>
>>$V'=\{ v_{i}^r \}$ è una clique
>>- Per $r\neq s$, $\mathcal{l}_{i}^r$ è compatibile con $\mathcal{l}_{i}^s$
>>>$\impliedby$
>>
>>Nessun arco in $G$ connette vertici di una tripla $V'$ ha un vertice per tripla, $v_i^r$
>>Si può porre $\mathcal{l}_{i}^r=1$


#### Riduzione Clique $\leq_{p}$ Vertex Cover
>[!info] Problema
>Dato un grafo $G$, se $G'$ è il grafo complementare di $G$, allora ogni coppia di nodi è connessa in $G'\iff$ non è connessa in $G$
>- $G'=(V,E')$ è complemento di $G=(V,E)\iff(u,v)\in E'\iff(u,v)\notin E$

