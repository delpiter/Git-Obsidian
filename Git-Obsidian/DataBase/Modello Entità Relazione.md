# MODELLO ENTITÀ RELAZIONE

Serie di strutture logiche utilizzate per definire schemi, occorrenze e istanze.

## Componenti

### ENTITÀ
Elementi della realtà raggruppati in una classe, avendo caratteristiche comuni.
- Concetto autonomo

### ATTRIBUTO
Proprietà con cui è possibile descrivere un’entità o una relazione.
- Concetto dipendente
- Diversi tipi:
  - **Semplice**
  - **Composto** (Es: indirizzo(via, nCivico, cap))
  - **Multivalore** (con cardinalità, es. persona con più numeri di telefono)

### IDENTIFICATORE
Attributo o insieme di attributi che identificano l’occorrenza di un’entità o relazione.
- **Interno**
- **Esterno** (Identifica insieme all’ID associato all’occorrenza dell’entità “padre”)

---

## RELAZIONE/ASSOCIAZIONE
N-upla costituita da occorrenze di entità, una per ciascuna delle entità coinvolte (insieme matematico).

### Reificazione
Operazione che trasforma una relazione o un attributo in un’entità.

### Associazioni ricorsive
Legame fra un’entità e un’occorrenza di se stessa.
- **Simmetrica**: Persona collega di Persona (bidirezionale)
- **Asimmetrica**: Persona erede di Persona (unidirezionale)

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

### Caratteristiche
- Ogni occorrenza di un’entità figlia è anche occorrenza dell’entità genitore.
- Ogni proprietà dell’entità genitore è anche proprietà delle entità figlie.

### Tipologie
- **Generalizzazione con una sola entità figlia** → Sottoinsieme
- **Gerarchia di generalizzazione** → Un’entità figlia è a sua volta entità padre di altre entità figlie.
- **Classificazione**
  - **TOTALE**: Ogni occorrenza dell’entità genitore è almeno una delle entità figlie.
  - **PARZIALE**: Non vale la condizione sopra.
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
