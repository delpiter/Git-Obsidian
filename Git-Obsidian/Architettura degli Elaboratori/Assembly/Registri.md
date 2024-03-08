## Registri [[IA-32|IA-32]]
---
![[Pasted image 20240308093600.png]]

## Registi di Base
---
![[Pasted image 20240308094435.png]]

>[!info] $8$ registri di utilizzo **più o meno generale**
- Fra questi i primi *4 registri* possono essere utilizzati in 3 *modalità*
	1. A $8$ `BIT` $\to$ `AL,AH,BL,BH,...`
	2. A $16$ `BIT` $\to$ `AX,BX,CX,DX,...`
	3. A $32$ `BIT` $\to$ `EAX,EBX,ECX,...`

>[!info] ***Instruction Pointer*** `EIP`:
- Contiene l'indirizzo della prossima istruzione da eseguire
- Viene *incrementato automaticamente* durante il **Fetch** delle istruzioni e *modificato dalle istruzioni di salto*

>[!info] ***EFLAGS***, `BIT` di stato
- Questo registro contiene diversi `BIT` utili sia alla `CPU` sia al programmatore
- I `BIT` principali determinano i cosiddetti **condition code**
	- Vengono scritti a ogni ciclo dell'`ALU` e riflettono il risultato dell'operazione e riflettono il risultato dell'operazione più recente

>[!abstract] Flag più comuni
*Tra parentesi il nome visualizzato nel debug di Visual Studio*
- `CF` (`CY`): ***Carry Flag***
	- Attivo quando il risultato ha determinato un riporto uscente
- `PF` (`PE`): ***Parity Flag***
	- Attivo quando il `BYTE` meno significativo del risultato ha il numero di `0` o `1` *pari*
- `AF` (`AC`): ***Auxiliary Flag***
	- Attivo quando il risultato ha determinato *riporto intermedio* sul `BIT` 3
- `ZF` (`ZR`) ***Zero Flag***
	- Attivo quando il risultato è *zero*
- `SF` (`PL`) ***Sign Flag***
	- Attivo quando il risultato è negativo
- `OF` (`OV`) ***Overflow Flag***
	- Attivo quando il risultato ha causato *overflow* con operazioni in aritmetica intera con segno
- `DF` (`UP`) ***Direction Flag***
	- Indica la direzione nelle istruzioni di *manipolazione stringhe*

Altri `BIT` sono dedicati alla [[IA-32#Modalità Operative|modalità operativa]] e a particolati **modalità di funzionamento**
- Come esecuzione *step by step* o *interrupt*
