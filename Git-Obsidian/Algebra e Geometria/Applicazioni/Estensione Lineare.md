## Teorema dell'Estensione Lineare
---
>[!Teorema]
>Sia $V$ uno [[Campi e Spazi Vettoriali#Spazio Vettoriale|spazio vettoriale]] si $\mathbb{K}$
>Sia $v_{1},\dots,v_{n}$ una sua [[Campi e Spazi Vettoriali#Base|base]]
>Sia $U$ uno *spazio vettoriale* su $\mathbb{K}$ 
>Sia $u_{1},\dots,u_{n}$ un insieme di vettori di $U$
><u>Allora</u>
>Esiste ***una e una sola*** *applicazione lineare*:
>$$f:V\to U:f(v_{1})=u_{1},\dots,f(v_{n})=u_{n}$$

### Dimostrazione
>Sia $v\in V$

Allora:
$$
\exists! a_{1},\dots,a_{n}\in \mathbb{K}:v=a_{1}v_{1}+\dots+a_{n}v_{n}
$$
- Quindi dato che $f$ è ***lineare***
$$
f(v) = a_{1}f(v_{1})+\dots+a_{n}f(v_{n})=a_{1}u_{1}+\dots+a_{n}u_{n}
$$

Quindi esiste ed è 