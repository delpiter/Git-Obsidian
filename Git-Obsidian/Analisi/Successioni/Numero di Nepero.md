## Numero di Nepero
- - -
>[!info] Dimostrazione
>Sia $f(n)_{n\in\mathbb{N}}=\left( 1+ \displaystyle{\frac{1}{n}} \right)^n$
>Dimostro che $f_{n}\nearrow$
>Devo mostrare che:
>$$
\displaystyle{\frac{f(n+1)}{f(n)}}\geq_{1}, \forall n\in\mathbb{N} \setminus\{0\}
>$$

$$
\begin{array}
\ \displaystyle{\frac{\left( 1+ \displaystyle{\frac{1}{n+1}} \right)^{n+1}}{\left(1+ \displaystyle{\frac{1}{n}}\right)^n}}=\left( \displaystyle{\frac{n+2}{n+1}} \right)^{n+1}\cdot\left( \displaystyle{\frac{n}{n+1}} \right)^n= \\
=\left( \displaystyle{\frac{n+2}{n+1}} \right)^{n+1}\cdot\left( \displaystyle{\frac{n}{n+1}} \right)^{n+1}\cdot\left( \displaystyle{\frac{n+1}{n}} \right)= \\
=\left( \displaystyle{\frac{n^2+n}{(n+1)^2}} \right)^{n+1}\cdot\left( \displaystyle{\frac{n+1}{n}} \right)= \\
=\left( \displaystyle{\frac{(n+1)^2-1}{(n+1)^2}} \right)^{n+1}\cdot\left( \displaystyle{\frac{n+1}{n}} \right)=
\end{array}
$$
- Applicazione della [[Tipologie di Dimostrazioni#Disuguaglianza di Bernoulli|disugualianza di Bernoulli]]
$$
\begin{array} \\
\text{prendo come "x" }-\displaystyle{\frac{1}{(n+1)^2}} \\
\ \left( 1-\displaystyle{\frac{1}{(n+1)^2}} \right)\cdot\left( \displaystyle{\frac{n+1}{n}} \right)\underbrace\geq_{\text{Bernoulli}}\left(1- \displaystyle{\frac{(n+1)}{(n+1)^2}} \right)\cdot\left( \displaystyle{\frac{n+1}{n}} \right)\\
\left( \displaystyle{\frac{n}{n+1}} \right)\cdot\left( \displaystyle{\frac{n+1}{n}} \right)=1
\end{array}
$$
>[!info] Continuazione
>Sia $h_{m}=\left( 1+\displaystyle{\frac{1}{n}} \right)^{n+1}$
>È possibile dimostrare in modo simile che $h_{m}\searrow$
### Osservazione
- $h_{m}=\left( 1+\displaystyle{\frac{1}{n}} \right)^n\cdot\left( 1+\displaystyle{\frac{1}{n}} \right)=f_{n}\cdot\left( 1+\displaystyle{\frac{1}{n}} \right)\geq f_{n}$
- Quindi $f_{n}\geq h_{n}$
$$
2=f_{1}\leq f_{n}\leq h_{n} \leq h_{1}=4, \forall n\in\mathbb{N}\setminus\{0\}
$$
### Conclusione
- $f_{n}$  e $h_{n}$ sono regolari e limitate, quindi sono convergenti.
- Inoltre, poichè $h_{m}=f_{n}\left( 1+ \displaystyle{\frac{1}{n}} \right)$
	- Si ha $\lim\limits_{n\to+\infty}h_{m}=\lim\limits_{n\to+\infty}f_{n}$
- E per il [[Limiti di Successioni#Teorema del Confronto|teorema del confronto]] tale valore è compreso tra $2$ e $4$
$$
e:=\lim\limits_{n\to+\infty}\left( 1+\displaystyle{\frac{1}{n}} \right)^n
$$