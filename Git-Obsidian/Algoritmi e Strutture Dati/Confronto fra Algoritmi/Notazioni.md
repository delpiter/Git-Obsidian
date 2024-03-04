## O Grande
---
Concetto simile a quello di [[Resto di Peano|o piccolo]] in matematica
La dimensione del [[Complessità di Algoritmi#Tempo di Esecuzione|problema]] per $\text{Example 1}$ è il numero di interi in input
- Una istanza con $100000$ interi è più grande di una con $1000$
- E' ovvio che il tempo di esecuzione cresce con la dimensione dell'istanza

>[!question] Quanto?

Non interessa il numero esatto di istruzioni, si considera solo il **termine dominante**
- Così si ottiene una approssimazione di $T(n)$

Interessa l'andamento della funzione andando verso ***valori sempre più grandi***
- Come per i limiti di funzione, per la complessità di un algoritmo si **seleziona il termine dominante**
- Anche i *coefficienti* diventano non significativi per $n$ molto grandi

L'**ordine di grandezza** di $T(n)$ dipende solo dal termine che cresce di più al crescere di $n$
- Ordine di grandezza si scrive ***O grande***
$f(x) = x^3+6x^2+9x+10$
$$O(f(x)) = O(x^3)$$
Un algoritmo $O(n^3)$ non può essere usato per istanze molto grandi, mentre un algoritmo $O(n)$ è utilizzabile per istanze di dati molto grandi
#### Crescita delle Funzioni
>[!info] Definizione
>La notazione $O-Grande$ caratterizza un limite superiore nel comportamento asintotico di una funzione
>>[!done] In altre parole
>>Questa notazione dice che una funzione cresce non più di un certo ritmo, basato sul termine di grado massimo.

>[!info]
>La crescita delle funzioni può essere descritta con la notazione ***O Grande***
>>[!tip] Definizione
>>Siano $f$ e $g$ due funzioni da $\mathbb{R}$ a $\mathbb{R}$
>>Diciamo che $f(x)$ è $O(g(x))$ se esistono due costanti $C$ e $K$ tali per cui 
>>$$f(x)\leq C\cdot g(x)$$ quando $x>k$
>
>Quando si analizza la crescita di **funzioni di complessità**, $f(x), g(x)$ si assumono sempre positive
>Quando si vuole dimostrare che $f(x)$ è $O(g(x))$, è sufficiente trovare una coppia $(C,K)$ per cui vale la relazione.
>- Notare che ce ne possono essere infinite

##### Esempio
>Dimostrare che $f(x)=x^2+2x+1$ è $O(x^2)$

Per $x>1$ abbiamo:
$$
x^2+2x+1 \leq 2x^2+ x^2 \implies x^2 +2x+1 \leq4x^2
$$
- Quindi per $C=4$ e $K=1:f(x)\leq Cx^2$ quando $x>k$
- $f(x)$ è $O(x^2)$

