>*Con le porte `NAND` è possibile realizzare qualsivoglia circuito*
>*Sarebbe logico creare [[Circuiti Digitali#Circuiti Integrati|circuiti integrati]] con una grande quantità di porte `NAND` indipendenti*
>[[Definizioni_Architettura#Economy|Problema]]

Allo scopo di ***aumentare il rapporto porte/piedini***
- I chip vengono realizzati *implementando internamente* circuiti più complessi collegando in uscita solo i ***piedini "rilevanti"***

## Multiplexer
---
>[!info] Descrizione
>Un ***multiplexer*** è un circuito con $2^n$ ***input di dati*** e $n$ ***input di controllo***
>- Gli *input di controllo* selezionano **quale** fra i $2^n$ *input dati* deve essere ***portato in uscita***

![[Screenshot 2024-04-12 145603.png]]
#### Esempio
![[Pasted image 20240412145223.png]]
*Multiplexer con $8$ input*

## Demultiplexer
---
>[!info] Descrizione
>Si tratta del circuito inverso del ***multiplexer***
>In questo caso $1$ ***input dati*** viene "*smistato*" su una delle $2^n$ ***linee di output***
>- Sempre in base alla selezione degli ***input di controllo***

![[Screenshot 2024-04-12 150036.png]]


> Un circuito costituito da un ***multiplexer*** $+$ una ***linea dati*** $+$ un ***demultiplexer***
> può essere usato per mettere in ***comunicazione più utenti*** su una stessa linea dati

## Decoder
---
>[!info] Descrizione
>Un ***decoder*** è un circuito che riceve in ***input*** $n$ segnali che vengono trattati come un numero binario di $n$ cifre
>Il *decoder* ha $2^n$ ***linee di output*** di cui ***una sola*** viene impostata a $1$
>- Sarà la linea **selezionata** dal *numero binario in input*

![[Pasted image 20240412151403.png]]

>[!done] Ovviamente esiste anche il circuito inverso, chiamato *encoder*

## Comparatore
---
>[!info] Descrizione
>Un ***comparatore*** confronta due parole di input e produce un output che indica l'***uguaglianza/inuguaglianza*** degli input
>Il circuito può essere realizzato con porte `XOR`

![[Logica Digitale#XOR]]

#### Esempio
>*Un comparatore di due parole $A$ e $B$ di `4 BIT` ciascuna*

Ogni porta `XOR` confronta una coppia di `BIT`
- Se almeno una delle coppie è diversa uno degli input della porta `NOR` vale $1$
	- L'output del comparatore vale $0$

![[Pasted image 20240412153159.png]]

## Circuiti Aritmetici
---
>[!info] I circuiti aritmetici