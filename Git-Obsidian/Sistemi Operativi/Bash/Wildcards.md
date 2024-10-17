## Pathname Substitution
---
>[!info] Definizione
>La *pathname substitution* è una delle [[Terminale Unix#Espansioni|espansioni]] più importanti, permette di generare delle stringhe, che possono essere solo **percorsi** di *file* o *directory*

#### Wildcards `* ? [...]`
>Prendendo come esempio una cartella con i seguenti file
> - `pippo pluto paperino test1 test2 test3 foo bar`

>[!attention] `*`
>Il carattere `*` può essere sostituito con una **qualsiasi sequenza di caratteri**, anche *vuota*

```bash
echo p*
pippo pluto paperino
```


>[!note] `?`
>Il carattere `?` può essere sostituito con **esattamente un carattere**

```bash
echo test?
test1 test2 test3
```

>[!example] `[...]`
>La sequenza di caratteri `[...]` può essere sostituita da **un solo carattere** fra quelli *specificati nell'elenco*

>[!question] Che cosa possono contenere le parentesi?

>Una sequenza di caratteri qualsiasi

`[ab123]`
- Può essere sostituito con un solo carattere tra `a`, `b`, `1`, `2` o `3`

`[1-7]`
- Può essere sostituito da una sola cifra compresa tra 1 e 7

`[a-g]`
- Può essere sostituito da un solo carattere compreso tra a e g

`[[:digit:]]`
- Può essere sostituito da un solo carattere numerico

`[[:upper:]]` / `[[:lower:]]` 
- Può essere sostituito da un solo carattere maiuscolo / minuscolo

