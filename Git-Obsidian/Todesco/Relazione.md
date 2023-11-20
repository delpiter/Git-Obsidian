## Approccio al Problema
Per la risoluzione del progetto Ercole con il fine di riassemblare dei frammenti di affreschi, vasi, etc..., l'algoritmo implementa le seguenti funzioni
- Analisi Immagine
	- Tracciamento bordo del frammento
	- Calcolo del colore dominante per ogni ancora
- Ricerca della compatibilità dei pezzi
	- Confronto colore
	- Confronto bordo
- Calcolo della rotazione del frammento
- Unione dei due frammenti migliori
### Analisi Immagine
#### Tracciamento bordo del Frammento
Il processo del tracciamento del bordo è stato diviso in più parti:
##### Rimozione sfondo
Con l'assunzione che l'immagine in input sia:
- Il frammento centrale con uno sfondo bianco "perfetto", valori $RGB=(255,255,255)$

Calcoliamo tramite una libreria di python l'immagine in scala di grigi.
- Trasformiamo poi l'immagine in una maschera per avere una distinzione precisa tra frammento e sfondo.
Infine sovrapponiamo le due immagini ottenute mettendo al posto dello sfondo pixel trasparenti.
##### Tracciamento bordo
Analizzando il bordo del frammento posizioniamo dei punti a distanza regolare.
Chiameremo "ancore" i punti appena posizionati
![anchors|300](anchors.png)
#### Calcolo colore dominante
Per ogni ancora consideriamo il colore di ogni pixel in un raggio predefinito
##### Raggruppamento colori
Dato che i colori sono molto simili ma non uguali, per calcolare il colore dominante abbiamo raggruppato i colori simili tra loro in base alla loro distanza.
- Per trovare la distanza fra due colori abbiamo considerato i tre valori $RGB$ dei colori come punti in un piano a tre dimensioni
	- Quindi la distanza fra i due colori sarà semplicemente calcolata come la distanza euclidea fra due punti in un piano tridimensionale
##### Media Colori
Una volta trovati gli insiemi di colori "simili", prendiamo l'insieme più numeroso e calcoliamo la media dei colori, utilizzando la seguente formula:
$$
C_{medio} = \displaystyle{\frac{\displaystyle\sum^n_{k=0}\text{color[n][R]}}{n}}+\displaystyle{\frac{\displaystyle\sum^n_{k=0}\text{color[n][G]}}{n}}+\displaystyle{\frac{\displaystyle\sum^n_{k=0}\text{color[n][B]}}{n}}
$$
Dove $n$ è il numero di colori presenti nell'insieme più numeroso trovato e $\text{color}$ è un array contente i valori RGB di ogni colore, ottenendo così il colore medio dominante all'interno dell'ancora
![colors|300](colors.png)
### Ricerca Compatibilità
Consideriamo un insieme di ancore adiacenti.
- Esse vengono confrontate con un insieme di ancore di ugual lunghezza del frammento confrontato
- Viene calcolato un punteggio basato sulla corrispondenza dei colori, calcolando la distanza tra i colori di ancore corrispondenti 
- Finchè questo punteggio è superiore ad una data soglia il processo viene reiterato aumentando il numero di ancore su entrambe le porzioni

Una volta usciti da questo ciclo verrà sommato al punteggio un valore basato sulla corrispondenza della forma delle due porzioni di bordo dei frammenti.

Questo processo di calcolo di punteggio verrà ripetuto per ogni combinazione di porzione di ancore possibili, per poi salvare il punteggio più alto ottenuto.

Da qui in avanti ci riferiremo a questa porzione come "porzione di matching".
![match|500](match.png)
### Rotazione frammenti
Viene poi calcolata la rotazione necessaria per accostare i due frammenti sulla porzione di matching.
Successivamente, il frammento, verrà ruotato e traslato evitando sovrapposizioni.
![merged_with_portions|500](merged_with_portions.png)
### Unione dei Frammenti
Per riunire i due frammenti in un unico pezzo:
- Partendo dalla porzione di matching troviamo gli estremi dei lati combacianti.
- Eliminiamo tutte le ancore comprese tra questi estremi e uniamo le restanti in un unico bordo
![merged_with_borders|500](merged_with_borders.png)
### Ricostruzione del dataset
L'unione dei frammenti precedente viene considerata come un unico frammento e l'algoritmo viene reiterato finché non rimarrà una sola immagine contenente tutti i frammenti disposti in maniera che combacino tra di loro
![full|500](full.png)
## Criticità dell'algoritmo
L'algoritmo presenta criticità in alcune fasi
- Le sovrapposizioni vengono evitate solo successivamente alla fase di comparazione delle ancore, quindi al confronto delle porzioni del bordo possono capitare combinazioni per le quali i frammenti si sovrappongono su parti non appartenenti a quelle combacianti.
- Nel caso dovesse verificarsi il problema precedentemente esposto, in fase di unione dei bordi tra i frammenti, vengo eliminate erroneamente ancore che dovrebbero essere mantenute.