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
