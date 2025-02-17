# PROGETTAZIONE LOGICA

Traduzione dello schema concettuale in uno schema logico.

## Modello logico

- Insieme di concetti per organizzare i dati relativi a un certo dominio di interesse.
- Insieme di regole per modellare eventuali vincoli e restrizioni sui dati.

---

# MODELLO RELAZIONALE

I dati sono divisi in record di dimensione fissa e organizzati in tabelle.

## Tabelle

- **Intestazione della tabella**
- **Schema della relazione** (nome tabella + attributi)
- **Colonne** → Attributi
- **Righe** → Istanze della relazione
- NON possono esistere attributi uguali.
- NON possono esistere righe uguali.
- I dati di una colonna devono essere omogenei (di un solo tipo).
- Ogni attributo dispone di un **dominio**, che definisce l’insieme dei valori validi per quell’attributo.

## Forme Normali

Le relazioni devono rispettare determinate proprietà matematiche per garantire coerenza e minimizzazione della ridondanza.

## Relazioni Matematiche

- **Sottoinsieme del prodotto cartesiano**
- **Prodotto cartesiano**: insieme delle tuple ordinate.
- Nei database, la rappresentazione NON è posizionale: (a; b) == (b; a).

## Definizioni Rigorose

- **Schema di Relazione R(X)**: un nome R con un insieme di attributi A1, A2, ..., Ax → X.
- **Istanza di una relazione su uno schema R(X)**: insieme r di ennuple su X.
- **Schema di Database**: insieme di schemi di relazioni → R = {R1(X1), ..., Rk(Xk)}.
- **Istanza di Database**: insieme delle istanze di relazioni → r = {r1, ..., rk}.

---

# ENNUPLA SENZA INFORMAZIONE

## Casi

- **Valore non noto**
- **Valore inesistente**
- **Valore senza informazione**

## Soluzioni

- Applicare un valore di **default**.
- Valori speciali per ogni attributo (le applicazioni devono conoscerli).
- Applicare un valore **NULL**:
  - Per definizione **NULL != NULL**.
  - Gestisce i tre casi possibili.

---

# VINCOLI DI INTEGRITÀ

Funzione booleana che associa un’istanza r di un database definito su uno schema a un valore di verità.

## Istanza lecita

Un’istanza che soddisfa i vincoli definiti.

## Tipologie di vincoli

### Intra-Relazionali (sulla singola tabella)

- **Vincoli di ennupla**: condizioni su ciascuna ennupla singolarmente (espresse con espressioni booleane).
- **Vincoli di Chiave**: garantiscono l’unicità delle tuple.

### Inter-Relazionali (fra più relazioni)

- **Collegamenti tra relazioni** espressi mediante valori comuni in attributi replicati.
- Ogni riga della tabella referenziante si collega al massimo con una riga della tabella referenziata.

#### Vincolo di Integrità Referenziale

**Foreign Key**: impone che i valori, diversi da NULL, su un attributo X in R1 compaiano come valori della chiave primaria di R2.

### Errori

- Un’operazione di modifica su una relazione causa una violazione di VIR su altre relazioni.

### Soluzioni

- **Eliminazione a cascata**.
- **Non consentire l’operazione**.
- **Inserimento di valori NULL**.

---

# CHIAVI

Insieme di attributi che consente di identificare univocamente un’enntupla di una relazione.

## Utilizzo

- Accesso a ciascuna ennupla della base di dati.
- Correlazione dei dati tra relazioni diverse.

### Superchiave

Un sottoinsieme k di attributi è detto **superchiave** se NON contiene due ennuple distinte t1 e t2 con t1[k] = t2[k].

### Definizione formale di chiave

- Una **chiave** di una relazione è una **superchiave minimale** di r.
- Non esiste una superchiave k’ in k.
- Esiste sempre almeno una chiave/superchiave.

### Caso estremo

- Tutti gli attributi possono costituire una superchiave.
- Possono esistere più chiavi/superchiavi.

### Chiave Primaria

- Chiave di una relazione su cui NON sono ammessi valori **NULL**.
- Ogni relazione deve averne una.
- Può essere composta da uno o più attributi.
