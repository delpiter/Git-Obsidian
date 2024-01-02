## Virtual Address Space
---
>[!info] Definizione
>Lo **spazio di indirizzamento virtuale** è lo spazio di memoria che il sistema operativo mette a disposizione di un processo (programma in esecuzione).

>[!tldr] Contenuto ***VAS***
>Lo spazio di indirizzamento contiene tutte le informazioni necessarie all’esecuzione del processo, come
>1. Il codice eseguibile.
>2. I dati.
>3. L’area riservata per l’allocazione dinamica della memoria.
>4. L’area riservata per l’esecuzione delle funzioni.

### Code segment
>[!tldr]
>Il **code segment**, chiamato anche **text segment**, contiene le istruzioni eseguibili del programma.
>
- Al momento dell’esecuzione, il set di istruzioni del programma è caricato nella sezione **code segment** dello *spazio di indirizzamento virtuale* assegnato al processo
- Il code segment è **read-only** e ha una dimensione fissa, definita al momento della compilazione.

### Data Segment
>[!tldr]
>Il **data segment** è una sezione dedicata alle variabili **globali** e variabili locali `static`

- Contiene una sezione read-only dedicata alle variabili il cui contenuto non può essere modificato durante l’esecuzione del programma.
- Come per il code segment, la dimensione del **data segment** è **fissa**.
- Tranne che per la sezione dedicata alle variabili read-only, il contenuto del code segment **può essere modificato a run-time**

### Heap
>[!tldr]
>La sezione heap è utilizzata per la **gestione dinamica** della memoria.
>Può essere visto come un *magazzino*, che viene utilizzato per immagazzinare dati **temporanei** durante l’esecuzione del programma.

- A differenza della variabili globali e statiche, la cui dimensione totale è nota al momento della compilazione, la dimensione della memoria richiesta dinamicamente è nota **solo durante l’esecuzione del programma**

### Stack
>[!tldr]
>La sezione **stack** (o **call stack**, stack delle invocazioni a funzione) è utilizzata per mantenere informazioni relative alle *chiamate di funzione* durante l’esecuzione del programma.

- Una chiamata a funzione provoca l’**allocazione** sullo stack di un **record di attivazione** relativo alla funzione chiamata.

- Lo stack viene gestito tramite una modalità **LIFO** (*Last In First Out*)

### Record di Attivazione
>[!tldr]
>Il **record di attivazione** (o anche **activation record**, **stack frame**) contiene le informazioni necessarie all’esecuzione della funzione e necessarie a ripristinare lo stato del processo al termine dell’esecuzione della funzione

Una chiamata a funzione comporta approssimativamente le seguenti operazioni:
1. Il chiamante, **caller**, posiziona sullo stack o in specifici registri della CPU gli argomenti da passare alla funzione chiamata, **callee**;
2. Il caller **salva** l’indirizzo di **ritorno** sullo stack;
3. Il caller **passa il controllo** al callee;
4. Il callee **salva sullo stack** le variabili locali;
5. Il callee salva sullo stack l’**attuale contenuto** di alcuni **registri** della CPU, in modo da poterli **ripristinare** al termine della chiamata;
6. il callee **esegue** le proprie istruzioni;

Al termine dell'esecuzione:
1. Il **callee** posiziona il **valore di ritorno** in specifici registri del processore o in altre locazioni di memoria, **note al caller**;
2. Il callee **ripristina lo stato dei registri** salvati sullo stack;
3. Viene **aggiornato** lo stack pointer
4. Il **controllo** passa al caller