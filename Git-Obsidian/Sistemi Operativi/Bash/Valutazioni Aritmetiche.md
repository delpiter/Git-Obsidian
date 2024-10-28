>È possibile *valutare una stringa* come se fosse una ***espressione costruita da operazioni aritmetiche*** tra soli numeri **interi**

>[!cite] Valutare operazioni con valori *non solo interi*
> Esiste un programma specifico: `Basic Calculator`
> Usato tramite il comando `bc`
> >[!danger] Rospi Maledetti, basta sapere che esiste

Esempio
```bash
echo "(32.16 - 14.03 ) / 3.33" | bc -l -q
# Visualizza 5.44444444444
```

Operatori:
>`(())` e `$(())`

>[!example] `(())`
>L'operatore `(())` racchiude ***tutta una riga di comando*** semplice, che deve essere una *espressione*, più un eventuale assegnamento
>>[!note] Esempio
>>`((NUM=3+2))`
>>Assegna 5 alla variabile `NUM`


>[!tl;dr] `$(())`
>L'operatore `$(())` racchiude ***una parte di una riga di comando*** , che deve essere una *espressione*, più un eventuale assegnamento.
>La bash:
>- *Valuterà* aritmeticamente l'espressione racchiusa
>- *Sostituisce* il risultato all'intera espressione
>- *Esegue* il comando modificato
>>[!note] Esempio
>>`$((3+2))`
>>Inserisce `5` al posto della riga di comando


Le valutazioni aritmetiche  
### Operazioni Disponibili
>Le valutazioni aritmetiche possono contenere:

>[!tip] Operatori Aritmetici
>Come `+`, `-`, `*`, `/` e `%`

>[!abstract] Degli Assegnamenti
>Come `NUM=3`

>[!attention] Delle Parentesi Tonde
>Per accorpare operazioni e *modificare precedenze*

>[!example] Espressioni Booleane
>Operatori Utilizzabili:
>- `==`, `!=`, `>`,`>=`,`<` e `<=`
>
>Utilizzate spesso per gli [[Exit Status]]
>Ritorna nella variabile `$?`:
>- Un numero *diverso da zero* se durante la valutazione è accaduto un **errore**
>- *Uguale a zero* se la valutazione aritmetica fornisce un *risultato logico* `true`
>- *Diverso da zero* se la valutazione aritmetica fornisce un *risultato logico* `false`
>- *Uguale a zero* se la valutazione aritmetica fornisce un *risultato intero diverso da zero*
>- *Diverso da zero* se la valutazione aritmetica fornisce un *risultato intero ugualea zero*