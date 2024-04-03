>*Per potere dire cosa deve fare una [[La CPU|CPU]] sono necessari dei dispositivi di Input/Output*
## I Monitor LCD
---
>[!info] *L*iquid *C*rystal *D*siplay
>I monitor `LCD` sono il sostituto del `CRT` (***C***athode ***R***ay ***T***ube)
>Forniscono una ***qualità grafica superiore*** rispetto ai `CRT` e hanno un *ingombro e peso inferiore*

### Funzionamento
>*I cristalli liquidi sono **molecole organiche vischiose** che scorrono in un liquido, ma come i cristalli sono anche dotate di una struttura spaziale*

>[!tip] Polarizzazione

Utilizzando un **campo elettrico** per modificare l'***orientamento delle molecole***
- Si fanno variare le *proprietà ottiche dei cristalli* e quindi l'***angolo di polarizzazione*** della luce che li attraversa

### Composizione
>*Uno schermo `LCD` è composto da numerose celle nelle quali sono intrappolati i cristalli*

>[!abstract] Contatti Elettrici
>Ogni cella è provvista di ***contatti elettrici***:
>- In modo da poter applicare un *campo elettrico* al liquido che contiene

>[!abstract] Schermi Polarizzatori
>Le celle sono contenute all'interno di due ***schermi polarizzatori***
>- Lungo gli assi perpendicolari tra loro

>[!abstract] Luce
>Una ***luce*** posizionata dietro la lastra posteriore

![[Screenshot 2024-04-03 145822.png]]
>[!done] RGB
>In uno schermo `LCD` a colori, ogni cella viene divisa in tre sezioni
>1. Una con un filtro ***Rosso***
>2. Una con un filtro ***Verde***
>3. Una con un filtro ***Blu***

### Matrice Attiva / Passiva

>[!info] Matrice Passiva
>Usata nei primi modelli degli schermi `LCD`
>La ***struttura a matrice passiva*** prevede un gruppo di contatti per ***ogni riga e colonna*** dello schermo, invece che una cella per ogni `PIXEL`
>>[!fail] Svantaggi
>>Può essere controllato un solo `PIXEL` alla volta
>>- Gli altri `PIXEL` devono *ricordare il loro stato* fino a che il **circuito di controllo** non si dedichi nuovamente a loro
>>Come conseguenze ci sono:
>>- Problemi di ***Persistenza***
>>	- Scie lasciate da *oggetti* in *moviemento*
>>- ***Diafonia*** 
>>	- *Diffusione laterale della luce* in parti molto luminose su sfondi scuri


>[!info] Matrice Attiva
>A ogni `PIXEL` dello schermo è associato un `TFT` (***T***hin ***F***ilm ***T***ransistor) realizzato con un substrato di materiale *semiconduttore* trasparente depositato sulle superfici interne dei vetri contenenti i **cristalli**
>Questo dispositivo ***memorizza lo stato elettrico*** di ogni `PIXEL` dello schermo mentre altri `PIXEL` vengono aggiornati

### AMOLED
>[!info] *A*ctive *M*atrix *O*rganic *LED*
>`AMOLED` è la tecnologia più recente utilizzata.
>È costituita da led organici che *emettono la luce* invece di bloccarla

## Il Mouse
---
>*È la periferica di puntamento più diffusa, resa popolare dalle `GUI` point & click, introdotte da Apple*

>[!tip] Modello Meccanico
>Nei ***modelli meccanici***, una sfera fa girare due *rotelle* *forate* *ortogonalmente* tra loro
>La loro *velocità di rotazione* è misurata da ***sensori a infrarossi*** e trasmessa al calcolatore

![[Pasted image 20240403175130.png]]

>[!hint] Modello Ottico
>I primi ***mouse ottici*** utilizzavano un `LED` e un *trasduttore ottico-elettrico* per rilevare il ***movimento relativo*** alla superficie
>>[!fail] Limitazione
>>Questi mouse potevano essere usati unicamente su ***speciali superfici metalliche*** con rete di sottili linee blue e grigie
>
>Venne introdotto successivamente un ***chip per l'elaborazione dell'immagine*** per supportare un maggior numero di superfici

>[!abstract] Modello Laser
>I ***mouse laser*** sono essenzialmente mouse ottici che utilizzano un ***laser*** al posto di un `LED` per l'illuminazione del piano d'appoggio
>Si ha una *maggiore risoluzione* nell'acquisizione dell'immagine

