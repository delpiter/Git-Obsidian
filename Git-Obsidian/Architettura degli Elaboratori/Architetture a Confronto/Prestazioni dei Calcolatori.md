## Tempo di Esecuzione
---
>[!abstract] Elementi
>Gli elementi che consentono di calcolare il ***tempo di esecuzione*** sono:
>>[!info] Periodo di Clock
>>$T_{clock}$
>>Dipende dalla ***tecnologia*** e dalla ***organizzazione*** del sistema
>
>>[!caution] Numero di clock per istruzione
>>$CPI_{i}$
>>Indica il numero di clock occorrenti affinché venga eseguita l'istruzione di tipo $i$
>>- Istruzione ***Semplice*** $\to CPI$ ***ridotto***
>>- Istruzione ***Complessa*** $\to CPI$ ***elevato***
>
>>[!info] Numero di istruzioni $i$
>>$N_{i}$
>>Indica il numero di istruzioni di tipo $i$
>
>>[!done] Formula
>>$$T_{esecuzione}=T_{clock}\cdot\left( \sum_{i=1}^n N_{i}\cdot CPI_{i} \right) $$

### IPS
>[!info] Instruction Per Second
>L'$IPS$ è una misura che serve per ***valutare le prestazioni*** di un sistema
>Indica quante istruzioni vengono ***eseguite al secondo***
>Al giorno d'oggi viene riportata come $MIPS$ (***M***illion ***IPS***)
>$$MIPS=\frac{\text{Frequenza del Clock}}{10^6\cdot CPI}$$

Questa misura è affetta da una ***forte approssimazione***
- Non tiene conto delle possibilità offerte dal ***set di istruzioni***
	- Più il set di istruzioni di una certa macchina è ***potente*** tanto più è possibile ***ridurre la lunghezza*** dei programmi eseguiti
- Non tiene conto delle ***percentuali delle diverse istruzioni*** all'interno di programmi reali
	- Una macchina più veloce in un programma può essere più lenta in altre
- Non tiene conto dell'ampiezza dei [[BUS dei Calcolatori|BUS]], della presenza di [[Cache]] o altre tecniche che ottimizzano i tempi di esecuzione

### Benchmark
>*Le stime vengono solitamente ottenute attraverso [[Definizioni_Architettura#Benchmarck|Benchmark]]*

>[!info] Benchmark Dhrystone
>Utilizzato per ottenere stime di $IPS$
>Contiene solamente operazione di aritmetica intera

>[!info] ***Flo***ating Point ***P***er ***S***econd
>`FLOPS`
>È una misura che è significativa se si intende utilizzare un programma dove la maggior parte delle operazioni sono di ***tipo floating point***
>Tipicamente riportata come `MFLOPS`, `GLOPS`