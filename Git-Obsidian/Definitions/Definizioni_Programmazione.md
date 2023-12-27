## ISO
---
>[!info] Descrizione
>La **International Organization for Standardization** è la più importante organizzazione a livello mondiale per la definizione di norme tecniche

## Precedenze e Associatività
---
| operatore              | Descrizione                             | Esempio            | Associatività | Precedenza |
| ---------------------- | --------------------------------------- | ------------------ | ------------- | ---------- |
| `++    --`             | Post incremento/decremento              | `x++` `x--`        | $\implies$    | 1          |
| `( )`                  | Chiamata a funzione                     | `x(y)`             | $\implies$    | 1          |
| `[ ]`                  | Elemento di un Array                    | `x[y]`             | $\implies$    | 1          |
| `.`                    | Membro di struttura o union             | `x.y`              | $\implies$    | 1          |
| `->`                   | Puntatore a membro di struttura         | `x->y`             | $\implies$    | 1          |
| `!`                    | Not Logico                              | `!x`               | $\impliedby$  | 2          |
| `~`                    | Complemento ad Uno                      | `~x`               | $\impliedby$  | 2          |
| `++   --`              | Pre incremento/decremento               | `++x  --x`         | $\impliedby$  | 2          |
| `+   -`                | Operatori unari di Segno                | `+x  -x`           | $\impliedby$  | 2          |
| `&`                    | Operatore di Indirizzo                  | `&x`               | $\impliedby$  | 2          |
| `*`                    | Operazione di Dereferenziazione         | `*x`               | $\impliedby$  | 2          |
| `(type)`               | Operatore di conversione di Tipo (Cast) | `(int)x`           | $\impliedby$  | 2          |
| `sizeof`               | Dimensione in Byte                      | `sizeof(x)`        | $\impliedby$  | 2          |
| `*`                    | Moltiplicazione                         | `x * y`            | $\implies$    | 3          |
| `/`                    | Divisione                               | `x / y`            | $\implies$    | 3          |
| `%`                    | Resto della Divisione Intera            | `x % y`            | $\implies$    | 3          |
| `+`                    | Somma                                   | `x + y`            | $\implies$    | 4          |
| `-`                    | Differenza                              | `x - y`            | $\implies$    | 4          |
| `<<`                   | Left Shift                              | `x << y`           | $\implies$    | 5          |
| `>>`                   | Right Shift                             | `x >> y`           | $\implies$    | 5          |
| `<`                    | Minore                                  | `x < y`            | $\implies$    | 6          |
| `<=`                   | Minore Uguale                           | `x <= y`           | $\implies$    | 6          |
| `>`                    | Maggiore                                | `x > y`            | $\implies$    | 6          |
| `>=`                   | Maggiore Uguale                         | `x >= y`           | $\implies$    | 6          |
| `==`                   | Ugualianza                              | `x == y`           | $\implies$    | 7          |
| `!=`                   | Non Ugualianza                          | `x != y`           | $\implies$    | 7          |
| `&`                    | _Bitwise_  AND                          | `x & y`            | $\implies$    | 8          |
| `^`                    | _Bitwise_  XOR                          | `x ^ y`            | $\implies$    | 9          |
| \|                    | _Bitwise_  OR                           | `x` \| `y`            | $\implies$    | 10         |
| `&&`                   | AND Logico                              | `x && y`           | $\implies$    | 11         |
| \|\|                   | OR Logico                               | `x` \|\| `y`            | $\implies$    | 12         |
| `? :`                  | Operatore Condizionale                  | `x ? y : z`        | $\impliedby$  | 13         |
| `=`                    | Assegnamento                            | `x = y`            | $\impliedby$  | 14         |
| `*=  /=  %=  +=  -=`   | Assegnamenti Composti                   | `x <op>= y` | $\impliedby$  | 14         |
| `<<=  <<=  &=  \|=  ^=` | Assegnamenti Composti                   | `x <op>= y` | $\impliedby$  | 14         |
| `,`                    | Operatore di Concatenazione             | `x, y`             | $\implies$    | 15           |