- Elenchiamo di seguito le proprietà degli [[Introduzione Integrali|integrali]]
## Proprietà
---
>[!info] Condizioni comuni
>Siano $f,g\in C([a,b],\mathbb{R})$

### Proprietà di linearità
>[!tip] Somma di Integrali
>$$\int ^b_{a}(f(x)+g(x)) \, dx = \int ^b_{a}f(x) \, dx + \int ^b_{a}g(x) \, dx   $$

>[!tip] Coefficiente Costante
>Sia $k\in\mathbb{R}$
>$$\int _{a}^b kf(x)\, dx = k\cdot\int _{a}^b f(x)\, dx  $$

### Proprietà di Monotonia
>[!tip] Monotonia
>Supponiamo $f(x)\geq g(x), \forall x\in[a,b]$
>$$\int _{a}^b f(x)\, dx \geq \int _{a}^b g(x)\, dx $$

### Proprietà di Additività
>[!tip] Additività
>Sia $c\in(a,b)$
>$$\int _{a}^b f(x)\, dx = \int _{a}^c f(x)\, dx+ \int _{c}^b f(x)\, dx $$

#### Osservazione
Per la proprietà dell'additività:
$$
0 = \int _{a}^a f(x)\, dx = \int _{a}^c f(x)\, dx +\int _{c}^a f(x)\, dx
$$
- Di conseguenza
$$
\int _{a}^b f(x)\, dx = -\int _{b}^a f(x)\, dx
$$

### Disugualianza Triangolare
>[!tip] 
>$$\left| \int _{a}^b f(x)\, dx  \right| \leq \int _{a}^b \left| f(x) \right| \, dx  $$