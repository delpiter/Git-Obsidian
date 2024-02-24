## I sistemi Digitali
---
>[!info] Segnale analogico
>Un segnale è ***Analogico*** quando i valori utili che lo rappresentano sono continui (*infiniti*) in un intervallo e non numerabili

>[!info] Segnale digitale
>Un segnale è ***digitale*** quando i valori utili che lo rappresentano sono discreti e finiti
>I calcolatori moderni utilizzano due stati logici (binari)

## L'aritmetica dei Calcolatori
---
Diversa da quella comunemente usata dalle persone

>[!tip] La Precisione

La precisione è con cui i numeri possono essere espressi è finita e predeterminata
 - I numeri devono essere memorizzati entro un limitato spazio di memoria
>[!tip] La Rappresentazione

La rappresentazione è normalmente ottenuta utilizzando il sistema binario
- Molto più adatto a essere maneggiato da un caloclatore

### Numeri a Precisione Finita
Fissate le caratteristiche del numero è determinato anche l'insieme di valori rappresentabili
- Le operazioni con i numeri a precisione finita causano errori ogniqualvolta il loro risultato **non appartiene all'insieme dei valori rappresentabili**
#### Errori possibili
>[!error] Underflow

Si verifica quando il risultato dell'operazione è minore del più piccolo valore rappresentabile

>[!error] Overflow

Si verifica quando il risultato dell'operazione è maggiore del più grande valore rappresentabile

>[!error] Non appartenenza all'insieme

Si verifica quando il risultato dell'operazione, pur non essendo troppo grande o troppo piccolo, non appartiene all'insieme dei valori rappresentabili
##### Esempi
>Numeri a precisione finita con 3 cifre senza virgola e senza segno

- $600+600 = 1200 \to$ overflow
- $300-600 = -300\to$ underflow
- $\displaystyle{\frac{007}{002}}=3,5\to$Non appartenenza all'insieme

#### Proprietà algebriche non rispettate
Le proprietà delle **operazioni** comunemente conosciute non sono **sempre vere**
>[!warning] Proprietà associativa

$a+(b-c)=(a+b)-c$
##### Esempio
$$
\begin{array}
\ 400+(300-500) = (400+300)-500 \\
400+(\underbrace{ -200 }_{ \text{Underflow} }) = 700-500
\end{array}
$$

>[!warning] Proprietà distributiva

$a\times(b-c) = a\times b -a\times c$
##### Esempio
$$
\begin{array}
\ 50\times (50-40)=50\times 50 -50\times 40 \\
50\times 10 = \underbrace{ 2500 }_{ \text{Overflow} }-\underbrace{ 2000 }_{ \text{Overflow} }
\end{array}
$$
## Sistema Posizionale
---
I sistemi di numerazione posizionali associano alle cifre un diverso valore in **base alla posizione che occupano** nella stringa che compone il numero
- Un sistema di numerazione posizionale è definito dalla ***base utilizzata per la rappresentazione***
### Sistemi posizionali utilizzati
>[!tip] Sistema Decimale

$b=10 \implies 0,1,2,3,4,5,6,7,8,9$

>[!tip] Sistema Binario

$b=2 \implies 0,1$
Ogni cifra, detta *bit* (**B**inary dig**IT**), può essere rappresentata direttamente tramite un livello elettrico di tensione

>[!tip] Sistema Ottale

$b=8\implies 0,1,2,3,4,5,6,7$

>[!tip] Sistema Esadecimale

$b=16\implies 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F$
Utilizzato nel linguaggio dell'assebly poichè molto compatto e semplice da scandire.
- Inoltre si presta bene alla traduzione in valori binari
	- Ogni cifra esadecimale corrisponde a 4 cifre binarie

### Conversione tra Basi