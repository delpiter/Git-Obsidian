Un sistema di elaborazione è composto da un insieme di risorse da assegnare ai processi
I processi competono nell'accesso
Esempi:
- Memoria
- Processore
- Dischi
- Interfacce di rete

### Suddivisione in Classi - Guarda Libro
> Le risorse possono essere suddivise in classi

Risorse appartenenti alla stessa classe sono equivalenti
![[ResourceClassification.png]]
Esempio
La RAM è la classe delle risorse e le singole celle sono le istanze della risorsa: la ca-
pacità totale di memoria è la molteplicità della risorsa
#### Definizione
>[!info] Istanza
>Le risorse di una classe vengono dette istanze della classe

>[!note] Molteplicità
>Il numero di risorse in una classe viene detto molteplicità del tipo di risorsa

# Risorse ad ...
## Assegnazione Statica
Avviene al momento della creazione del processo e rimane valida fino al termine
- Descrittore del processo

## Assegnazione Dinamica
I processi richiedono le risorse durante la loro esecuzione e le usano una volta ottenute, le rilasciano quando non più necessarie
- Periferiche di I/O


## Tipi di Richieste
Quando un processo necessita di una risorsa generalmente non può richiedere una particolare risorsa ma solo 
una “generica” istanza di quella specifica classe: quindi una richiesta di risorse viene fatta per una classe di risorse 
e può essere soddisfatta da parte del SO assegnando al richiedente una qualsiasi istanza di quel tipo
#### Richiesta singola
È il caso normale
- Si riferisce a una singola risorsa di una classe definita
#### Richiesta multipla
- Si riferisce a una o più classi e per ogni classe ad una o più risorse

#### Bloccante
il processo richiedente si sospende se non ottiene immediatamente l'assegnazione ○ la richiesta rimane pendente e viene riconsiderata dalla funzione di gestione ad ogni rilascio
#### Non Bloccante
la mancata assegnazione viene notificata al processo richiedente, senza provocare la sospensione


### Tipi di Risorse
Risorse Seriali
- O con accesso mutualmente esclusivo
- Accetta solo richieste in "serie", uno alla volta
- Es
	- Processore 
	- Stampanti

Risorse non Seriali
Es
- File di sola lettura

### Risorse Prerilasciabili
Preemptable
- una risorsa si dice prerilasciabile se la funzione di gestione può sottrarla ad un processo prima che questo l'abbia effettivamente rilasciata

Meccanismo:
- il processo che subisce il prerilascio deve sospendersi ○ la risorsa prerilasciata sarà successivamente restituita al processo

Una risorsa è prerilasciabile
- Se il suo stato non si modifica durante l'utilizzo
- Il suo stato può essere facilmente salvato e ripristinato

Esempi:
- Processore

## Risorse Non Prerilasciabili
Def
- La funz di gestione non può sottrarre al processo le risorse che gli sono assegnate
- Sono non prerilasciabili le risorse il cui stato non può essere salvato e ripristinato

Es
- Stampanti
- Classi di Sezioni Critiche

