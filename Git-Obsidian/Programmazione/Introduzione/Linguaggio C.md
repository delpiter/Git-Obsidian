## Introduzione
---
Il linguaggio C, così come qualsiasi altro linguaggio di programmazione è definito da:

>[!tip] Alfabeto
>Insieme di simboli ammissibili nel linguaggio

>[!tip] Regole Lessicali
>Con i caratteri dell'alfabeto possiamo formare Sequenze finite di simboli dette _parole_.
>Non tutte le sequenze sono ammissibili nel linguaggio

>[!tip] Regole Sintattiche
>Con le parole appartenenti al linguaggio possiamo definire sequenze di parole, dette _frasi_.
>Queste regole ci dicono quali sono le frasi grammaticalmente corrette

>[!tip] Regole Semantiche
>Solo alcune delle frasi grammaticalmente corrette del lunguaggio sono anche _valide_, _hanno significato_. 
>La semantica definisce quali frasi corrette sono anche valide e si occupa dell'interpretazione di tali frasi

### Alfabeto
>[!info] Definizione
>L'alfabeto di un linguaggio è l'unità minima di informazione che permette di definire costanti, variabili, operatori, parole chiave ed espressioni che formano il codice sorgente

- Lo standard [[Definizioni_Programmazione#ISO|ISO]] richiede che l'alfabeto del linguaggio C comprenda
	- Un alfabeto **Base** per il codice sorgente, il _source character set_
	- Un alfabeto per il codice eseguibile, _execution character set_
	- **Trigraphs**, sequenze di tre caratteri trattate come un unico carattere

#### Alfabeto Base
>[!tldr]
>Tutti gli standard [[Definizioni_Programmazione#ISO|ISO]] richiedono che l'alfabeto base del linguaggio C comprenda almeno i seguenti 96 simboli:

###### 26 Caratteri minuscoli 

```
a    b    c    d    e    f    g   h   i   j   k   l   m
n    o    p    q    r    s    t   u   v   w   x   y   z
```

###### 26 Caratteri maiuscoli

```
A    B    C    D    E    F    G   H   I   J   K   L   M
N    O    P    Q    R    S    T   U   V   W   X   Y   Z
```

###### 10 Cifre Decimali
```
0    1    2    3    4    5    6   7   8   9   0
```

###### 29 Caratteri Grafici
```
!    "    #    %    &    '    (   )   *   +   ,   -   .   /   :
;    <    =    >    ?    [    \   ]   ^   _   {   |   }   ~
```

###### Spaziature
- 5 Caratteri di spaziatura
```
newline(\n)    horizontal tab(\t)    space( )
form feed(\f)    vertical tab(\v)
```
##### Trigraph
I trigraph sono sequenze di tre caratteri trattate come singolo carattere che permettono di editare simboli non supportati dallo standard ISO/IEC 646:

| carattere | Trigraph |
|:---------:|:--------:|
|     #     |   ??=    |
|    \\     |   ??/    |
|     ^     |   ??'    |
|    \[     |   ??(    |
|    \]     |   ??)    |
|    \|     |   ??!    |
|    \{     |   ??<    |
|    \}     |   ??>    |
|     ~     |   ??-    |
###### Esempio
```c
??=inclued <stdio.h>
/* Print Hello, World! on the terminal*/
int main() ??<
	printf("Hello, World! ??/n");
	return 0;
??>
```

### Regole Lessicali
>[!tldr]
>Set di regole per poter definire parole sull'alfabeto del linguaggio
>>[!done] Breve
>>Le parole valide nel linguaggio possono essere utilizzate per la definizione di programmi

- In C possiamo definire le seguenti principali categorie lessicali:
	1. Parole chiave, o _keywords_
	2. Identificatori
	3. Costanti Letterali
	4. Stringhe Letterali
	5. Commenti
	6. Segni di punteggiatura e operatori
#### Keywords
>[!example] Definizione
>Il linguaggio C contiene una serie di parole, _keywords_, che non possono essere utilizzazte come identificatori di variabili o funzioni.
- Lo standard [[Definizioni_Programmazione#ISO|ISO]] C89 ha definito il seguente set di 32 parole chiave:
```
auto      break     case      char
const     continue  default   do
double    else      enum      extern
float     for       goto      if
int       long      register  return
short     signed    sizeof    static
struct    switch    typedef   union
unsigned  void      volatile  while
```
- Nello standard successivo ISO C99 sono state aggiunte le seguenti parole chiave:
```
inline    restrict  _Bool     _Complex _Immaginary
```
#### Identificatore
>[!example] Definizione
>Un identificatore è una parola composta da una sequenza di caratteri:

![[#26 Caratteri minuscoli]]
![[#26 Caratteri maiuscoli]]
![[#10 Cifre Decimali]]
E uno fra i caratteri grafici:
> `-`

##### Regole
Ci sono diverse regole per la creazione di identificatori:
1. Il primo carattere di un identificatore non può essere una cifra
2. Una parola chiave non può essere identificatore
3. Gli identificatori sono _case-sensitive_
	1. `hello != Hello`
4. Non ci sono limiti specifici sulla massima lunghezza di un identificatore

##### Utilizzo
Un identificatore può essere usato per denotare:
1. Un nome di una variabile o funzione
2. Un membro o _tag_ di una struct, union, enum
3. Un nome di tipo, definito con il _typedef_
4. Un nome di macro o parametro di una macro
