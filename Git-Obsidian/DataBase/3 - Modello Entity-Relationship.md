## Modelli dei Dati
---
>Un ***modello dei dati*** è una *collezione* di **concetti** che sono utilizzati per ***descrivere i dati***, le loro associazioni e i vincoli che questi devono rispettare.

>[!tldr] Modelli Logici
>I ***modelli logici*** sono usati nei ***DBMS*** per l'*organizzazione dei dati* e usati dai programmi, ***indipendenti*** dalle ***strutture fisiche***

>[!abstract] Modelli Concettuali
>I [[Definizioni Importanti#Modello Concettuale|modelli concettuali]] permettono di rappresentare i dati in modo *indipendente* da ogni particolare sistema.
>Cercano di descrivere i ***concetti del mondo reale***.
>Sono usati nelle fasi preliminari di progettazione

I modelli concettuali prevedono una ***rappresentazione grafica***
- Utile come strumento di *documentazione* e *comunicazione*

## Modello Entity-Relationship
---
>Caratterizzato da una *rappresentazione grafica intuitiva* che consente di disegnare **schemi** E/R che facilitano la *comprensione* delle ***informazioni*** modellate
### Costrutti del Modello
>[!todo] Concetti Fondamentali
>- ***Entità*** (entity)
>- ***Associazione*** (relationship)
>- ***Attributo*** (attribute)

>[!example] Altri costrutti
>- ***Vincolo di Cardinalità*** (cardinality constraint)
>- ***Identificatore*** (identifier)
>- ***Gerarchia di Generalizzazione*** (generalization)
#### Entità
>[!def] Definizione
> Una ***entità*** sono elementi della realtà ***raggruppati in una classe***, avendo caratteristiche comuni.
> Hanno una esistenza "***autonoma***", indipendente dalle *proprietà associate*

Graficamente un'entità si rappresenta con un ***rettangolo*** al cui interno è evidenziato la ***denominazione dell'entità*** stessa

![[Entity.png]]

>[!info] Livello Intensionale
>Il ***livello intensionale*** è lo schema che rappresenta un'entità, ne descrive la *struttura*.

>[!hint] Istanza
>Un'***istanza di un'entità*** è uno specifico oggetto *appartenente all'insieme* che quella ***entità*** rappresenta

##### Denominazione
>[!warning] Importante
>Il nome di un'entità deve essere univoco all'interno di uno schema

***Non esiste*** una convenzione per il nome da assegnare a un'entità
- È preferibile utilizzare un ***sostantivo al singolare***

"***Persona***" è una denominazione preferibile a "***Persone***"
##### Estensione di un'entità
>A ***livello estensionale*** un'entità è un insieme di istanze ammissibili per quella entità.

>[!done] In Breve
> Un'***estensione di un'entità*** a un certo tempo è un ***insieme*** di specifici oggetti

#### Associazione
>[!def] Definizione
>Un'***associazione*** o ***relazione*** rappresenta un *legame logico* tra entità, rilevante nella realtà che si sta considerando

>[!hint] Istanza
>Una ***istanza di una associazione*** è una combinazione di *istanze delle entità* che prendono parte all'associazione.
>>[!done] In altre Parole
>>N-upla costituita da *occorrenze di entità*, una per ciascuna delle entità coinvolte.

Graficamente un'*associazione* si rappresenta con un **rombo** al cui interno ne viene evidenziata la ***denominazione***.
![[BinaryRelation.png]]
- Se $p$ è istanza di *Persona* e $c$ è istanza di *Città*, la coppia $(p,c)$ è istanza dell'associazione *Residenza*

> Per definizione:
- L'insieme delle istanze di un'associazione è un ***sottoinsieme del prodotto cartesiano*** degli insiemi delle istanze di entità che partecipano
##### Denominazione
>[!warning] Importante
>Il nome di un'entità deve essere univoco all'interno di uno schema

È preferibile usare un *sostantivo al singolare* per denotare un'associazione, invece di un verbo o di una composizione di nomi di entità.

> Siano "***Persona***" e "***Città***" due entità

***Residenza*** è una denominazione dell'associazione preferibile a ***Risiede*** o ***Persona-Città***

##### Grado delle Associazioni
> Una associazione ***n-aria*** coinvolge $n$ entità, non necessariamente distinte

>[!def] Grado di un'associazione
> Il ***grado di un’associazione*** è il numero di istanze di entità che sono coinvolte in un’istanza dell’associazione

***Associazione Binaria***:
- *Grado* 2
- Un'istanza è una ***coppia*** di istanze di entità

***Associazione Ternaria***:
- *Grado* 3
- Un'istanza è una ***terna*** di istanze di entità
##### Associazioni Ricorsive
>[!info] Definizione
>Legame fra un’entità e un’***occorrenza di se stessa***
>Un'associazione ricorsiva può essere o meno:
>- *Simmetrica*: $(a,b)\in A \implies (b,a)\in A$
>- *Riflessiva*: $(a,a) \in A$
>- *Transitiva*: $(a,b) \in A, (b,c) \in A \implies (a,c) \in A$

###### Tipi di associazioni ricorsive:

**Simmetrica**
- *Persona* collega di *Persona* (bidirezionale)

**Asimmetrica**
- *Persona* erede di *Persona* (unidirezionale)
#### Attributo
>[!def] Definizione
>Un ***attributo*** è una *proprietà elementare* di un'entità o di un'associazione

> Denotato con un nome che ***deve essere univoco*** all'interno dell'entità o associazione

Graficamente:
![[Attribute.png]]

Ogni attributo è definito su un ***dominio di valori***.

>[!example] Tipi di attributi
>- **Semplice**
>- **Composto**: (Es: indirizzo(via, nCivico, cap))
>- **Multivalore** (con cardinalità, es. persona con più numeri di telefono)

#### Vincoli
>In ogni schema E/R sono presenti ***vincoli***

Alcuni vincoli sono *impliciti*:
- Ogni **istanza di un'associazione** deve riferirsi a **istanze di entità**
- La coppia $(a,b)$ ***non*** può essere presente due volte nell'associazione $A\text{\&}B$

>[!note] Vincoli Espliciti
>Altri vincoli sono **espliciti** e sono definiti da chi progetta lo schema **E/R** sulla base della *conoscenza della realtà* che sta modellando

#### Vincoli di Cardinalità
>[!info] Definizione
>Per un attributo è possibile specificare anche il numero minimo e il numero massimo di valori che possono essere associati 

### IDENTIFICATORE
Attributo o insieme di attributi che identificano l’occorrenza di un’entità o relazione.
- **Interno**
- **Esterno** (Identifica insieme all’ID associato all’occorrenza dell’entità “padre”)


---

## CARDINALITÀ
Specifica per ogni partecipazione di entità a una relazione e descrive il numero minimo (N-min) e massimo (N-max) di occorrenze di relazione a cui un’entità può partecipare.

### Tipologie
- **Partecipazione**
  - Partecipazione Facoltativa (0;N)
  - Partecipazione Obbligatoria (1;N)
- **Associazione**
  - Associazione 1 a 1
  - Associazione 1 a molti
  - Associazione molti a molti

---

## GENERALIZZAZIONE/GERARCHIA
Legame logico tra un’entità **E** (entità genitore) e una o più entità **E1, E2, ...** (entità figlie), in cui **E** è il caso generale e **E1, E2, ...** sono i casi particolari.

### Tipologie
- **Generalizzazione con una sola entità figlia** → Sottoinsieme
- **Gerarchia di generalizzazione** → Un’entità figlia è a sua volta entità padre di altre entità figlie.
- **Classificazione**

Confronto fra unione delle specializzazioni e classe generalizzata
  - **TOTALE**: Ogni occorrenza dell’entità genitore è almeno una delle entità figlie.
  - **PARZIALE**: Non vale la condizione sopra.

Confronto fra le classi specializzate
  - **ESCLUSIVA**: Ogni occorrenza dell’entità genitore è al più una delle entità figlie.
  - **SOVRAPPOSTA**: Non vale la condizione sopra.

---

## BUSINESS RULES

### 2 Tipi
- **Regole di Vincolo** → `<Concetto> DEVE / NON DEVE <ESPRESSIONE SUL CONCETTO>`
- **Regole di Derivazione** → `<Concetto> SI OTTIENE <ESPRESSIONE SUL CONCETTO>`

### Implementazione
- Aggiungendo clausole SQL
- Utilizzando dei **trigger** (regole attive che si attivano a seguito di un evento)
- A livello di logica applicativa (**da codice**)
