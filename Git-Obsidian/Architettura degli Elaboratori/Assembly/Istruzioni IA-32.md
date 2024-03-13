>Di seguito le istruzioni usate nello standard [[IA-32]]
## Copia e Spostamento di Valori
---
![[Pasted image 20240312144815.png]]
### MOV
>[!info] Descrizione
>`MOV DST, SRC`
>Copia un valore dall'operando `SRC` all'operando `DST`
>- `SRC` e `DST` devono avere la stessa dimensione
>- Per `SRC` è possibile utilizzare un indirizzamento *immediato*, *registro* o *memoria*
>- Per `DST` è possibile utilizzare un indirizzamento di *registro* o *memoria*
>	- Non può essere *immediato* poiché non ha senso impostare come destinazione una *costante*
>>[!warning] Indirizzamento
>>Non è possibile utilizzare un indirizzamento in memoria per entrambi gli operandi nella stessa istruzione
>>- Non è possibile scrivere una istruzione che copia valori da memoria a memoria

### PUSH e POP
>[!info] Descrizione
>`PUSH` e `POP` *mettono e tolgono* [[I Tipi di Dati|word]] dalla **cima** dello [[Definizioni_Architettura#Stack|stack]]
>>[!warning] Attenzione
>>Lo **stack** cresce verso il basso, ovvero verso indirizzi più piccoli, pertanto una `PUSH` causa causa, oltre alla copia, anche il decremento di `ESP` e una `POP` l'incremento di `ESP` (***E***xtended ***S***tack ***P***ointer)
>
>
>Si possono inserire solo **word** (`2 BYTE`) o **doubleword** (`4 BYTE`)

#### Esempio
```assembly
...            // ESP = 0x0023F7D8
PUSH EAX       // ESP = 0x0023F7D4
PUSH BX        // ESP = 0x0023F7D2
PUSH WORD PTR  // ESP = 0x0023F7D0
POP AX         // ESP = 0x0023F7D2, AX = 0x0010

ADD ESP 6      // Stack "Reset" ESP = 0x0023F7D8
```


### Exchange
>[!info] Descrizione
>`XCHG DS1, DS2`
>Scambia il contenuto di `DS1` e `DS2` in un'**unica** *operazione*

#### Esempio
```assembly
MOV AX, 5
MOV BX, 4
XCHG AX, BX //AX = 4 e BX = 5
```

### Load Effective Address
>[!info] Descrizione
>`LEA DST, SRC`
>Carica in `DST` (*registro* solitamente a `32 BIT`) l'[[Istruzione Assembly#Offset|offset]] di `SRC`
>`LEA` è l'acronimo di *Load Effective Address*
>

- Questo strano costrutto è utilizzato talvolta per **ottimizzare al massimo** il *codice*
	- Si sfruttano le peculiarità del modo di *indirizzamento* con *offset* per ***eseguire operazioni aritmetiche***
#### Esempi
```assembly
LEA EAX, [10456de4h]  // EAX = 10456de4
LEA EAX, pippo        // EAX = offset dell'indirizzo di pippo
```

```assembly
LEA EAX, pippo //Carica in EAX l'indirizzo di pippo
MOV [EAX], 10  // pippo = 10
```

### Conditional MOV
>[!info] Descrizione
>`CMOVcc DST, SRC`
>Istruzione simile alla `MOV` ma la copia viene eseguita solo se a condizione `cc` è vera
>La condizione viene determinata a partire dal valore dei `BIT` del [[Registri#Registi di Base|registri]] `EFLAG`
>Può essere considerato come una assegnazione con condizione

#### Esempio
```assembly
CMP AX,BX    // Confronta AX e BX, se sono uguali -> ZF = 1
CMOVZ CX, DX // Se ZF = 1 CX = DX
```

Questa istruzione risulta molto utile per evitare di usare ***salti condizionali***
- I salti condizionali generalmente *deteriorano le prestazioni* in quanto rendono inefficace il ***pre-fetching***


## Aritmetica Intera
---
![[Pasted image 20240312182944.png]]


### Complemento a 2
>[!info] Descrizione
>`NEG DST`
>Questa istruzione esegue il complemento a due del registro `DST`

#### Esempio
```assembly
MOV EAX, 15
NEG EAX     // EAX = -15
```
### Somma
>[!info] Descrizione
>`ADD DST, SRC`
>Questa istruzione esegue la somma fra `DST` e `SRC`
>Il risultato è **inserito in `DST`** il cui valore iniziale viene, quindi, *sovrascritto*

In base al risultato ottenuto da questa istruzione andranno opportunamente ***aggiornati i flag***:
- `OF`, `SF`, `ZF`, `AF`, `CF`, `PF`

#### Esempio
```assembly
MOV EAX, 5
ADD EAX, pippo // EAX = EAX + pippo
```

### Sottrazione
>[!info] Descrizione
>`SUB DST, SRC`
>Esegue la ***sottrazione*** `DST-SRC` e memorizza il risultato in `DST` il cui valore iniziale viene quindi *sovrascritto*

#### Esempio
```assembly
MOV EAX, 15
SUB EAX, 20 // EAX = -5 (in complemento a 2)
```

### Moltiplicazione
#### Moltiplicazione Senza Segno
>[!info] Descrizione
>`MUL SRC`
>Esegue una moltiplicazione ***senza segno***
>Il risultato dell'operazione viene messo in un registro *sufficientemente* *grande* per contenere il ***valore più grande ottenibile***
>>[!warning] Nota
>>Non è possibile usare un operando immediato per `SRC`

![[Pasted image 20240312184747.png]]
Nel caso in cui il valore più grande ottenibile si rappresenta con un numero più alto di `BIT` del registro, il risultato viene memorizzato in due registri differenti

##### Esempio
```assembly
MOV EAX, 80000000h
MOV EBX, 2h
MUL EBX             // EDX:EAX = EAX * EBX = 100000000h
					// EDX = 1h
					// EAX = 0h
```

#### Moltiplicazione con Segno
>[!question] Perchè la somma non ha bisogno di una istruzione apposita per le operazioni con e senza segno?

La somma in [[Il Calcolatore e i Numeri Binari#Complemento a due|complemento a due]] si fa nello stesso identico modo di una somma fra due numeri binari
- Di conseguenza la somma necessita di un unico circuito per essere eseguita

D'altra parte il prodotto deve tenere conto del segno separatamente

>[!info] Descrizione
>Esegue una *moltiplicazione intera* con **segno**, con operandi in ***complemento a 2***
>A differenza di `MUL` il cui formato prevede solo un operando, `IMUL` prevede *3 formati*
>>[!example] Formato 1
>>`IMUL SRC`
>>Il funzionamento è analogo a `MUL` per quanto riguarda i registri utilizzati
>
>>[!example] Formato 2
>>`IMUL DST, SRC`
>>In questo caso `SRC` può essere anche un *valore [[Istruzione Assembly#Indirizzamento Immediato|immediato]]*
>>Equivalente alla scrittura:
>>- `DST = DST * SRC`
>
>>[!example] Formato 3
>>`IMUL DST, SRC1, SRC2`
>>In questo caso `SRC2` è * **obbligatoriamente** un valore immediato*
>>Equivalente alla scrittura:
>>- `DST = SRC1 * SRC2`

>[!warning] Attenzione

Nei formati 2 e 3 possono non essere sufficienti $n$ `BIT` per memorizzare il risultato della moltiplicazione di due operandi a $n$ bit
- Sarà necessario controllare il valore del [[Registri#Flags di Stato|flag]] `OF`

##### Esempio
```assembly
MOV EAX, 10000000h
IMUL EBX, EAX, 16   // Risultato = 100000000h, EBX = 0, OF = 1!
```

### Divisione Intera
#### Divisione Senza Segno
>[!info] Descrizione
>`DIV SRC`
>Analogamente alla `MUL` la `DIV` si *comporta in modo diverso* in base alla **dimensione** dell'operando `SRC` (***divisore***)
>In particolare il *divisore*, il *quoziente* e il *resto* sono **prelevati/scritti** differentemente in base alla dimensione in `BIT` di `SRC`

![[Pasted image 20240313164236.png]]
>[!warning] Attenzione

L'operazione può causare *overflow* (es. $\frac{256}{1} =256 \implies$ overflow)
- Necessario gestirlo per prevenire il blocco del programma
#### Divisione con Segno
>[!info] Descrizione
>Per definire l'operatore `IDIV` è necessario dare una definizione al ***resto***
>>[!done] Resto
>>Il *resto* è quel numero che ***sommato*** al prodotto fra *quoziente* e *dividendo* ti da il numero originale
>
>`IDIV SRC`
>Equivalente al `DIV` ma gli operandi sono con segno

>[!warning] Problema

Quando il valore da dividere occupa solamente uno dei due registri il segno del valore deve essere "*propagato*"

>[!done] Soluzione

È stata creata una istruzione apposita per *estendere il valore* di un registro in un altro registro, ***mantenendo il segno***
- Istruzione ***specifica*** per la divisione con il *segno*
- Istruzione ***senza operandi***

`CDQ`
- Convert Doubleword to Quadword
- Converte, estendendo il segno la `DWORD EAX` nella `QWORD EDX:EAX`
`CDW`
- Converte un registro a `16 BIT` in un registro `16 BIT:16 BIT`

##### Esempio
```assembly
MOV EAX, 100
CDQ

MOV EBX, -3
IDIV EBX     // EAX = 100/-3 = -33 (quoziente), EDX = 1 (resto)
```

### Incremento
>[!info] Descrizione
>`INC DST`
>Incrementa di $1$ il valore specificato da `DST` senza alterare il [[Registri#Flags di Stato|flag]] `CF`
>Utilizzato in genere nei *cicli*

Lo stesso risultato si otterrebbe  con `ADD DST, 1`
- `INC DST` è più efficiente poiché non richiede di caricare *[[Istruzione Assembly#Indirizzamento Immediato|operandi immediati]]*

>[!note] Nota

Se `DST` ha raggiunto il valore massimo (ex. `EAX = ffffffffh`) l'istruzione incremento causa un *overflow* e quindi la destinazione assume valore `0`
- Ciò però non causa il *set* del [[Registri#Flags di Stato|flag]] `OF`
- Siccome neanche il flag `CF` viene alterato l'unico ***flag*** utile per verificare *traboccamento* è `ZF`

#### Esempio
```assembly
INC EAX    // EAX = EAX + 1
INC pippo  // pippo = pippo + 1
```
### Decremento
>[!info] Descrizione
>`DEC DST`
>Decrementa di $1$ il valore specificato da `DST` senza alterare il [[Registri#Flags di Stato|flag]] `CF`
>Utilizzato in genere nei *cilci*

Lo stesso risultato si otterrebbe  con `SUB DST, 1`
- `DEC DST` è più efficiente poiché non richiede di caricare *[[Istruzione Assembly#Indirizzamento Immediato|operandi immediati]]*

Per verificare *underflow* (***traboccamento sotto lo zero***) può essere usato il flag di segno `SF`
#### Esempio
```assembly
DEC EAX    // EAX = EAX - 1
DEC pippo  // pippo = pippo - 1
```

## Operazioni sui BIT
---
![[Pasted image 20240313205552.png]]
### AND, OR, XOR
>[!info] Descrizione
>`AND/OR/XOR DST, SRC`
>Sono le istruzioni per ***AND***, ***OR*** e ***XOR*** logici `BIT` a `BIT`
>Il risultato viene *sovrascritto* su `DST`

***AND*** e ***OR*** sono ampiamente usati per le operazioni di [[Mascherature dei Bit|mascheratura e impostazioni]] di `BIT`
***XOR*** molto utilizzato per *crittografia*
#### Esempi
```assembly
AND EAX, 00001111h       // EAX = EAX AND 00001111h
AND pippo, EBX           // pippo = pippo AND EBX
OR EAX, Vettore[EBX*2+4] // EAX = EAX OR dword all'indirizzo vettore+EBX*2+4
XOR EAX, EAX             // EAX XOR EAX -> azzera il registro
XOR EBX, 0a0b0c0dh       // EBX = EBX XOR 0a0b0c0dh
```

### SHL, SHR
>[!info] Descrizione
>`SHL/SHR DST, #`
>*Shift logico* `BIT` a `BIT` a sinistra (**L**eft) e a destra (**R**ight) in `DST` di un numero **specificato** di `BIT`
>- `#` Può essere un valore [[Istruzione Assembly#Indirizzamento Immediato|immediato]] a `8 BIT` compreso tra $0$ e $31$ oppure il registro `CL`

Entrambe le istruzioni pongono il `BIT` *entrante* a $0$, rispettivamente
- `SHR` pone il `MSB` a $0$
- `SHL` pone il `LSB` a $0$

#### Esempio
```assembly
MOV AL, 01001011b
SHR AL, 1          // AL = 00100101b
```

### SAL, SAR
>[!info] Descrizione
>`SAL/SAR DST, #`
>*Shift* ***aritmetico*** `BIT` a `BIT` a sinistra (**L**eft) e a destra (**R**ight) in `DST` di un numero di `BIT` specificato dal secondo operando (`#`)
>***Aritmetico*** significa equivalente ad una *moltiplicazione* per $2$ (`SAL`) o *divisione* per $2$ (`SAR`)
>- `#` Può essere un valore [[Istruzione Assembly#Indirizzamento Immediato|immediato]] a `8 BIT` compreso tra $0$ e $31$ oppure il registro `CL`
>
>>[!tip] Shift a Sinistra
>>Per ogni shift (`SAL`) atomico (1 posizione) il `BIT` *meno significativo* assume valore $0$
>>Mentre il `BIT` *più significativo* (che **fuoriesce**) finisce nel [[Registri#Flags di Stato|flag]] `CF`
>>`SAL` opera in modo identico al `SHL`, hanno lo stesso **OP-CODE**
>
>>[!tip] Shift a Destra
>>Per ogni shift (`SAR`) per ogni shift atomico il `BIT` *meno significativo* fuoriesce, finisce in `CF`
>>Mentre il `BIT` *più significativo* **estende il segno** (*stesso valore* del precedente `MSB`)

#### Esempi
```assembly
MOV EAX, 20
SAL EAX, 2      // EAX = 80

MOV EAX, -9
SAR EAX, 1      // EAX = -5
```

### ROL, ROR
>[!info] Destinazione
>`ROL/ROR DST, #`
>*Rotazione logica* `BIT` a `BIT` a sinistra (**L**eft) e a destra (**R**ight) di un numero specificato dal *secondo operando*
>- `#` Può essere un valore [[Istruzione Assembly#Indirizzamento Immediato|immediato]] a `8 BIT` compreso tra $0$ e $31$ oppure il registro `CL`
>Il `BIT` che **fuoriesce** rientra dall'*altra parte del valore*

#### Esempio
```assembly
MOV AL, 01010101b
ROR AL, 1          // AL = 10101010b
```

## Istruzioni di Salto
---
![[Pasted image 20240313213755.png]]

![[Pasted image 20240313213943.png]]
