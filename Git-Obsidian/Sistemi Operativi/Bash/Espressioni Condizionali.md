>[!def] Definizione
>Le ***espressioni condizionali*** sono particolari comandi che valutano alcune condizioni e *restituiscono* un [[Exit Status]] di valore `0` per indicare la ***verità*** dell'espressioni o di valore diverso da `0` per indicarne la ***falsità***
>>[!note] Sintassi
>>Ciascuna espressione si scrive mettendo le condizioni da valutare tra doppie parentesi quadre
>>- `[[...]]`

>[!warning] Le condizioni che possono essere inserite sono condizioni apposite, ***NON*** possono essere comandi

Le condizioni possono essere composte mediante *operatori logici*:
- `!` not
- `&&` and
- `||` or

E mediante delle parentesi tonde pere stabilire l'*ordine di valutazione*

>[!hint] Espressioni Valutate
>La `bash` effettua solo le seguenti interpretazioni:
>- [[Variabili#Variable Expansion|Variable Expansion]]
>- [[Valutazioni Aritmetiche|Arithmetic Expansion]] con `$(())`
>- [[Command Substitution]]
>- Process Substitution
>- [[Command Substitution#Quoting di Stringhe|Quote Removal]]
>
>Ma solamente negli operandi
>- Non si possono fare operazioni sugli ***operatori***

#### Cosa non si può fare
>[!fail] Non si possono generare operatori

>[!danger] Non si possono eseguire assegnamenti a variabili

>[!fail] Non si possono usare valutazioni aritmetiche come condizioni isolate

>[!danger] Una espressione condizionale non può contenere espressioni condizionali
## Operatori di Condizione
---
>Ci sono numerose operazioni disponibili tramite gli ***operatori di condizione***

>[!summary] Confronti Aritmetici
>Specificando gli operatori opportuni:
>- `-eq -ne -le -lt -ge -gt`
>
>Questi operatori corrispondono a:
>- $=$, $\neq$, $\leq$, $<$, $\geq$ e $>$   

>[!abstract] Condizioni su Stringhe
>Usando ***operatori di confronto*** *lessicografico* tra stringhe
>- `== = != < <= >= > `
>
>È possibile verificare se delle stringhe sono vuote
>- `-z -n`

>[!tl;dr] Condizioni sui file
>Usando gli operatori:
>- `-d -e -f -h -r -s -t -w -x -O -G -L`
>
>Confronto di date di ultima modifica di *files*
>- `-nt -ot`

