## Scheduling
---
>Per rappresentare uno [[I Processi#Schedule|schedule]] si utilizzano i diagrammi di Gantt

![[GanttDiagram.png]]
- Ogni *linea* rappresenta una *risorsa diversa*, in questo caso sarebbe un **processore con due core**

### Politiche di Scheduling
> Esistono due tipi di scheduler che si basano sugli eventi che possono causare un [[I Processi#Mode Switching e Context Switching|Context Switch]]

>[!info] Cambio di Stato del Processo
>1.  Da **Running** a *Waiting*
>2. Da **Running** a *Ready*
>3. Da **Waiting** a *Ready*
 
>[!caution] Terminazione del Processo
>4. Quando il processo stesso **Termina** la propria esecuzione

#### Scheduler Non-Preemptive
>[!abstract] Definizione
>Uno scheduler ***Non-Preemptive*** è uno scheduler in cui il *context switch* avviene solamente nel caso in cui il processo **termina** o si mette in **attesa** di una *risorsa*
>- Va avanti finché non è forzato a fermarsi
>
>>[!done] Pro
>>Non richiede alcuni meccanismi hardware come timer programmabili
>>- Sono ***più semplici*** da progettare


#### Scheduler Preemptive
>[!hint] Definizione
>Uno scheduler ***Preemptive*** è uno scheduler in cui il *context switch* può avvenire in **qualsiasi condizione**
>- ***Terminazione*** del Processo
>- Il processo si mette in ***attesa*** di una risorsa
>- Il suo ***quanto di tempo*** termina
>- $\dots$
>
>>[!done] Pro
>>Permette di *utilizzare al meglio* le *risorse* del calcolatore

### Criteri di Scelta di uno Scheduler
> Ci sono delle *metriche fondamentali* per capire la bontà di una **tecnica di scheduling**

##### Criteri da Massimizzare

>[!info] Utilizzo della risorsa

>La *percentuale di tempo* in cui la `CPU` è occupata ad eseguire dei processi

>[!abstract] Throughput

>Numero di *processi completati* per unità di tempo
> - Dipende dalla *lunghezza* dei processi

##### Criteri da Minimizzare

>[!caution] Tempo di Turnaround

>Tempo che trascorre dalla **creazione** di un processo alla sua **terminazione**

>[!example] Tempo di Attesa

> Tempo **trascorso** da un processo nella coda **Ready**

>[!note] Tempo di Risposta

>Tempo che intercorre fra *sottomissione* di un processo e il tempo di *prima risposta*

## Algoritmi di Scheduling
---
>Esistono una larga gamma di *algoritmi di scheduling*, di seguito alcuni:

### First Come First Served
>[!info] ***FCFS***
>È un algoritmo che esegue per *primo* il processo che *arriva per primo*
>- Algoritmo di tipo ***Non-Preemptive***

L'implementazione è semplice, basta una *coda* con politica `FIFO`

>[!danger] Problemi

Questo algoritmo provoca elevati *tempi medi di attesa* e *turnaround*
- Processi `CPU` *bound* ritardano i process i`I/O` *bound*
>[!caution] Convoy Effect
>Il *convoy effect* avviene quando una serie di processi `I/O` *bound* sono in coda dietro al processo `CPU` *bound*
>- Mentre i processi `I/O` *bound* sono in attesa della disponibilità della risorsa che il processo `CPU` *bound* sta occupando, la **ready queue** ***rimane vuota***

### Shortest Job First

>[!info] SJF
>Lo *Shortest Job First* (più precisamente Shortest next `CPU` *burst* First) è un algoritmo che assegna alla `CPU` il processo **ready** che ha la minima durata del `CPU` *burst* successivo

L'algoritmo è **ottimale** rispetto al *tempo di attesa*
- Tuttavia à **impossibile** da implementare nella pratica
- È solo possibile fornire delle *approssimazioni* tramite ***tecniche euristiche***

##### Calcolo Approssimato
>Il calcolo della durata del prossimo `CPU` *burst* è basato sul concetto di media esponenziale dei `CPU` *burst* precedenti

>[!abstract] Concetto
>Sia $t_{n}$ il tempo dell'$n$-esimo `CPU` *burst* e $T_{n}$ la corrispondente previsione
>Sia $\alpha$ il peso che voglio dare alle operazioni:
>>[!question] Devo dare più peso alla *previsione* o al *tempo effettivo*?

Dati questi dati si può calcolare una sorta di **media pesata** fra il valore di tempo del *burst* previsto e la durata effettiva
- $T_{n+1}$ si può approssimare come seque:

$$
T_{n+1}=\alpha t_{n}+(1-\alpha)T_{n}
$$

Andando a sostituire ad ogni passo il valore di $t_{n}$ precedente:
$$
T_{n+1}=\sum_{j=0}^n \alpha(1-\alpha)^j\cdot t_{n-j} +(1-\alpha)^{n+1} T_{0}
$$

##### Tipologia dell'Algoritmo
> L'algoritmo ***SJF*** può essere sia **Preemptive** che **Non-Preemptive**

>[!note] Non Preemptive
>Una volta il processo più "*corto*" è in esecuzione, esso continua fino alla sua **terminazione**.

>[!tldr] Preemptive
>Il processo in esecuzione può essere inserito nella coda **ready**, se durante la sua esecuzione è entrato un processo con un `CPU` *burst* più *breve* di quanto rimane da eseguire al processo corrente
>- ***Shortest Remaining Time First***

