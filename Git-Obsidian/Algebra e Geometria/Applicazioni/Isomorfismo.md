## Isomorfismo
---
>[!info] Definizione
>Un ***isomorfismo*** è una [[Introduzione#Funzione o Applicazione|applicazione]] [[Applicazioni Lineari#Applicazione Lineare|lineare]] e [[Git-Obsidian/Analisi/Funzioni/Introduzione Funzioni#Funzione Biunivoca|biunivoca]]

#### Esempio 1
>$f:\mathbb{R}^2\to \mathbb{R}^2, f(x,y)=(x+y,x-y)$

>[!question] $f$ è un isomorfismo?

- $f$ è lineare?

#Da_verificare

$\mathrm{ker}f=\{ \underline{0} \}\implies f$ è iniettiva $\implies f$ è biunivoca
- (Vedi [[Teorema del Rango#Conseguenze del Teorema del Rango|conseguenze del teorema del Rango]])
Quindi $f$ è lineare e biunivoca

>[!done] $f$ è un isomorfismo tra $\mathbb{R}^2$ e se stesso

#### Esempio 2
>Sia $V=\mathbb{R}[x]_{\leq n-1}=\{ \text{polinomi di grado }\leq n-1 \}=\{ p(x)=a_{0}+a_{1}x+a_{2}x^2+\dots+a_{n-1}x^{n-1} \}$
>E sia $U=\mathbb{R}^n$

Sia $f:V\to U$, $a_{0}+a_{1}x+a_{2}x^2+\dots+a_{n-1}x^{n-1}\mapsto(a_{0},a_{1},a_{2},\dots,a_{n-1})$

- $f$ è iniettiva perche $f(p(x))=\underline{0}\Leftrightarrow p=0$
	- E dunque $\mathrm{ker}=\{ \underline{0} \}$
- $f$ è suriettiva

>[!done] $f$ è un ***isomorfismo*** tra $V$ e $U$

### Spazi Isomorfi
>[!info] Definizione
>Due [[Campi e Spazi Vettoriali#Spazio Vettoriale|spazi vettoriali]] $V,U$ su uno stesso [[Campi e Spazi Vettoriali#Campo|campo]] $\mathbb{K}$, sono ***Isomorfi*** se esiste un isomorfismo da $V\to U$
>>[!tip] Proprietà
>>Essere Isomorfi è una [[Introduzione#Relazione di Equivalenza|relazione di equivalenza]]

#### Dimostrazione
>[!abstract] Proprietà Riflessiva

Uno spazio vettoriale è un ***isomorfismo*** *rispetto a se stesso*
- Prendo la [[Git-Obsidian/Analisi/Funzioni/Introduzione Funzioni#Funzione Identità|funzione identità]]
$$
\begin{array}
\ f:V\to V \\
v\mapsto v
\end{array}
$$
- È un ***isomorfismo***

>[!abstract] Proprietà Simmetrica

##### Proprietà
>L'***inverso*** di un isomorfismo è un isomorfismo

###### Dimostrazione
>Sia $f:V\to U$ un *isomorfismo* di [[Campi e Spazi Vettoriali#Spazio Vettoriale|spazi vettoriali]]

Poiché $f$ è biunivoca, esiste $f^{-1}:U\to V$

>[!question] $f$ è lineare?

Siano $u_{1},u_{2}\in U$
- Poiché $f$ è [[Git-Obsidian/Analisi/Funzioni/Introduzione Funzioni#Funzione Biunivoca|biunivoca]], cioè
$$
\exists! v_{1},v_{2}\in V :f(v_{1})=u_{1},f(v_{2}) =u_{2}
$$

Possiamo dire che :
$$
f^{-1}(u_{1}+u_{2})=f^-1(f(v_{1})+f(v_{2}))
$$
E poiché $f$ è lineare:
$$
f^{-1}(f(v_{1}+v_{2})) = v_{1}+v_{2}=f^{-1}(u_{1})+f^{-1}(u_{2})
$$

Quindi $f^{-1}$ è un ***isomorfismo***

>[!abstract] Proprietà Transitiva

##### Proprietà
>La ***composizione*** di [[Applicazioni Lineari#Applicazione Lineare|applicazioni lineari]] è lineare
>- *In particolare la composizione di isomorfismi è un isomorfismo*

###### Dimostrazione
>Siano $V,U,W$ [[Campi e Spazi Vettoriali#Spazio Vettoriale|spazi vettoriali]] e $f,g$ *applicazioni lineari*
$$
V\underbrace{ \to }_{ f } U \underbrace{ \to }_{ g } W
$$

>[!abstract] Somma

Siano $v_{1},v_{2}\in V$
- Allora $(g_{o}f)(v_{1}+v_{2})=g(f(v_{1}+v_{2}))$

Quindi poiché $f$ è *lineare*, possiamo dire che:
- $g(f(v_{1})+f(v_{2}))$
Di nuovo, poiché $g$ è *lineare*
- $g(f(v_{1}))+g(f(v_{2}))=(g_{o}f)(v_{1})+(g_{o}f)(v_{2})$


>[!abstract] Prodotto

>Analogamente il *prodotto per scalare*:

$$
g(f(av)) = g(af(v))=ag(f(v))
$$

Inoltre se $f$ e $g$ sono [[Git-Obsidian/Analisi/Funzioni/Introduzione Funzioni#Funzione Biunivoca|biunivoche]], cioè esistono le *inverse* $f^{-1},g^{-1}$
- Allora anche $g_{o}f$ è ***biunivoca***, perché la sua inversa è:
$$
(g_{o}f)^{-1} =f^{-1}_{o}g^{-1}
$$
>[!done] Conclusione

Quindi $g_{o}f$ è un'applicazione lineare biunivoca
- $g_{o}f$ è un ***isomorfismo***

