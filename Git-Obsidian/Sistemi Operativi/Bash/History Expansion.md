## History Expansion
---
>[!note] Concetti Base
>La `bash` mantiene una lista completa di tutti i comandi *eseguiti in precedenza*
>- Dando a ciascun comando eseguito un **identificatore** in maniera crescente

>Il comando `history` stampa a video tutta la storia dei comandi

È possibile *eseguire* un comando per tramite del suo ***indice identificativo***
- `!1008`
	- Esegue il comando con l'**id** `1008`
È possibile *eseguire* un comando per tramite del ***nome***
- `!ca`
	- Esegue il comando che **inizia con** `ca` più *recente*

>[!danger] Attenzione, comandi Potenzialmente Pericolosi!


#### Comando `set`
>Lanciato senza nessun parametro, visualizza tutte le variabili della `shell`
>- Sia *locali* che d'*ambiente*
>Visualizza, inoltre, le ***funzioni*** implementate nella `shell`

>[!info] Lanciato con parametri
>Se lanciato con parametri serve a *settare* o *resettare* una opzione di comportamento della `shell` in cui viene eseguito
>- `set +o history` e `set -o history`, rispettivamente *disabilita* e *riabilita* la memorizzazione di nuovi comandi
>- `set -a`, dal momento in cui viene lanciato il comando, le variabili create o modificate, sono ***variabili d'ambiente***
>	- Ora le *variabili locali* si possono creare tramite il comando `export` con il flag `-n`

