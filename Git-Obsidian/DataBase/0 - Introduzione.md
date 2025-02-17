# Definizioni
---
### Sistema Informativo
>[!def] Definizione
>Complesso ***sistema di procedure***, informatizzate e non, che permettono di gestire le informazioni *utili* ai processi aziendali.
>Componente che gestisce **informazioni di interesse**

Un *sistema informativo* deve provvedere alla raccolta e alla classificazione delle informazioni.
###### Funzioni
> Il sistema informativo ha le seguenti funzioni:
- *Acquisire*
- *Conservare*
- *Elaborare*
- *Condividere* e *Distribuire* le ***informazioni***

#### Classificazione
###### Sistemi Strutturati
>[!abstract] Transaction Processing System
>

###### Sistemi Semi Strutturati
>[!abstract] Management Information System

###### Sistemi Non Strutturati
>[!abstract] Decision Support System


### Dato vs Informazione
>[!quote] Dato
>Un ***dato*** è ciò che è *immediatamente presente* alla conoscenza prima di ogni elaborazione

Nell'ambito informatico si presentano sotto varie forme:
- **Numeri**
- **Lettere**
- **Immagini**
- *etc...*

>[!quote] Informazione
>Notizia, ***dato*** o elemento che consente di avere *conoscenza* più o meno esatta di ***fatti***
### Sistema informatico

>[!info] Definizione
> *Sottoinsieme* del sistema informativo.
> Tutto ciò che aumenta la *conoscenza* e deriva dall’***elaborazione di dati***

## PROBLEMI DELL’APPROCCIO BASATO SUL FILE SYSTEM
---
### Dipendenze
>[!tldr] Logica
>Intesa come la possibilità di aggiornare la ***struttura logica*** dei *dati* di un ***data base*** senza dover modificare i programmi che li elaborano.

>[!caution] Fisica
> ***Legame stretto*** tra livello *logico* e *fisico*

### Problemi generali
>[!fail] Problemi presenti con un data base basato sul *file system*

***Povertà dell'astrazione***
- È richiesta al programmatore l'*esplicitazione dei percorsi* per *accedere ai dati* e alle modalità di elaborazione

***Difficoltà per l'accesso alle informazioni***
- Ogni nuova richiesta di informazione è un *nuovo programma*

***Necessità di privatezza fra gli utenti***

***Gestione dell’integrità***
- Regola del tutto o niente
- Protezione a fronte di guasti

***Gestione della concorrenza***

## DATABASE
---
>[!def] Definizione
>Collezione di ***dati di interesse*** per una o più applicazioni
>È un *insieme di dati* **organizzato** e **multidimensionale**

#### DBMS
Software utilizzato per la gestione di un DB
Sistema software in grado di gestire efficientemente le informazioni necessarie ad un sistema informatico
Rappresenta i dati in forma integrata, secondo un modello logico, garantendo:
- Persistenza
- Condivisione
- Affidabilità
- Riservatezza

### Architettura a 3 livelli
Ad ogni livello appartiene uno schema secondo un modello:

- **Livello Esterno**: Come si presenta il DB agli utenti
- **Livello Logico**: Cosa rappresenta il DB
- **Livello Fisico**: Come vengono memorizzati i dati

#### Attori Principali
Database Administrator (DBA)
- Installa, configura e gestisce il DBMS
	- Crea gli oggetti logici necessarie per le applicazioni
	- Crea gli utenti e concede i dovuti privilegi
	- Garantisce la sicurezza e l'integrità dei DB
	- Effettua controllo e monitoraggio degli accessi
	- Monitora e ottimizza le performance dei DB
	- Pianifica strategie di backup e recovery

Data Base Designer:
- Cura la progettazione di un modello dettagliato del DB da implementare

Software Engineer
- Analisti di sistema e programmatori di applicazioni 

End User
- Persone che interagiscono con una o più basi di dati per lo svolgimento delle proprie attività

## MODELLO

Fornisce regole per schemi e istanze

### SCHEMA
Struttura del DB

### ISTANZA
Contenuto del DB

## MODELLO CONCETTUALE
Descrive i concetti del mondo reale usati nella fase di programmazione

## MODELLO LOGICO
Descrive l’organizzazione dei dati in modo visibile all’utente

---

# PROGETTAZIONE DEL DB

## 4 Fasi

1. **Raccolta informazioni e Analisi dettagliata**
   - Specifiche sui dati
   - Specifiche sulle informazioni
2. **Progettazione concettuale**
   - Scelta della tipologia di schema per la rappresentazione concettuale
   - Creazione dello schema concettuale
   - Diagramma E/R
   - Non ci si preoccupa dell’efficienza
3. **Progettazione logica**
   - Creazione dello schema logico
   - Tabelle modello relazionale
   - Importante iniziare a pensare all’efficienza
   - Necessario scegliere la categoria del DBMS (modello relazionale / non realzionale)
4. **Progettazione fisica**
   - Creazione dello schema fisico
   - Database fisico

---

# DOCUMENTAZIONE SCHEMI ER

- Serie di frasi in linguaggio naturale
- Ipotesi aggiuntive
- Glossario/Dizionario dei dati

## CONCETTO

| CONCETTO | TIPO | DESC | ATTRIBUTI | ID  |
| -------- | ---- | ---- | --------- | --- |
