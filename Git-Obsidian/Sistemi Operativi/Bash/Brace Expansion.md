>[!info] Comando
>Un ordine di ***brace expansion*** è una *stringa di testo*
>Sono *espansioni della riga* costituite da **tre parti** e **due separatori**
>Una parte iniziale, seguita da una *parentesi graffa*, seguita da *altro testo* seguito da *parentesi graffa* chiusa seguita da *altro testo*
>- `adsf{asdf}asdf`
>
>>[!abstract] Preambolo e Postscritto
>>Sono le sequenze di caratteri *prima* e *dopo* le parentesi graffe
>
>>[!example] Parte centrale
>>La sequenza di stringhe, separate da virgola, *compresa* fra le parentesi graffe
>>- **Non** sono presenti *tab* o *spazi bianchi*
>>- Ciascuna stringa rappresenta una ***possibile scelta*** di stringhe che possono essere aggiunte al *preambolo* e seguite dal *postscritto*

Il comando `echo he{asd,dfg,poe}vb
- viene *espanso* in questa maniera:
	- `echo heasdvb hedfgvb hepoevb`

>Possono mancare *preambolo*, *postscritto* o ***entrambi***

>[!warning] Non ci possono essere spazi bianchi o tab
>O **non** viene *riconosciuta* come brace expansion

Si possono *proteggere* con dei **backslash**: 
- `{aa,bb\ ,cc}`: Brace expansion valida

##### Variabili
> È possibile inserire delle *variabili* nelle brace expansion
- Inserendo le *variabili* come segue: `$(variablename)`
- Il comando verrà espanso seguendo l'*ordine* descritto dal [[Terminale Unix#Espansioni|terminale]]
##### Annidamento
>È possibile ***annidare*** degli ordini di *brace expansion* dentro ordini di *brace expansion*

#### Semplificazione
>Sono state introdotte delle semplificazioni per elenchi di caratteri

***Sintassi***
- `echo a{b..e}f`
	- Sarebbe *equivalente* a:
	- `echo a{b,c,d,e}f`