## Operazioni sui Puntatori

È possibile eseguire diverse operazioni sulle variabili di tipo [[Introduzione Puntatori|puntatore]].
- Operazioni *ammesse*:
	- **Assegnamento** tra puntatori e con tipi interi
	- **Addizione e sottrazione** tra puntatori e tipi numerici interi
	- **Sottrazione** tra due puntatori
	- **Confronto relazionale** tra puntatori e con tipi di dato interi
- Operazioni *non ammesse*:
	- Assegnamento con tipi in virgola mobile
	- Addizione e sottrazione tra puntatori e tipi numerici in virgola mobile
	- Addizione fra due puntatori e sottrazione tra puntatori di tipo differente
	- Confronto relazionale con tipi in virgola mobile
	- Le altre operazioni aritmetiche
	- Operazioni `bitwise`

### Assegnamento
- Operazioni valide
```c
void *p = 0;
int *q = p;
int *r = q;
void *s = r;
```
- Operazioni Non valide
```c
void *p = 1.2; //Syntax Error
int *q = 1.2; //Syntax Error
float *r = 1.2; //Syntax Error
```
- Operazioni *non sicure*
```c
int *p = -10; // Warning
int *q = 100; // Warning
float *r = q; // Warning
```