## I Files
---
In C le operazioni di input e di output sono gestite su **stream di dati**
>[!info]
>Uno stream di dati viene gestito in modo uniforme tramite l'**astrazione file** oppure con dati strutturati su memoria di massa
>>L'astrazione dei file permette di gestire in maniera uniforme le operazioni di *I/O*
>>senza considerare le varie caratteristiche fisiche dei device con cui sono state effettuate le operazioni

- Sono supportate due forme di **stream**
	- Stream di dati **testuali**
		- Sequenza ordinata di caratteri organizzati in righe, terminate da un carattere di `newline`
	- Stream di dati **binari**
		- Sequenza di caratteri

>[!tip] Unix
>Nei sistemi *unix* i due stream sono equivalenti
>Su altre piattaforme lo stream testuale permette di gestire in modo trasparente la conversione di caratteri *speciali* che sono inseriti in un file di testo

La struttura dati che rappresenta unp stream è chiamata `FILE`
- Nonostatne il nome, un oggetto di tipo `FILE` non rappresenta necessariamente uno stream di dati associato ad un file sulla memoria di massa
- Le dichiarazioni del tipo `FILE` e i prototipi delle funzioni di **I/O** sono definiti nell'header di libreria standard `stdio.h`