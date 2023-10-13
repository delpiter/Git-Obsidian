>[!info] Definizione
>Sia $a\neq 0$ chiamiamo successione in $A$ una qualsiasi funzione
> $$
f: \mathbb{N}\to A
>$$
## Notazione
$$
\underbrace{a_{n}}_{\text{termine n-esimo}} := a(n)
$$
- $n$ anche detto l'indice della successione
##### Es
- $a_{n}=k, \ k\in\mathbb{R}$
![[Pasted image 20231013094149.png]]

- $a_{n}=(-1)^n$
![[Pasted image 20231013095115.png]]

## Successioni infinitesime
- - -
>[!info] Definizione
>Sia $(a_{n})_{n\in\mathbb{N}}$ una successione in $\mathbb{R}$ diciamo che la mia successione è infinitesima (che tende a $0$) per $n \to +\infty$ se
>$$
\forall \mathcal{E} \in \mathbb{R}^+\setminus\{0\}, \exists m_{\mathcal{E}}\in \mathbb{N} : \forall n \geq m_{\mathcal{E}} \text{ si ha } |a_{n}|\leq\mathcal{E}
>$$

![[Pasted image 20231013110411.png]]
### Es
- $a_{n}=\displaystyle{\frac{1}{n}}$
- Verifichiamo che $\lim\limits_{n\to+\infty} \displaystyle{\frac{1}{n}} =0$
###### Infatti
$\forall \mathcal{E} \in \mathbb{R}^+\setminus\{0\}, \exists m_{\mathcal{E}}\in\mathbb{N} : \forall n\geq m_{\mathcal{E}} \text{ si ha } |\displaystyle{\frac{1}{n}}|\leq\mathcal{E}$
$$
\ |\displaystyle{\frac{1}{n}}|\leq\mathcal{E} \Leftrightarrow \displaystyle{\frac{1}{n}}\leq\mathcal{E}\Leftrightarrow n\geq \displaystyle{\frac{1}{\mathcal{E}}}
$$
- Posso scegliere come $m_{\mathcal{E}}=\lfloor \displaystyle{\frac{1}{\mathcal{E}}}\rfloor+1$
