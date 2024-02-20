## Fondamenti
Algoritmo è un modo di risolvere un problema
### Problemi
In matematica un problema è un quesito che richiede la determinazione o la costruzione di uno o più enti che soddisfino alle condizioni specificate nell'enunciato del problema

Vengono forniti dei dati in ingresso
- Con una struttura nota

Vengono richiesti dei dati in uscita non noti ma che devono soddisfare delle condizioni note
- Deve essere vero un predicato specificato dall'enunciato del problema

Ciclo hamiltoniano
- Sequenza di nodi che parte da un nodo e passa tutti i nodi una sola volta tornando in fine al nodo iniziale

Dato un problema una sua risoluzione è un processo che trasforma i dati in ingresso nei corrispondenti dati finali

L'algoritmo è una sequenza di azioni non ambigue che risolve un problema utilizzando un insieme di azioni elementari che possono essere eseguite da un opportuno esecutore

 - UN ALGORITMO NON È UN **PROGRAMMA**
	 - Un programma è un algoritmo scritto in un linguaggio che una macchina è in grado di capire
	 - Per scrivere un algoritmo non è necessario conoscere un linguaggio di programmazione specifico

Le istruzioni devono essere:
- Non ambigue
	- Deve essere interpretata univocamente da chiunque
Una ricetta di cucina può essere un algoritmo unicamente se soddisfa i requisiti.
- La maggiorparte delle ricette scritte sembra un algoritmo in quanto sia una sequenza di istruzioni
un algoritmo soddisfa queste prop
Proprietà degli Algoritmi:
- **Input** deve essere un insieme ben specificato
- **Output** deve essere una struttura algebrica ben specificata 
- **Non ambiguità** di ogni passo di elaborazione
	- Chiunque legge l'algoritmo deve sapere che cosa richiede di fare una precisa istruzione
- **Eseguibilità** di ogni istruzione in tempo finito
	- Ogni passo deve concludersi in un tempo finito
- **Correttezza** l'algoritmo deve funzionare per ogni possibile input
- **Finitezza** Un algoritmo deve concludere in un numero finito di passi
- **Efficacia** di ogni passo di elaborazione
- **Generalità** per una classe di problemi



## Algoritmi
Ogni problema può essere risolto in **molti modi diversi**
- Ne consegue il fatto che esistono diversi algoritmi di soluzione per uno stesso problema

>[!question] Quale conviene usare??

Esiste un modo per confrontare algoritmi
Necessità
- Deve essere possibile saperli rappresentare ->**pseudocodice**
- Deve essere possibile saperli confrontare -> **Notazione O grande**

#### Pseudocodice
Algoritmo è espresso come una sequenza id azioni elementari (passi) da eseguire per risolvere il problema

I passi vengono rappresentati con un linguaggio astratto ed informale: **lo pseudocodice**
- Non richiede regole sintattiche necessarie in un linguaggio di programmazione
- Utilizza però la struttura di un linguaggio di programmazione normale ma è inteso per la comprensione umana
- Il linguaggio è aumentato con passi in linguaggio naturale
- Non esiste nessuno standard

Esistono parole chiavi comuni:
- `do while  ... endDo;`
- `repeat ... until;`
- `if ... endif;`
- `case ... endCase;`
- `return ...;`

Gli array hanno indici che iniziano da $1$
I blocchi devono essere sempre indentati
- Racchiusi o fra parentesi graffe o fra parole chiave e terminatore 
Spesso vengono usati verbi inglesi 

###### Es
```
function max(a1,a2,...,an)
max = a1
for i=2 to n
	if max < ai then max = ai
```


#### Sommatorie
$$
\sum^5_{i=2} i
$$
