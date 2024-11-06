>Di seguito vedremo come risolvere il problema della concorrenza [[Sezioni Critiche#Approcci|modificando l'hardware]]

>[!tldr] Idea
>Si può pensare di fornire alcune *istruzioni hardware* speciali per semplificare la realizzazione di ***sezioni critiche***
>Nei sistemi uniprocessore, i processi concorrenti vengono "[[Concorrenza#Multiprogramming|alternati]]" tramite il meccanismo degli ***interrupt***

>[!question] Risolve il problema, disabilitare gli interrupt?

Il sistema operativo deve la sciare ai processi la responsabilità di riattivare gli interrupt
>[!danger] Altamente Pericoloso!

Inoltre non funziona su ***sistemi multiprocessore***

###### Pro e Contro
>[!done] Vantaggi

- Concetti applicabili a qualsiasi numero di processi, sia su sistemi mono processore che multiprocessore
- Può essere usato per supportare sezioni ***critiche multiple***

>[!fail] Svantaggi

- Viene utilizzato il ***busy-waiting***
- I problemi di [[Condivisione di Risorse#Starvation|starvation]] ***non*** sono eliminati
- Complessi da programmare
### Test e Set
>[!abstract] Istruzioni Speciali
>Sono istruzioni che realizzano due azioni in modo ***atomico***
>>[!example] Come
>>- Lettura e Scrittura
>>- Test e Scrittura
>
>`TS(x,y):= < y = x; x = 1 >`
>>[!done] A parole
>>Assegna in `y` il valore precedente di `x`, e successivamente assegna `1` ad `x`


##### Esempio di Utilizzo di Test&Set
```pseudo
	\begin{algorithm}
	\begin{algorithmic}
	\State $ \text{shared }lock\  =0 $
	\State $\text{Cobegin } P \ \ Q \text{ Coend}$
	\Procedure{P}{$  $}
\State $ \text{int }vp  $
\While{$true$}
\Repeat
\State \Call{TS}{$ lock,vp $}
\Until{$vp$}
 \State $ \text{Critical Section} $
 \State $ lock = 0 $
 \State $  \text{Non-Critical Section} $
\EndWhile
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

```pseudo
	\begin{algorithm}
	\begin{algorithmic}
\Procedure{Q}{$  $}
\State $ \text{int }vq  $
\While{$true$}
\Repeat
\State \Call{TS}{$ lock,vq $}
\Until{$vq$}
 \State $ \text{Critical Section} $
 \State $ lock = 0 $
 \State $  \text{Non-Critical Section} $
\EndWhile
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

>[!done] Mutua Esclusione
>Entra solo chi riesce a settare per primo il lock

>[!done] No deadlock
>Il primo che esegue `TS` entra senza problemi

>[!done] No Delay non necessari
>Un processo fuori dalla ***critical section*** non blocca gli altri

