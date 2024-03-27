## Memoria Principale
---
>[!info] `RAM`
>La `RAM`, ***R***andom ***A***ccess ***M***emory, o *memoria principale* è quella parte del calcolatore preposta a **immagazzinare** i *programmi in esecuzione* e i relativi *dati*
>La [[Le Memorie|memoria]] principale è di tipo ***volatile***

La `RAM` si compone di un ***numero di celle***, ognuna delle quali è in grado di memorizzare una *parte delle informazioni*
- Ogni *cella* è associata ad un ***indirizzo*** che la identifica univocamente

 Tutte le *celle* di una memoria mantengono lo ***stesso numero*** di `BIT`
 - Il numero di `BIT` associato a un indirizzo è detto *word*
 - La dimensione minima è il `BYTE`
 - La dimensione della *word* determina anche le dimensioni dei ***registri*** e delle ***istruzioni***

>[!done] Indirizzamento

Gli indirizzi di memoria sono espressi tramite numeri binari:
- Se un indirizzo ha $m$ `BIT` il numero massimo di celle indirizzabili sarà $2^m$

### Assemblaggio
>*I **chip** di memoria non vengono venduti singolarmente ma sono normalmente organizzati su schede stampate*
>*Ogni scheda contiene generalmente da $8$ a $16$ **chip***

![[Pasted image 20240327115941.png]]

#### Tipi di Memoria Principale
>[!tldr] SIMM
>***S***ingle ***I***nline ***M***emory ***M***odule
>È un tipo di *banco di memoria* dove i ***contatti dorati*** si trovano solo su un lato della scheda

>[!summary] DIMM
>***D***ual ***I***nline ***M***emory ***M***odule
>È un tipo di *banco di memoria* dove i ***contatti dorati*** si trovano su entrambi i lati della scheda
>La velocità dipende dalla ***tipologia di memoria*** (`DDR`, `DDR2`, `DDR3`, `DDR4`, `DDR5`)

>[!tldr] SO-DIMM
>***S***mall ***O***utline ***DIMM***
>Sono ***DIMM*** a dimensioni ridotte usate in genere nei portatili

