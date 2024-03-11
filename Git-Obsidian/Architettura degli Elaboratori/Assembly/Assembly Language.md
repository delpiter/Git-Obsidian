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

### Immediato
>[!done] ‎ 
>Il valore è *codificato direttamente nell'istruzione* appena letta

