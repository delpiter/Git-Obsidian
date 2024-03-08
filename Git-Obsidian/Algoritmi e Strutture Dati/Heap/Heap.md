>[!info] Definizione
>Un *Heap* è un [[Gli Alberi#Albero Binario|albero binario]] *quasi completo*
>Quasi, significa che *possono mancare* alcune foglie *consecutive* a partire dall'ultima foglia di destra
>Per ogni nodo deve valere:
>$$value(i)\leq value(parent(i))$$
>>[!tip] Nota 1
>>Il massimo si trova nella radice
>
>>[!tip] Nota 2
>>Non c'è ***nessuna relazione*** tra il *valore di un nodo* e quello di un **suo fratello**

### Heap in un Vettore
>È possibile immaginarsi un heap come una struttura: ***vettore***
![[image-removebg-preview.png]]

Considerando la radice dell'albero come la posizione 1
- Per ogni nodo in posizione $i$
	- $\text{left-child}(i) =$ posizione $2i$
	- $\text{right-child}(i) =$ posizione $2i+1$
- $\text{parent}(i)=\lfloor \frac{i}{2}\rfloor$
### Heapify
>[!info] Definizione
>***Heapify*** è il processo di creazione di una struttura dati heap 