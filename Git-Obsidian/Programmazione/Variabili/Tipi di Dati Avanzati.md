![[Definizioni_Programmazione#Classificazione dei Tipi di Dati in C]] 
Il Tipo `enum`
---
>[!info] Definizione
>Il tipo **enumerativo** è un tipo di dato che consiste in un insieme ristretto di valori
>La caratteristica principale dei tipi enumerativi è che **ogni elemento** appartenente al tipo ha un **proprio nome**

- I nomi associati agli elementi del tipo sono trattati come **valori costanti**
	- Chiamati *costanti enumerative*

>[!done] Quando usarlo
>In C le **enumerazioni** hanno come unica funzione quella di rendere più leggibile il codice (*syntactic sugar*): possiamo simulare le costanti enumerative con le **macro**.

### Dichiarazione
>[!tldr]
>Per poter dichiarare un tipo di dato *enumerativo* facciamo uso della parola chiave `enum` seguita da una lista di costanti enumerative (**identificatori**).

```c
enum Tag{
	Name1 = constExpr1, //Assignement is Optional
	Name2 = constExpr2,
	...
	NameN = ConstExprN
};
```

- Per convenzione gli identificatori delle costanti enumerative sono in **maiuscolo**
- Il nome del tipo enumerativo (il `tag`) è opzionale

```c
#include<stdio.h>

enum bool {FALSE, TRUE};
```

>[!warning]
>Ogni costante enumerativa può assumere **solo** valori di tipo intero

- Se non specificato, di *default* il primo elemento nella lista ha valore $0$
- Gli elementi successivi sono associati con il **valore dell'elemento precedente** incrementato di $1$

```c
enum days {
	MON = -6 , // -6
	TUE , // -5
	WED , // -4
	THU , // -3
	FRI , // -2
	SAT , // -1
	SUN // 0
};
```

- È possibile avere costanti enumerative con lo **stesso valore** (Poco elegante e sconsigliato)
- Ogni **assegnamento esplicito** viene utilizzato come punto di partenza per gli assegnamenti successivi.
>[!bug] Errore comune
>Gli identificatori in una lista di enumerazioni devono essere **distinti** da altri identificatori di enumerazioni nello **stesso scope**, anche se assumono lo stesso valore.

>[!tldr] Definizione e Dichiarazione
>La **dichiarazione di un tipo** `enum` *dichiara* un nuovo tipo di dato, non riserva la memoria.
>Una **dichiarazione di variabile** di tipo `enum`, riserva memoria e deve essere preceduta, come di consueto, dal nome del tipo enumerativo

```c
enum bool { FALSE , TRUE }; /* definizione */

enum bool flag ; /* dichiarazione */
```
- Il tipo della variabile `flag` è `enum bool`
### Operazioni con `enum`
In C, le variabili di tipo `enum` sono effettivamente variabili di **tipo intero**.
- Possiamo quindi assegnare ad una variabile di tipo `enum` qualsiasi valore di tipo intero, non solo quelli **specificati nella enumerazione**

```c
enum bool { FALSE , TRUE } flag1 = 10 , flag2 = -1;
```

- Possiamo utilizzare le variabili di tipo `enum` con tutti gli operatori applicabili con i tipi di dato interi.
```c
enum bool { FALSE , TRUE } flag1 , flag2 , flag3;
flag1 = FALSE +1; // 1
flag2 = flag1 * TRUE + 10; // 11
flag3 = flag1 / flag2 ; // 0 ( int divison )
```

## Il Tipo `struct`
## Il Tipo `union`