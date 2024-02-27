# `26/02/2024
## Crescita delle funzioni

```functionplot
---
title: Crescita Funzioni
xLabel: 
yLabel: 
bounds: [0,10,0,50]
disableZoom: true
grid: true
---
f(x)=2^x
g(x)=x^3
q(x)=x^2
t(x)=x*log(x)
y(x)=x
j(x)=log(x)
```
### Ordini di Grandezza
- $O(1)$
- $O(log(n))$
- $O(n)$
- $O(n\cdot log(n))$
- $O(n^k)$
- $O(C^n)$
- $O(n^n),O(n!)$

- un problema con una soluzione algoritmica di complessità polinomiale si dice **trattabile**
- Complessità maggiore **intrattabile**
- Non si conosce algoritmo che risolva **insolubile**

### $\Omega$ grande

>[!info]
>L'opposto della notazione $O$ Grande
>>[!tip] Definizione
>>Siano $f$ e $g$ due funzioni da $\mathbb{R}$ a $\mathbb{R}$
>>Diciamo che $f(x)$ è $\Omega(g(x))$ se esistono due costanti $c_{1}$ e $n_{0}$ tali per cui 
>>$$f(x)\geq c_{1}\cdot g(x)$$ quando $x>n_{0}$
>

### $\Theta$ Grande

>[!info] teta grande
>Approssimazione stretta sia o grande che omega grande
>>[!tip] Definizione
>>Siano $f$ e $g$ due funzioni da $\mathbb{R}$ a $\mathbb{R}$
>>Diciamo che $f(x)$ è $\Theta(g(x))$ se esistono tre costanti $c_{1},c_{2},n_{0}$ tali per cui 
>>$$c_{1}g(n)\leq f(n)\leq c_{2}g(n)$$ quando $n \geq n_{0}$

## Analisi asintotica
Obbiettivo
- Semplificare l'analisi del consumo di risorse di un algoritmo prescindendo dai dettagli implementativi o di altro genere
- Classificare gli algoritmi in base al loro comportamento asintotico

## Algoritmi Ricorsivi
```pseudo
	\begin{algorithm}
	\caption{Binary Search}
	\begin{algorithmic}
	\Procedure{BinarySearch}{$val,v[],i,j  $}
\If{$ i>j  $}
  \Return $ -1 $
  \Else 
 \State $ m=(i+j)/2 $
 \If{$ v[m]==val  $}
 \Return $ m $
 \Else 
 \If{$ v[m]>val  $}
  \Return \Call{BinarySearch}{$val,v,i,m-1$}
  \Else 
 \Return \Call{BinarySearch}{$val,v,m+1,j$}
 \EndIf  
 \EndIf
 \EndIf
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```
