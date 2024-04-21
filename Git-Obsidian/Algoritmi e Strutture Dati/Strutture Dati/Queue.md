## Queues - *Code*
---
>[!info] Descrizione
>>[!tip] Dati
>>I dati sono un insieme $Q$ di *elementi*
>
>>[!example] Operazioni
>>***ENQUEUE***:
>>- *Inserisce* un elemento in $Q$
>>***DEQUEUE***
>>- *Restituisce* l'elemento da **più tempo presente** e lo *rimuove* da $Q$
>
>>[!done] Politica
>>Una ***queue*** ha una politica ***FIFO***
>>- ***F***irst ***I***n ***F***irst ***O***ut

![[Git-Obsidian/Algoritmi e Strutture Dati/Strutture Dati/attatchements/queue.webp]]

### Enqueue

```Java
void Enqueue(Q,x)
{
	Q[Q.tail] = x;
	if(Q.tail == Q.length)
		Q.tail = 1;
	else
		Q.tail = Q.tail + 1;
}
```

### Dequeue

```Java
int Dequeue(Q)
{
	x = Q[Q.head];
	if(Q.head == Q.length)
		Q.head = 1
	else
		Q.head = Q.head +1
}
```