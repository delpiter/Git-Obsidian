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
