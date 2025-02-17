# NORMALIZZAZIONE

Attività che permette di trasformare schemi non normalizzati in schemi che soddisfano una **forma normale**.

- Utilizzata come tecnica di verifica dei risultati della progettazione di una base di dati.
- **Non** è una metodologia di progettazione.

## Forme normali

### Proprietà di uno schema relazionale
Garantiscono:
- **Qualità** del database.
- **Assenza di determinati difetti**.

## Anomalie

### Anomalia di aggiornamento
- Necessario modificare il valore in diverse tuple.

### Anomalia di cancellazione
- Perdita di informazione a seguito di una cancellazione di un dato diverso.
  - **Esempio:** Studente e scuola → Se uno studente interrompe la partecipazione a tutte le scuole, bisogna eliminare lo studente.

### Anomalia di inserimento
- L’inserimento di dati nuovi deve essere accompagnato dall’inserimento di dati non necessari.
  - **Esempio:** Studente e scuola → Per aggiungere un nuovo studente, bisogna aggiungere anche la scuola.

---

# DIPENDENZE FUNZIONALI

- Nuovo tipo di vincolo.
- Si considerino:
  - Un’istanza **r** di uno schema **R(X)**.
  - Due sottoinsiemi (non vuoti) di attributi **Y** e **Z** di **X**.
- Si dice che in **r** vale la dipendenza funzionale (FD) **Y → Z** se:
  - Per ogni coppia di tuple **t1** e **t2** di **r** con gli stessi valori su **Y**, **t1** e **t2** hanno gli stessi valori anche su **Z**.
- Una dipendenza funzionale sempre soddisfatta è detta **banale**.

---

# FORME NORMALI

## Prima forma normale (1NF) - "Forma Atomica"
- Ogni attributo deve avere un **dominio atomico**.
- Ogni attributo deve contenere solo **un valore**.

## Seconda forma normale (2NF)
Uno schema è in **2NF** se:
1. È in **1NF**.
2. Ogni attributo **non chiave** dipende **completamente** da ogni chiave.

## Terza forma normale (3NF)
Uno schema è in **3NF** se:
1. È in **2NF**.
2. Non esistono **dipendenze transitive**.
   - **Un attributo non chiave** non deve dipendere da **un altro attributo non chiave**, che a sua volta dipende dalla chiave dello schema.
- È sempre possibile ottenere schemi in **3NF** preservando tutte le dipendenze.

## Forma normale di Boyce e Codd (BCNF)
Uno schema è in **BCNF** se:
- Per ogni dipendenza funzionale non banale **Y → Z**, **Y** è una **superchiave** dello schema.
- **Non è sempre possibile** portare uno schema in **BCNF**.

---

# DECOMPOSIZIONE SENZA PERDITA

- La decomposizione non deve alterare il **contenuto informativo** del database.
- **Decomposizione lossless**: Uno schema si decompone senza perdita se, eseguendo il **join naturale** delle tabelle “decomposte”, si ottiene esattamente la tabella originale.
- Una decomposizione **con perdita** può:
  - **Perdere** delle tuple.
  - **Generare** delle tuple errate.
