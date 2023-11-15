## Approccio al Problema
Per la risoluzione del progetto Ercole con il fine di riassemblare dei frammenti di affreschi, vasi, etc..., l'algoritmo implementa le seguenti funzioni
- Analisi Immagine
	- Tracciamento bordo del frammento
	- Calcolo del colore dominante per ogni ancora
- Ricerca della compatibilità dei pezzi
	- Confronto colore
	- Confronto bordo
- Calcolo della rotazione del frammento
### Analisi Immagine
#### Tracciamento bordo del Frammento
Il processo del tracciamento del bordo è stato diviso in più parti:
##### Rimozione sfondo
Con l'assunzione che l'immagine in input sia:
- Il frammento centrale con uno sfondo bianco "perfetto", valori $RGB=(255,255,255)$
Calcoliamo tramite una libreria di python l'immagine in scala di grigi.
- Trasformiamo poi l'immagine in bianco e nero per avere una distinzione precisa tra frammento e sfondo.
Infine sovrapponiamo le due immagini ottenute mettendo al posto dello sfondo pixel trasparenti.
##### Tracciamento bordo
Analizzando il bordo del frammento posizioniamo dei punti a distanza regolare.
Chiameremo "ancore" i punti appena posizionati
![[anchors.png|500]]
#### Calcolo colore dominante
Per ogni ancora consideriamo il colore di ogni pixel in un raggio predefinito
##### Raggruppamento colori
Dato che i colori sono molto simili ma non uguali, per calcolare il colore dominante abbiamo raggruppato i colori simili tra loro in base alla loro distanza.
- Per trovare la distanza fra due colori abbiamo considerato i tre valori $RGB$ dei colori come punti in un piano a tre dimensioni
	- Quindi la distanza fra i due colori sarà semplicemente calcolata come la distanza euclidea fra due punti in un piano tridimensionale
##### Media Colori
Una volta trovati gli insiemi di colori "simili", prendiamo l'insieme più numeroso e calcoliamo la media dei colori, utilizzando la seguente formula:
$$
C_{medio} = \displaystyle{\frac{\displaystyle\sum^n_{k=0}\text{color[0]}}{n}}+\displaystyle{\frac{\displaystyle\sum^n_{k=0}\text{color[1]}}{n}}+\displaystyle{\frac{\displaystyle\sum^n_{k=0}\text{color[2]}}{n}}
$$
Ottenendo così il colore medio dominante all'interno dell'ancora
![[colors.png|500]]

### Ricerca Compatibilità
Consideriamo un insieme di ancore adiacenti.
Esse vengono confrontate con un insieme di ancore di ugual lunghezza del frammento
confrontato
Viene calcolato un punteggio basato sulla corrispondenza dei colori
Finchè questo punteggio è superiore ad una data soglia il processo viene reiterato aumentando il
numero di ancore
Una volta usciti da questo ciclo verrà sommato al punteggio un valore basato sulla corrispondenza
della forma delle due porzioni di bordo dei frammenti
Questo processo di calcolo di punteggio verrà ripetuto per ogni combinazione di ancore possibile, per
poi salvare il punteggio più alto ottenuto

Rotazione frammenti
Infine viene calcolata la rotazione necessaria per accostare i due frammenti
Successivamente, il frammento, verrà ruotato e traslato.