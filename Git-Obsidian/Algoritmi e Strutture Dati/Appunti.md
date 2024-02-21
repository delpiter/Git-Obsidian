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
##### Sommatorie utilizzate
>[!tip] Serie costante

$$
\sum^b_{i=a}1 =\begin{cases}
(b-a+1) \text{ se } b\geq a \\
0 \text{ altrimenti}
\end{cases}
$$
>[!tip] Serie Aritmetica $n\geq0$

$$
\sum^n_{i=0}i = \displaystyle{\frac{n(n+1)}{2}}
$$
>[!tip] Serie Geometrica $n\geq0$ e $x\neq 1$

$$
\sum^n_{i=0} x^i = \displaystyle{\frac{x^{n+1}-1}{x-1}}
$$
- Se $\mid x\mid <1$ allora
$$
\sum^n_{i=0} x^i = \displaystyle{\frac{1}{1-x}}
$$
>[!tip] Serie Armonica $n\geq 1$

$$
\sum^n_{i=1} \frac{1}{i} \approx ln(n)
$$

### Confronto fra algoritmi
Diversi algoritmi possono risolvere uno stesso problema
Analisi di complessità
>[!question] Qual è il migliore?

Si controlla l'utilizzo di risorse
- La risorsa principale è il tempo, meno ce ne mette meglio è
- Memoria richiesta, chi ne usa di più si trova piu facilmente di cercare di utilizzare più memoria di quanto se ne è a disposizione, meno se ne usa meglio è
- Numero di CPU, è sempre meglio lasciare libera una parte della CPU
- Banda passante per la comunicazione
- Energia elettrica consumata
Tempo e memoria sono le due risorse più sensibili
- Tempo sensibilità massima

Fattori del tempo di CPU
- Dimensione dell'input
- Tempo di elaborazione
- Velocità di accesso alla memoria
- Velocità della CPU
- Numero di processori
- Ottimizzatore del compilatore/linker

Leggere e scrivere dati in parti diverse del calcolatore ha delle differenze di tempo molto eleveate
- Registri
- Cache
- RAM
- Mass Storage

Il tempo di esecuzione di un algoritmo può essere espresso come il numero di passi necessari per risolvere il problema
- La differenza in tempi di esecuzione su due calcolatori diversi non deve essere un fattore di miglioramento dell'algoritmo
L'assegnazione di un valore ad una cella di memoria è la più costosa in termini di tempo
- Contandole si ha una approssimazione del tempo di esecuzione
	- Guarda esempio slides
- Possiamo denotare questo con una funzione $T$, dove $T(n)=3+(n-1)$
	- Dove $n$ è il numero di parametri in input

### O grande

Obbiettivo: 
- Capire chi e quanto cresce di più
- Non interessa il numero esatto di istruzioni si considera solo il termine dominante.
	-  Ottenendo una approssimazione di $T$
- Interessa l'andamento della funzione andando verso valori sempre più grandi
	- Come per i limiti di funzione la complessità di un algoritmo si seleziona il termine dominante
	-  Anche i coefficienti diventano non significativi per $n$ molto grandi

L'**ordine di grandezza** di $T(n)$ dipende solo dal termine che cresce di più al crescere di $n$
- Ordine di grandezza si scrive ***O grande***
$f(x) = x^3+6x^2+9x+10$
$$O(f(x)) = O(x^3)$$
Un algoritmo $O(n^3)$ non può essere usato per istanze molto grandi, mentre un algoritmo $O(n)$ è utilizzabile per istanze di dati molto grandi

#### Caso ottimo, medio, pessimo
