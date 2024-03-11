## L'Istruzione Assembly
---
> Consideriamo l'istruzione `MOV`, utilizzata per copiare un valore da una *sorgente* a una *destinazione*

```assembly
MOV DST,SRC
```

>[!info] Operandi
>`DST` e `SRC` vengono chiamati **operandi** dell'istruzione
>Esistono istruzioni *senza* operandi, istruzioni con *un solo* operando e istruzioni a *due o più* operandi
>Un operando può specificare ***elementi diversi***:
>- Un registro
>- Una costante
>- Un indirizzo di memoria *semplice*
>- Un indirizzo di memoria con *scostamento*

## Modi di Indirizzamento
---
>[!info]
>Gran parte delle istruzioni [[Il Livello ISA|ISA]] consentono di *caricare/salvare* i dati attraverso i registri e la memoria
>Le modalità di reperimento dei dati sono definite dai ***modi di indirizzamento***


### Indirizzamento Immediato
>[!done] ‎ 
>Il valore è *codificato direttamente nell'istruzione*
>La lunghezza del valore (1, 2, 4 `BYTE`) dipende dal tipo di *operazione e dai registri coinvolti*

```assembly
MOV AL,10 
MOV AH,10h 
MOV AH,10100101b 
MOV AX,0d3c5h      // 0 davanti al valore esadecimale per il compilatore* 
MOV EAX,104ed3c5h

MOV AX, 104ed3c5h // Errore -> Registro a 16 BIT valore a 32
```
* * Visual Studio non accetta valori che iniziano con le *lettere*

>[!tip] La costante $0$

Per caricare la costante $0$ (azzeramento del registro) invece di scrivere
```assembly
MOV EAX, 0
```
È preferibile
```assembly
XOR EAX, EAX
```
### Registro
>[!done] ‎ 
>Il valore viene preso da *un altro registro*

```assembly
MOV EAX, EBX
```

### Memoria
>[!done] ‎ 
>Il dato viene reperito da una *cella di memoria* tramite il suo indirizzo

```assembly
MOV EAX, DS:[10345467h]
MOV EAX, [ECX]
MOV EAX, [ECX+2]
```

Grazie al programma assemblatore, possiamo utilizzare *nomi simbolici per **variabili** e **indirizzi***
- Se l'indirizzo `10345467h` precedente fosse l'indirizzo della variabile `pippo`
	- Potremmo caricare il valore di `pippo` in `EAX` scrivendo:

```assembly
MOV EAX, pippo
```