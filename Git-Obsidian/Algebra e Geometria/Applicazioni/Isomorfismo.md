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


>[!abstract] Proprietà Transitiva

