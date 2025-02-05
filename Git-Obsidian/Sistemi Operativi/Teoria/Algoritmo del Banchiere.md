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
