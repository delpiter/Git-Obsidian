## Ordinamento
---
>[!input]
>Una sequenza di $n$ numeri $<a_{1},a_{2},\dots,a_{n}>$

>[!done] Output
>I numeri ricevuti in input ***ordinati*** dal più *piccolo* al più *grande*, ovvero:
>$$<a_{\pi(1)},a_{\pi(2)},\dots,a_{\pi(n)}>\text{ dove } a_{\pi(i)}\leq a_{\pi(i+1)}$$
>$\pi$ è una opportuna permutazione degli indici $1,\dots,n$

>[!tip] Ordinamento
>Ordinare un insieme di elementi significa identificare una ***opportuna permutazione*** degli indici del vettore tali per cui *riposizionando gli elementi del vettore* in accordo con la ***permutazione*** si ottiene un vettore ordinato

### Ordinamento in Place
>[!info] Definizione
>L'algoritmo permuta gli elementi ***direttamente nell'array originale***, senza utilizzare un secondo array di *appoggio*

### Ordinamento Stabile
>[!info] Definizione
>L'algoritmo *preserva l'ordine* con cui elementi con la *stessa chiave* compaiono nell'array originale
>>Mantiene l'ordinamento relativo originale

## Limite Inferiore di Complessità
---
>[!tip] Algoritmi Comparison Sort
>Gli algoritmi *comparison sort* sono algoritmi basati su **confronti di coppie di elementi**
>>[!example] Per esempio:
>>- *Insertion-Sort*
>>- *Merge-Sort*
>>- *Heap-Sort*
>>- *Quick-Sort*
>
>Questi metodi calcolano una soluzione che dipende esclusivamente dall'esito di confronti fra numeri

>[!Teorema] Lower Bound for Comparison Sort


```
t any comparison sort must make  omega(n lg n) comparisons in the worst case to sort n elements. Thus, merge sort and heapsort are asymptotically optimal, and no comparison sort exists that is faster by more than a constant factor.
```
