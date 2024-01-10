## La Struttura `FILE`
---
>[!info] Definizione
>Il tipo di dato `FILE` è una struttura che contiene una lista di campi che permettono di gestire le operazioni di **apertura**, **chiusura**, **lettura** e **scrittura** del file

- Il programmatore dovrebbe utilizzare il [[Tipi di Dati|tipo di dato]] `FILE` soltatnto tramite le [[Funzioni in C|funzioni]]  di libreria fornite, senza accedere direttamente ai campi interni della struttura
- La cosa importante da capire è che non si lavora realmente su un file, ma sul suo puntatore
	- Il [[Introduzione Puntatori|puntatore]] è riferito al file preso in considerazione