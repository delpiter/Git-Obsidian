### [[Numeri Complessi]]
### [[Limiti di Successioni#Unicità del Limite|Unicità del Limite]]
### [[Limiti di Successioni#Valore assoluto del Limite|Valore Assoluto del Limite]]
### [[Limiti di Successioni#Teorema del Confronto|Teorema del Confronto]]

### [[Criterio del Rapporto]]

### [[Introduzione Funzioni|Funzioni]]

### [[Limiti]]




























## Teorema di caratterizzazione
Sia $f: \mathrm{I} \rightarrow \mathbb{R}, c \in \mathrm{I}$
Allora le seguenti affermazioni sono equivalenti
1. $f$ è [[#Derivate#Definizione|derivabile]] in $c$
2. $\large f(x) = f(c) + f'(c)(x-c) + \circ(x-c) \ x\rightarrow c$
### Dimostrazione
#### $1) \implies 2)$
Sia $f$ [[#Derivate#Definizione|derivabile]] in $c$ (1)
$$
\displaylines{
\begin{align}
& \lim_{ x \to c } \frac{f(x)-f(c)}{x-c} = f'(c) \\
& \iff \frac{f(x)-f(c)}{x-c} = f'(c) + \circ(1) \qquad x\rightarrow c \\
& \iff f(x) - f(c) = f'(c)(x-c) + \circ(x-c) \qquad x\rightarrow  c \\
& \iff \large f(x) = f(c) +f'(c)(x-c)+\circ(x-c) \qquad x\rightarrow  c
\end{align}
}
$$
#### $2) \implies 1)$
Possiamo seguire gli [[#$1) implies 2)$|stessi passaggi]] in ordine inverso

