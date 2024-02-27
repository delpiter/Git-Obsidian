## Introduzione
---
> Molti problemi di calcolo richiedono una gamma di valori **molto vasta** difficilmente esprimibile con le convenzionali tecniche di numerazioni

- La massa del sole $2\times 10^{33}gr.$ richiede un numero a $34$ cifre decimali o $111$ cifre binarie
- La massa dell'elettrone $9\times 10^{-28}gr.$ richiede un numero con $28$ cifre decimali oppure $90$ cifre binarie

Manipolare questi valori per *esteso* è molto scomodo e spesso infattibile e inutile
- Es la massa del sole non è certa dopo le prime 5 cifre significative

## Floating-Point
---
>[!info] Virgola Mobile
>Si adotta quindi una notazioni in cui la **gamma** dei valori esprimibili è indipendente dal numero di **cifre significative**
>Questo sistema è detto ***floating-point***

$$
n=f\times 10^e
$$
- $f\to$ **frazione o mantissa**
- $e \to$ **esponente**

La precisione è determinata dalla mantissa $f$ mentre la gamma di valori è determinata dall'esponente $e$

>[!warning] La notazione floating point consente più rappresentazioni per uno stesso numero

$$
3.14 = 0.314 \times 10^1 = 3.14 \times 10^0
$$
Per questo motivo è stata definita una **codifica *standard*** o *normalizzata* in cui i valori della **mantissa** $f$ sono compresi tra $0.1$ e $1$, ($0.1\leq f < 1$)


I **floating-point** possono essere utilizzati per "simulare" i numeri reali
- I numero di valori rappresentabili sono comunque infinitamente inferiore al numero di numeri reali
![[floatingpoints.png]]

>[!warning] Non tutti i numeri reali appartenenti alle aree rappresentabili possono essere espressi correttamente tramite un numero **floating-point**

A differenza dei numeri **reali**, la densità dei *floating-point* non è infinita
- Quando il risultato non si può esprimere nella rappresentazione numerica usata, viene utilizzato il numero più vicino rappresentabile
- L'errore che si commette è detto **errore di arrotondamento**

$$
E=min(\left| v-v_{1} \right|;\left| v-v_{2} \right|  )
$$
#### Esempio
Con numeri floating point con tre cifre decimali con segno per la mantissa e due cifre decimali con segno per l'esponente non è possibile rappresentare:
$$
\frac{10}{3}= 3.\overline{3}
$$
- In questo caso l'errore di arrotondamento è
$$
3.\overline{3} -0.333 \times10^1=0.000\overline{3}
$$

## IEEE 754: Standard Floating-Point
---
>[!info] Standard
>Lo standard prevede vari formati
>I più utilizzati sono:
>- Formato a **singola precisione**
>- Formato a **doppia precisione**


| Elemento                        | Singola Precisione | Doppia Precisione   |
| ------------------------------- | ------------------ | ------------------- |
| `BIT` di segno                  | $1$                | $1$                 |
| `BIT` per l'esponente           | $8$                | $11$                |
| `BIT` nella parte frazionaria   | $23$               | $52$                |
| Numero totale di `BIT`          | $32$               | $64$                |
| Rappresentazione dell'esponente | Eccesso $127$      | Eccesso $1023$      |
| Campo dell'esponente            | Da $-126$ a $127$  | Da $-1022$ a $1023$ |
|                                 |                    |                     |
