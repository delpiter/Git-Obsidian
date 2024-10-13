---
## Avvio del sistema operativo
---
Tutte le volte che un processo entra nel sistema, viene inserito in una delle code gestite dallo scheduler![[Code dei Processi.png]]

![[Screenshot 2024-10-13 172559.png]]

#### Gerarchia dei Processi
>[!info] Gerarchia
>I processi sono organizzati in una struttura gerarchica
>- Quando un processo crea un nuovo processo, il processo creante viene detto *padre* e il creato *figlio*
>>[!done] Si viene a creare una struttura ad albero di processi


![[Screenshot 2024-10-13 172825.png]]

### Processi e Thread
Tutti i sistemi operativi supportano l'esistenza di processi multithread
- In un processo multithread esistono molte *linee di controllo* ognuna delle quali può eseguire un diverso insieme di istruzioni

#### Thread
Un thread è lunità di base di utilizzazione della cpu
- Ogni thread possiede:
	- La copia dello stato del processore
	- Il program counter
	- Uno stack

I thread appartenenti allo stesso processo condividono
- Codice, dati e risorse `I/O`
![[Threads.png]]

>[!example] Condivisione di Risorse
>I Thread condividono lo spazio di memoria e le risorse allocate degli altri thread dello stesso processo

>[!done] Thread: Pro
>Creare Thread all'interno di un processo e il context switching fra thread è meno costoso rispetto a creare un processo nuovo / Context switching fra processi

Utilizzare i thread al posto dei processi rende l'implementazione più efficiente


Implementazione:
- User Thread(livello utente)
- Kernel Thread (livello kernel)

Gli user thread vengono supportati sopra il kernel, implementati da una libreria a livello utente
- La lib fornisce supporto per la creazione, scheduling e gestione dei thread senza l'intervento del kernel

Kernel Thread, Supportati dal sistema operativo
- Creazione, scheduling e gestione sono implementati a livello kernel

Tre modelli di multithreading
- Many to one
	- Un numero di user thread vengono mappati su un solo kernel thread
		- Sistemi operativi che non supportano kernel thread multipli (nessuno)
- One to One
	- Ogni user thread viene mappato su un kernel thread
		- Problemi di scalabilità
- Many to Many
	- Più thread kernel a cui associare più thread livello user


![[Many-to-One.png]]

![[One-to-One.png]]

![[Many-to-Many.png]]

### Processi in Linux
Creazione di processi: pid = fork() -> Creazione del processo figlio da un processo padre (<0 errore, =0 processo figlio >0 processo padre)
- wait() (processo padre) -> il proc padre aspetta la fine dell'esecuzione del proc figlio
- exec() -> esegue il processo figlio
- exit() -> chiude il processo figlio

```c
int value = 5;

int main()
{
	pid_t pid;
	pid = fork(); // Returns 0 to the child process and the PID of the child to the parent process
	if(pid == 0)
	{/*if child process*/
		value += 15;
		printf("Child: value = %d\n",value);// value = 20
		return 0;
	}
	else if (pid > 0)
	{/*if parent process*/
		wait(NULL);
		printf("Parent : value = %d\n", value); // Value = 5
		return 0;
	}
}
```

Passaggio di valori tra processi: pipe

La funzione pipe() crea una pipe unidirezionale di comunicazione che può essere utilizzata per il passaggio di dati fra processi
- La funzione chiede come argomento un array di 2 posizioni
	- array[0] -> estremità di lettura della pipe
	- array[1] -> estremità di scrittura della pipe
