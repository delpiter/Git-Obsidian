## Tipizzazione
---
>[!tldr]
>Il C è un linguaggio **tipizzato**, ovvero richiede che venga associato un tipo ad ogni dato utilizzato nel codice
>>[!done] In Breve
>>La tipizzazione permette al compilatore di:
>>1. Capire come interpretare il contenuto della locazione di memoria
>>2. Verificare che ci sia coerenza nell'uso dei dati.

- Il linguaggio C può essere definito come un linguaggio debolmente tipizzato, in quanto presenta dei meccanismi impliciti ed espliciti per trattare in modo flessibile le regole di _conversione_ di tipi di dati

### Specificatori e Modificatori

#### Specificatori
>[!info] Definizione
>Classi primarie di memorizzazione del linguaggio C

1. `void`: tipo di dato *indefinito*, _non specificato_
2. `char`: rappresenta i caratteri nel set a disposizione sul calcolatore
3. `int`: rappresenta i numeri interi
4. `float`: rappresenta i numeri in virgola mobile, decimali, a _precisione singola_
5. `double`: rappresenta i numeri in virgola mobile a _precisione doppia_

#### Modificatori
>[!info] Definizione
>Modificano il range di valori ammissibili per il tipo

1. `short`: riduce il numero di valori memorizzabili
2. `long`: aumenta il numero di valori memorizzabili
3. `signed`: il tipo di dato è dotato di segno
4. `unsigned`: il tipo di dato non è dotato di segno

| Combinazioni                  | Classe                 | Byte | Min           | Max           |
| ----------------------------- | ---------------------- | ---- | ------------- | ------------- |
| `void`                        | Tipo indefinito        | NULL | NULL          | NULL              |
| `char, signed char`           | Tipo intero            | 1    | $-128$        | $127$         |
| `unsigned char`               | Tipo intero            | 1    | $0$           | $255$         |
| `short int, signed short int` | Tipo intero            | 2    | $-32768$      | $32767$       |
| `unsigned short int`          | Tipo intero            | 2    | $0$           | $65535$       |
| `int, signed int`             | Tipo intero            | 4    | $-2147483648$ | $-2147483647$ |
| `unsigned int`                | Tipo intero            | 4    | $0$           | $4294967295$  |
| `long int, signed long int`   | Tipo intero            | 4/8  | $-2^3$ o $-2^7$              | $2^3-1$ o $2^7-1$              |
| `unsigned long int`           | Tipo intero            | 4/8  | $0$              | $2^4-1$ o $2^8-1$              |
| `float`                       | Tipo in virgola mobile | 4    | $-3.4E 38$              | $3.4E 38$              |
| `double`                      | Tipo in virgola mobile | 8    | $-1.7E308$              | $1.7E308$              |
| `long double`                 | Tipo in virgola mobile | 16   | $3.4E-4932$              | $1.1E+4932$              |

### Overflow
È importante conoscere il range di valori ammissibili per un tipo di dato per evitare problemi di **overflow** durante l'esecuzione

##### Esempio
```c
int main()
{
	short int x ) 4294967295;

	return 0;
}
```
- Non possiamo fare alcun tipo di assunzione sul valore della variabile `x` a riga 4

#### Operatore `sizeof`
>[!tldr]
>L'operatore `sizeof` applicao ad un nome di variabile o tipo, _ritorna_ la dimensione in byte dell'oggetto passato come argomento

##### Esempio
```c
int main()
{
	char x = 'a';
	printf(sizeof(x));//1
}
```