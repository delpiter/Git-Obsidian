>[!question] Perché studiare l'algebra di Bool?

Si studia l'algebra booleana poiché le funzioni dell'algebra booleana sono ***isomorfe*** ai circuiti digitali.
- Un *circuito digitale* può essere espresso tramite un'*espressione booleana* e ***viceversa***

## Funzione Booleana
---
>[!info] Definizione
>Una ***funzione booleana*** ha una o più variabili in input e fornisce risultati che dipendono solo da queste variabili
>>[!abstract] Tabella di Verità
>>Poiché le variabili possono assumere solo i valori $0$ o $1$, una funzione booleana con $n$ variabili di input, ha solo $2^n$ *combinazioni possibili* e può essere descritta dando una tabella, detta ***tabella di vertià***

$$
V=f(X,Y,Z)
$$
![[Screenshot 2024-04-10 180548.png]]

### Operazioni di Base
>*L'algebra di **Boole** si basa su tre operatori di base, `AND`, `OR`, `NOT`*

Tutte le ***funzioni booleane*** possono essere espresse come combinazione di queste tre operazioni

#### NOT
![[NOT_Logic_Gate_symbol_with_truth_table_600x600.webp]]

#### OR
![[OR_Logic_Gate_symbol_with_truth_table.png]]

#### AND
![[AND_Logic_Gate_symbol_with_truth_table_600x600.webp]]

### Rappresentazioni Alternative
>*Le dimensioni delle tabelle di verità crescono al crescere delle variabili in input, sono quindi necessarie delle rappresentazioni alternative*

#### Ordinamento delle Righe
>[!info] ‎ 
>Ordinando le righe dell'input come i ***numeri binari*** è possibile codificare le tabelle di verità memorizzando solo la colonna dell'***output***

![[Pasted image 20240410182231.png]]

#### Output `1`
>[!info] ‎ 
>Si può specificare l'output di ogni ***funzione booleana*** esprimendo, tramite una ***espressione booleana***, quali combinazioni delle variabili di input determinano l'output `1`

Questa rappresentazione è importante perché può essere ***direttamente tradotta*** in un circuito di ***porte digitali***

Nell'esempio precedente, la rappresentazione sarebbe:
- `011`
- `101`
- `110`
- `111`

