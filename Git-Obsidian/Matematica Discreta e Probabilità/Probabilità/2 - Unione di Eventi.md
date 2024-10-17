>Siano $A_{1},A_{2},\dots,A_{n}$ degli eventi

>[!question] Qual è la probabilità: $\mathcal{P}(A_{1}\cup A_{2}\cup\dots\cup A_{n})$?

## Complementare
---
>[!attention] Ricordando che
>$(A_{1}\cup A_{2}\cup\dots\cup A_{n})^c=A_{1}^c\cap A_{2}^c\cap\dots\cap A_{n}^c$

$$
\mathcal{P}(A_{1}\cup A_{2}\cup\dots\cup A_{n})=1-\mathcal{P}(A_{1}^c\cap A_{2}^c\cap\dots\cap A_{n}^c)
$$

#### Esempio
>[!question] Qual è la probabilità di ottenere un sei lanciando due dadi?

- $E_{1}=$"Il primo dado da $6$" $\implies(6,1),(6,2),(6,3),\dots$
- $E_{2}=$"Il secondo dado da $6$" $\implies(1,6),(2,6),(3,6),\dots$

$$
\mathcal{P}(E_{1}\cup E_{2})=1-\mathcal{P}(E_{1}^c\cap E_{2}^c)=1-\frac{25}{36}=\frac{11}{36}
$$
Dove:
- $E_{1}^c$ e $E_{2}^c$ sono gli *eventi* in cui non esce 6 ne nel primo dado ne nel secondo dado
	- Posso scegliere il primo numero in $5$ modi e il secondo dado il $5$ modi:
	- I casi possibili sono $6\cdot6$


## Principio di Inclusione Esclusione
---
> In alternativa è possibile utilizzare il principio di inclusione-esclusione


>[!note] [[2 - Principio di inclusione-esclusione]]
>$$\mathcal{P}(E_{1}\cup E_{2})=\mathcal{P}(E_{1})+\mathcal{P}(E_{2})-\mathcal{P}(E_{1}\cap E_{2})$$


- $\displaystyle= \frac{1}{6}+\frac{1}{6}-\frac{1}{36}=\frac{11}{36}$

## Probabilità Condizionata
---
>[!info] Definizione
>Fissato $A$, un *evento che accade*:

