>Esistono un numero di problemi "*classici*" della programmazione concorrente

## Produttori e Consumatori
---
>[!info] Concetto Base
>Esiste un processo "***produttore***": `Producer` che genera valori e vuole trasferirli ad un processo "***consumatore***": `Consumer` che prende i valori generati e li "*consuma*"

#### Proprietà da Garantire
- `Producer` ***non*** deve *scrivere* l'area di memoria condivisa prima che `Consumer` abbia effettivamente *usato* il ***valore precedente***
- `Consumer` ***non*** deve *leggere* due volte lo stesso valore
- Assenza di [[Condivisione di Risorse#Deadlock|deadlock]]

#### Implementazione
```c++ title="Produttore/Consumatore"
shared Object buffer;

Semaphore empty = new Semaphore(1);
Semaphore full = new Semaphore (0);

void Producer(){
	while(true){
		Object val = produce();
		empty.P();
		buffer = val;
		full.V();
	}
}

void Consumer(){
	while(true){
		full.P();
		Object val = buffer;
		empty.V();
		consume(val);
	}
}
```

### Buffer Limitato
---
>[!info] Problema Simile
>Il problema è simile a quello del ***produttore/consumatore***, a differenza che lo scambio ***non*** avviene tramite un *singolo elemento*, ma tramite un ***buffer*** di dimensione limitata

#### Proprietà da Garantire
Le proprietà da garantire sono le [[#Proprietà da Garantire|stesse]] con l'aggiunta:
- Assenza di [[Condivisione di Risorse#Starvation|starvation]]

#### Implementazione
>Si utilizzano due indici `front` e `rear` che indicano rispettivamente il ***prossimo elemento*** da *scrivere*/*leggere*

Gli indici vengono utilizzati in ***modo ciclico***
![[CircularArray.png]]

```c++ title="Produttore/Consumatore"
shared Object buffer[SIZE];

int front = 0;
int rear = 0;

Semaphore empty = new Semaphore(1);
Semaphore full = new Semaphore (0);

void Producer(){
	while(true){
		Object val = produce();
		empty.P();
		buffrearer[front] = val;
		front = (front + 1) % SIZE;
		full.V();
	}
}

void Consumer(){
	while(true){
		full.P();
		Object val = buffer[rear];
		rear = (rear + 1) % SIZE
		empty.V();
		consume(val);
	}
}
```

>[!question] È possibile usare il codice precedente con produttori e ***consumatori multipli***?

>[!done] Si, basta aggiungere un ***semaforo mutex*** che gestisce l'accesso al *buffer*

## Cena dei Filosofi
---
>[!info] Concetti di Base
>Cinque ***filosofi*** passano la lora vita a *mangiare* e a *pensare*
>Per *mangiare* fanno uso di una tavola rotonda con:
>- $5$ sedie
>- $5$ piatti
>- $5$ posate fra i piatti
>
>Per *mangiare* un filosofo ha bisogno di ***2 posate*** (*destra* e *sinistra*)
>Per *pensare* un filosofo lascia le posate dove le ha prese

Questo problema mostra come *gestire situazioni* in cui i processi entrano in ***competizione*** per accedere ad insiemi di risorse a ***intersezione non nulla***

![[PhilosopherDinner.png]]

##### La vita di un Filosofo
```c++ title:Filosofo
void Philo[i]{
	while(true){
		//think
		aquireChopsticks();
		eat();
		releaseChopsticks();
	}
}
```

##### Definizioni
- $up_{i}$ Indica il numero di volte che la bacchetta $i$ viene *presa dal tavolo*
- $down_{i}$ Indica il numero di volte che la bacchetta $i$ viene *rilasciata sul tavolo*

>[!cite] Invariante
>$$down_{i}\leq up_{i} \leq down_{i}+1$$

In pratica:
> La bacchetta può essere vista come [[Semafori#Semafori Binari|semaforo binario]]