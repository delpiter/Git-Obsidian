>[!def] Definizione
>Il ***multiplexing*** è il meccanismo per cui più *canali trasmissivi in ingresso* condividono lo stesso [[Git-Obsidian/Reti/0 - Introduzione#Canale|canale]] per trasferire più flussi di informazione in **un solo segnale** (detto _multiplato_).

Più canali sono trasportati dallo stesso ***mezzo di trasmissione***.

Si può realizzare utilizzando:
- ***Tempo*** (***T***ime ***D***ivision ***M***ultiplexing)
- ***Frequenza*** (***F***requency ***D***ivision ***M***ultiplexing)
- ***Codice*** (***C***ode ***D***ivision ***M***ultiplexing)
- ***Spazio*** (***S***pace ***D***ivision ***M***ultiplexing)

>[!hint] Efficienza
>Dal punto di vista ***teorico*** queste modalità sono *equivalenti*

### Time Division Multiplexing
>[!info] Definizione
>Il ***TDM*** è una ***tecnica di multiplexing*** di un canale di comunicazione secondo la quale ogni dispositivo *ottiene a turno* l'uso esclusivo del canale

#### TDM Slotted/Unslotted

>[!note] TDM Unslotted
>Nel *Time Division Multiplexing* di tipo ***Unslotted***, l'asse dei tempi *non* è suddiviso a priori.
>Si possono adottare unità informative di *lunghezza variabile*.
>- È necessario un ***sistema esplicito di delimitazione*** delle unità informative

![[TDMUnslotted.png]]

>[!example] TDM Slotted
>Nel *Time Division Multiplexing* di tipo ***Slotted***, l'asse dei tempi è *suddiviso* in intervalli di durata prefissata (**slot**)
>- Le *unità informative* hanno tutte la **stessa lunghezza** commisurata al singolo ***slot***

![[TDMSlotted.png]]

##### Framed/Unframed
>[!caution] Framed
>I singoli *slot* vengono strutturati in un ***frame***.
>La **sincronizzazione** non è necessaria a livello di ogni singolo slot, ma viene fatta ad ogni *frame*

>[!todo] Unframed
>I singoli *slot* si susseguono ***senza una struttura predefinita***.
>- Occorre un sistema di sincronizzazione di *slot*
### Frequency Division Multiplexing

## Assegnazione della Banda
---
>[!def] Assegnazione Statica
>Nella ***assegnazione statica*** il flusso informativo
>La banda ***non può cambiare*** a comunicazione in corso.
>