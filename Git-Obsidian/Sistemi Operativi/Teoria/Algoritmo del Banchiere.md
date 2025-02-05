## Introduzione
---

>[!info] 
>Algoritmo per evitare lo ***stallo*** sviluppato da ***Dijkstra***


Il banchiere deve essere in grado di soddisfare tutte le richieste dei clienti
- Concedendo immediatamente il prestito
- Oppure facendo attendere il cliente

### Variabili
>[!summary] Descrizione
>- $N$: Numero di *clienti*
>- $IC$: *Capitale* Iniziale
>- $c_{i}$: ***Limite*** di *credito* del cliente $i$ ($c_{i}<IC$)
>- $p_{i}$: Denaro ***prestato*** al cliente $i$ ($p_{i}\leq c_{i}$)
>- $n_{i}=c_{i}-p_{i}$: Credito ***residuo*** del cliente $i$
>- $SC = IC -\sum_{i=1}^n p_{i}$: ***Saldo*** di cassa

#### Stato Safe
>[!def] Definizione
>Le richieste che ogni cliente $i$ può fare possono essere soddisfatte dalle risorse attualmente disponibili più tutte le risorse detenute dai processi $j$
>>[!done] In Breve:
>>Si calcoli il vettore `avail` come segue
>> - $avail[1]=SC$
>> - $avail[j+1]=avail[j]+p_{s(j)}$ con $j=1,\dots N-1$
>> 
>> Uno stato del sistema si dice safe se vale la seguente condizione:
>> $$n_{s(j)}\leq avail[j], \quad \text{con} j=1, \dots, N$$

#### Stato Unsafe
>[!def] Definizione
>È condizione ***necessaria*** ma ***non sufficiente*** per avere [[Condivisione di Risorse#Deadlock|deadlock]]

## Similitudine con il Sistema Operativo
---
> Il banchiere è il *sistema operativo* che gestisce le risorse

>[!info] Nota bene
>L'algoritmo si basa sull'utilizzo di ***una sola risorsa*** (una unica moneta)
>Il *sistema operativo* deve essere in grado di gestire [[Risorse#Definizioni|più classi]]

>[!warning] Attenzione
>>[!question] Non basterebbe avere più banchieri?
>> ***NO***.
>> Un banchiere deve avere coscienza delle risorse in prestito ad un cliente, o potrebbe causare del [[Condivisione di Risorse#Deadlock|deadlock]]

### Algoritmo del Banchiere Multivaluta
#### Variabili
>[!summary] Descrizione
>- $N$: Numero di *clienti*
>- $IC_{k}$: *Capitale* Iniziale della valuta $k$
>- $c_{i,k}$: ***Limite*** di *credito* in valuta $k$ del cliente $i$ ($c_{i,k}<IC_{k}$)
>- $p_{i,k}$: Denaro ***prestato*** in valuta $k$ al cliente $i$ ($p_{i,k}\leq c_{i,k}$)
>- $n_{i,k}=c_{i,k}-p_{i,k}$: Credito ***residuo*** in valuta $k$ del cliente $i$
>- $SC_{k} = IC_{k} -\sum_{i=1}^n p_{i,K}$: ***Saldo*** di cassa in valuta $k$

- I ragionamenti per controllare stati ***safe*** e ***unsafe*** sono uguali all'algoritmo con *singola valuta*