## `21/02/2024`
### Byte




#### Modalità di rappresentazione negativi
>[!tip] Grandezza e segno

Con questa rappresentazione il bit più significativo viene utilizzato per il segno
- Con zero si indicano i valori positivi
- Con 1 si rappresentano i valori negativi

>[!bug] Problema: doppia rappresentazione dello $0$

>[!tip] Complemento a due

Con questa rappresentazione il bit più significativo viene comunque usato per il segno
Codifica a due passaggi:
1. Negare tutti i bit
	1. `0101`$\to$ `1010`
2. Si aggiunge uno al risultato
	1. `1010 + 0001 = 1011`

In caso di riporto nella ottava cifra, non è necessario aggiungere la nona cifra, basta ignorare l'ultimo riporto.

I numeri positivi sono rappresentati esattamente nello stesso modo, mentre per i numeri negativi bisogna ripetere i passaggi usati nella conversione
1. `1011`$\to$`0100`
2. `0100 + 0001 = 0101`

Pro
- Unica rappresentazione dello $0$
- I numeri positivi sono codificati nello stesso modo di prima
- La sottrazione è eseguibile semplicemente sommando il numero con il numero in complemento a $2$
##### Operazioni in colonna con complemento a due

Il riporto generato dai bit più a sinistra, esso viene ignorato
- Se gli addendi sono di segno opposto non si può verificare un *overflow*
- L'overflow si verifica se gli ultimi due riporti nel fare la somma sono diversi fra di loro
-  Gli ultimi due riporti sono i " segnalatori di overflow"
>[!tip] Eccesso $2^{m-1}$

Consente di rappresentare i numeri come somma di se stessi con $2^{m-1}$ dove $m$ è il numero di bit  utilizzati per rappresentare il valore
- Si noti che il sistema è identico al complemento a due con il bit di segno invertito
- Per rappresentare il numero in eccesso $2^{m-1}$ basta sommare al numero il numero massimo rappresentabile con $m-1$ bit 
	- `0100` $\to$ 4 bit
	- `0100 + 0111 = 1011`
- Visualizzandolo nella retta dei numeri naturali sarebbe come "spostare" il minimo e il massimo numero rappresentabile a sinistra dell'unità massima rappresentabile $-1$ ($2^{m-1}$)

Anche in questa codifica è possibile fare la sottrazione come addizione di un numero con l'altro numero codificato in eccesso $2^{m-1}$