### Deadlock
[[Condivisione di Risorse#Deadlock|Deadlock]]
Le risorse bloccate in deadlock non possono essere utilizzate da altri processi
#### Condizioni per deadlock
- Mutua Esclusione
	- Le risorse Coinvolte devono essere seriali
- Risorsa non Prerilasciabile
	- Le risorse non possono essere prerilasciate, devono essere lasciate volontariamente
- Richieste bloccanti
	- Le richieste di risorse devono essere bloccanti

### Attesa Circolare
>[!def] Definizione
>Esiste una sequenza di processi $P_{0},P_{1},\dots,P_{n}$, tali per cui $P_{0}$ attende una risorsa controllate da $P_{1}$, $P_{1}$ attende una risorsa controllata da $P_{2}$, $\dots$, $P_{n}$ attende una risorsa controllata da $P_{0}$

La presenza di queste condizione è necessario e sufficiente
- Devono valere tutte contemporaneamente affinche un deadlock si presenti nel sistema

### Grafo di Holt
sistema di rappresentazione mediante un grafo che permette di rappresentare tutte le situazioni in cui si possono venire a trovare i processi e le richieste di risorse

È un [[I Grafi|grado diretto e bipartito]]
- Gli Archi hanno una direzione
- I nodi sono suddivisi in due sottoinsiemi e non esistono archi che collegano nodi dello stesso sottoinsieme

Sottoinsiemi
- Risorse e Processi
	 - di forma rettangolare le classi di risorsa
		 - Le risorse sono come punti all'interno delle classi (l'istanza è il punto)
	 - di forma rotonda i processi

gli archi risorsa -> processo indicano che la risorsa è assegnata al processo
gli archi processo → risorsa indicano che il processo ha richiesto la risorsa

![[Pasted image 20250109114134.png]]

Non si rappresentano grafi di holt con archi relativi a richieste che possono essere soddisfatte

## Metodi di gestione dei Deadlock

###### Condizioni di Base per Deadlock
>[!warning] Se le risorse sono ad accesso ***mutualmente esclusivo***, ***seriali*** e ***non prerilasciabili***

^8b5cc1

### Deadlock Detection and Recovery
>[!info] Deadlock Detection and Recovery
>Permette al sistema di **entrare in stati di deadlock**
>Si utilizza un *algoritmo* per ***rilevare*** questo stato ed eventualmente eseguire un'azione di ***recovery***

#### Deadlock Detection
##### Caso 1 una risorsa per Classe

>[!teor] Teorema
>![[#^8b5cc1]]
><u>Allora</u>
>Lo stato è di deadlock **se e solo se** il *grafo di Holt* contiene un [[I Grafi#^e45e8d|ciclo]]
###### Dimostrazione
>Si utilizza una *variante* del grafo di Holt: ***grafo Wait-For***

- Si ottiene un grafo wait-for *eliminando* i nodi di tipo **risorsa** e collassando gli archi in maniera appropriata
- Il grafo di Holt contiene un *ciclo* ***se e solo se*** il grafo Wait-for contiene un *ciclo*
- Se il grafo wait-for contiene un ciclo, abbiamo ***attesa circolare***

![[CicloDeadlock.png]]
- *Un collasso appropriato sarebbe un ciclo fra il processo $t_{1}$ e $t_{2}$*
##### Caso 2 più risorse per Classe
La presenza di un *ciclo* nel caso di Holt ***non è sufficiente*** per avere deadlock
![[Deadlock2.png]]
- *Immagine a) Deadlock, Immagine b) No Deadlock*
##### Riducibilità di un grafo di Holt
>[!def] Definizione
>Un grafo di Holt si dice ***riducibile*** se esiste almeno un nodo processo con soli archi entranti
>
>>[!done] Riduzione
>>La riduzione consiste nell'***eliminare*** tutti gli archi di tale nodo e *riassegnare* le risorse agli altri processi
>>>[!question] Con quale logica?
>>>Eventualmente un **nodo** che utilizza una **risorsa** prima o poi la ***rilascerà***.

- Dalle immagini di prima (*grafo b)*), possiamo applicare le seguenti *riduzioni*:
![[HoltReduction.png]]
>[!teorema]
>![[#^8b5cc1]]
><u>Allora</u>
> Lo stato ***non*** è di *deadlock* ***se e solo se*** il grafo di Holt è *completamente riducibile*
> - ***Esiste*** una sequenza di passi di riduzione che elimina tutti gli archi del grafo
###### Esempio
>Consideriamo il seguente Grafo di Holt:

- $R_{1}\to$ Classe di Risorsa con 3 Istanze
- $R_{2}\to$ Classe di Risorsa con 2 Istanze
- $R_{3}\to$ Classe di Risorsa con 2 Istanze
- $R_{1,1}$ è assegnata al processo $t_{1}$
- $R_{1,2}$ è assegnata al processo $t_{2}$
- $R_{1,3}$ è assegnata al processo $t_{4}$
- $R_{2,1}$ è assegnata al processo $t_{4}$
- $R_{2,2}$ è assegnata al processo $t_{4}$
- $R_{3,1}$ è assegnata al processo $t_{3}$
- $R_{3,2}$ è assegnata al processo $t_{4}$
- Il processo $t_{3}$ richiede una risorsa $R_{1}$
- Il processo $t_{2}$ richiede una risorsa $R_{2}$
- Il processo $t_{4}$ richiede una risorsa $R_{3}$

>[!question] Questa, è una situazione di deadlock?

- Risposta: ***No***
>[!done] Si possono eseguire le seguenti riduzioni

![[EsDeadlock.png]]
![[EsDeadlock2.png]]

##### Knot
>[!def] Definizione
>Dato un nodo $n$, l'insieme dei nodi raggiungibili da $n$ viene detto *insieme di raggiungibilità* di $n$ e si scrive $R(n)$
>Un ***knot*** del grafo $G$ è il massimo sottoinsieme *non banale* di nodi $M$ tale che:
>$$\forall n \in M, R(n) =M$$
>>[!done] In altre Parole
>>Partendo da un *qualunque nodo* di $M$ si **possono** raggiungere tutti i nodi di $M$ e nessun nodo all'*infuori* di esso.

>[!Teorema]
>Dato un ***grafo di Holt*** con una sola richiesta sospesa per processo
>![[#^8b5cc1]]
><u>Allora</u>
>Il grafo rappresenta uno *stato di deadlock* ***se e solo se*** esiste un *knot*

### Deadlock Recovery
>Il sistema deve essere continuamente monitorato per riconoscere le situazioni di ***stallo***, utilizzando i *grafi di Holt* e quando si individua un problema si ***interviene per eliminarlo***

La risoluzione delle situazioni indesiderate può avvenire in modo:
- *Manuale*
- *Automatica*
 
>[!info] Soluzione Manuale 
>È richiesto all'operatore di *intervenire* per risolvere la situazione a favore di uno dei processi in **modo da sbloccare il sistema**

>[!Abstract] Soluzione Automatica
>Il [[Livelli del Sistema Operativo#^9f2787|sistema operativo]] è in grado di risolvere *automaticamente* lo ***stallo*** applicando *meccanismi opportuni*

#### Soluzioni
>Le soluzioni per entrambe le modalità sono:

>[!Example] Terminazione dei Processi
>È il modo ***più semplice e più drastico*** per risolvere la situazione di *Deadlock*
>- Si **forza** la *terminazione* di un processo alla volta, osservando se man mano viene risolto il *deadlock*

>[!hint] Prerilascio di una risorsa
>Viene forzato il ***prerilascio*** di una *risorsa* da parte di uno dei processi in *Deadlock* in modo che questa possa essere acquisita da un altro processo.
>>[!warning] Attenzione
>>Questa operazione ***non*** può essere effettuata per *tutti i tipi di risorse*

>[!tldr] Checkpoint / Rollback
>Viene fatto periodicamente il *salvataggio* su disco dello ***stato dei processi*** in determinati istanti ben definiti (***checkpoint***)
>In caso di *Deadlock*, si ripristina (***rollback***) uno o più processi ad uno *stato precedente*

##### Considerazioni
>[!info] Terminare processi può essere costoso
>**Uccidere** un processo che è in esecuzione da *parecchio tempo* significa perdere completamente tutto il lavoro da esso effettuato

>[!caution] Risorse in uno stato inconsistente
>Se un processo viene terminato nel mezzo di una [[Sezioni Critiche|sezione critica]] si rischia di lasciare le risorse in uno ***stato inconsistente***

>[!abstract] Preemption
>Fare ***preemption*** *non* è sempre possibile in automatico e può richiedere **interventi manuali**



>[!hint] Deadlock Prevention / Avoidance
>Si impedisce al sistema di entrare in uno stato di deadlock

>[!abstract] Ostrich Algorithm
>Ignorare il Problema