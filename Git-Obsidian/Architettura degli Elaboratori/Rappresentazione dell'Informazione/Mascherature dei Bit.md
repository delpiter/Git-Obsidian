## Introduzione
---
> Un `BYTE` fornisce un insieme di configurazioni che normalmente vengono utilizzate per codificare dei numeri

Possono tuttavia essere utilizzate per memorizzare **qualsiasi tipo di informazione**

>[!example] Esempio
>Codifica del Firmware di un semaforo a tre luci
>1. `00000001` $\to$ Semaforo **rosso**
>2. `00000010` $\to$ Semaforo **giallo**
>3. `00000100` $\to$ Semaforo **verde**

- In altre parole è possibile associare ad alcuni numeri un particolare significato

>[!info] Maschera di `BIT`
> Chiameremo **Maschera di `BIT`** una qualsiasi configurazione di un insieme di `BIT` di lunghezza predefinita

Le operazioni che possono essere utili da eseguire su una **locazione di memoria** sono:
- `SET` di uno o più `BIT`
- `CHECK` o verifica del valore di uno o più `BIT`

Queste operazioni possono essere eseguite tramite operatori **bitwise**

### AND bit a bit
>[!info] Definizione
>Dati due `BYTE` in input restituisce un `BYTE` in cui un `BIT` è $1$ se e solo se 
>i `BIT` corrispondenti nei due operandi sono posti a $1$
>
>>[!done] Esempio
>>`00110110 AND 01111000 = 00110000`

>[!question] A cosa serve?

Utilizzato per impostare a $0$ uno o più `BIT` di una locazione di memoria
- `AND` bit a bit, **maschera** in cui i `BIT` di interesse sono impostati a $0$ e i `BIT` rimanenti a $1$
#### Esempio
>[!exercise] Dato `x = 0010101` impostare a $0$ il primo e l'ultimo `BIT`


| Operando  | `00110101` |
| --------- | ---------- |
| Maschera  | `01111110` |
| Risultato | `00110100` |

### OR bit a bit
>[!info] Definizione
>Dati due `BYTE` in input restituisce un `BYTE` in cui un `BIT` è $1$ se almeno uno dei 
>`BIT` corrispondenti nei due operandi sono posti a $1$
>
>>[!done] Esempio
>>`00110110 OR 01111000 = 01111110`

Utilizzato per impostare a $1$ uno o più bit di  una locazione di memoria
- `OR` bit a bit, **maschera** in cui i `BIT` di interesse sono impostati a $1$ e i rimanenti a $0$

#### Esempio
>[!exercise] Dato `x=11001010` impostare a $1$ il terzo e il quarto `BIT`

| Operando  | `11001010` |
| --------- | ---------- |
| Maschera  | `00001100` |
| Risultato | `11001110` |
