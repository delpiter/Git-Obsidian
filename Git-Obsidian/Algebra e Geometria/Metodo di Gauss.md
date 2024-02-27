## Metodo di Gauss
---
>[!tip] Vediamo un esempio

$$
\begin{matrix}
1^a \\
2^a \\
3^a \\
4^a
\end{matrix}
\begin{cases}
2x_{1}-x_{2}+x_{3}+2x_{4}=1 \\
4x_{1}-x_{2}-3x_{3}-x_{4}=-1 \\
-2x_{1}-x_{2}+x_{3}+x_{4} = 1 \\
x_{1}+x_{2}+x_{3}+x_{4} = 2
\end{cases}
$$
>[!example] Primo Step

*Non tocco la prima equazione*
Sommo a ciascuna equazione, dalla $2^a$ in poi, un *multiplo* dilla $1^a$ equazione
- In modo tale che il *coefficiente* di $x_{1}$ **si annulli**

$$
\begin{matrix}
1^a \\
2^a-2\cdot1^a \\
3^a+ 1^a \\
4^a-\frac{1}{2}\cdot 1^a
\end{matrix}
\begin{cases}
2x_{1}-x_{2}+x_{3}+2x_{4}=1 \\
0x_{1}+x_{2}-5x_{3}-5x_{4}=-3 \\
0x_{1}-2x_{2}+2x_{3}+3x_{4} = 2 \\
0x_{1}+\frac{3}{2}x_{2}+\frac{1}{2}x_{3}+0x_{4} = 2
\end{cases}
$$
>[!example] Secondo Step

*Non tocco più la prima e la seconda equazione*.
Sommo a ciascuna equazione, dalla $3^a$ in poi, un *multiplo* dilla $2^a$ equazione
- In modo tale che il *coefficiente* di $x_{2}$ **si annulli**
$$
\begin{matrix}
1^a \\
2^a \\
3^a+2\cdot2^a \\
4^a-\frac{3}{2}2^a
\end{matrix}
\begin{cases}
2x_{1}-x_{2}+x_{3}+2x_{4}=1 \\
0x_{1}+x_{2}-5x_{3}-5x_{4}=-3 \\
0x_{1}-0x_{2}-8x_{3}-7x_{4} = -4 \\
0x_{1}+0x_{2}+8x_{3}+\frac{15}{2}x_{4} = 6
\end{cases}
$$
>[!example] Terzo Step

*Non tocco più la prima, la seconda e la terza equazione*.
Sommo a ciascuna equazione, dalla $4^a$ in poi, un *multiplo* dilla $3^a$ equazione
- In modo tale che il *coefficiente* di $x_{3}$ **si annulli**
$$
\begin{matrix}
1^a \\
2^a \\
3^a \\
4^a+3^a
\end{matrix}
\begin{cases}
2x_{1}-x_{2}+x_{3}+2x_{4}=1 \\
0x_{1}+x_{2}-5x_{3}-5x_{4}=-3 \\
0x_{1}-0x_{2}-8x_{3}-7x_{4} = -4 \\
0x_{1}+0x_{2}+0x_{3}+\frac{1}{2}x_{4} = 2
\end{cases}
$$

>[!done] Step Finale

Ora partendo dall'ultima equazione e salendo troviamo:
$$
\begin{cases}
\frac{1}{2}x_{4} = 2 \implies x_{4}=4 \\
8x_{3}=-4+7x_{4}=-24 \implies x_{3}=-3 \\
x_{2} = 5x_{3}+5x_{4}-3=2 \\
2x_{1} = 1+x_{2}-x_{3}-2x_{4} = -2 \implies x_{1}=-1
\end{cases}
$$
### $\infty$ soluzioni
>Quando ci sono $\infty$ soluzioni, il metodo di gauss mi aiuta a esprimerle in [[Forme Parametriche e Cartesiane#Forme per Descrivere un Sottospazio Vettoriale|forma parametrica]]
#### Esempio
$$
\begin{cases}
x_{1}+x_{2}-3x_{3}+2x_{4}+13x_{5}-8x_{6}=0 \\
0x_{1}+0x_{2}-x_{3}+2x_{4}+x_{5}+x_{6} =0 \\
0x_{1}+0x_{2}+x_{3}-2x_{4}+2x_{5}+11x_{6}=0 \\
0x_{1}+0x_{2}+0x_{3}+0x_{4}+x_{5}+x_{6} =0 \\
0x_{1}+0x_{2}+0x_{3}+0x_{4}-3x_{5}+x_{6}=0 \\
0x_{1}+0x_{2}+0x_{3}+0x_{4}+0x_{5}+7x_{6} =0
\end{cases}
$$

$$
\begin{cases}
x_{1}+x_{2}-3x_{3}+2x_{4}+13x_{5}-8x_{6}=0 \implies x_{1}=s-4t\\
0x_{1}+0x_{2}\cancel{ -x_{3} }+\cancel{ 2x_{4} }+x_{5}+x_{6} =0 x_{2}=s\in\mathbb{R}\\
0x_{1}+0x_{2}+x_{3}-2x_{4}+2x_{5}+11x_{6}=0 \implies x_{3}-2t =0 \implies x_{3}=2t\\
0x_{1}+0x_{2}+0x_{3}+0x_{4}+x_{5}+x_{6} =0 \implies x_{4} = t\in\mathbb{R}\\
0x_{1}+0x_{2}+0x_{3}+0x_{4}-3x_{5}+x_{6}=0 \implies x_{5}=0\\
0x_{1}+0x_{2}+0x_{3}+0x_{4}+0x_{5}+7x_{6} =0 \implies x_{6}=0
\end{cases}
$$
L'insieme delle soluzioni è:
$$
\{ (4t-s,s,2t,t,0,0 ), t,s \in\mathbb{R}\}
$$
