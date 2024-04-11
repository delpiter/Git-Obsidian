>*L'output di un circuito digitale può essere descritto, oltre come [[Algebra di Bool#Da Tabella di Verità a Espressione Booleana|tabella di verità]], anche come [[Algebra di Bool#Funzione Booleana|funzione booleana]] dei suoi input*

$$
M=\overline{A}BC+A\overline{B}C+ABC
$$
![[Screenshot 2024-04-11 145137.png]]
*Tabella di verità $\nearrow$*

![[Pasted image 20240411150311.png]]
*Circuito associato alla tabella di verità e funzione booleana*

>[!done] Da funzione booleana a circuito digitale

1. Scrivere la ***tabella di verità*** per la funzione
2. Disporre di invertitori (`NOT`) per generare il ***complemento di ogni input***
3. Introdurre una ***porta*** `AND` per ogni termine con `1` nella colonna dell'***output***
4. ***Collegare le porte*** `AND` agli input appropriati
5. Inviare l'output di tutte le porte `AND` in ***una porta*** `OR`

>[!abstract] Dal punto di vista Hardware
>Dal punto di vista costruttivo, è preferibile realizzare un circuito utilizzando ***un solo tipo di porta logica***
>- Preferibilmente `NOR` o `NAND`

