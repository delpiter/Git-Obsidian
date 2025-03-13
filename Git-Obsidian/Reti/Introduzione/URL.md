>Una risorsa $R$ è univocamente identificata da un indirizzo che la localizza ([[Indirizzamento|locator]]).

La modalità di accesso a un elemento nel web viene specificata mediante un'espressione denominata ***U***niform ***R***esource ***L***ocator


>[!def] Definizione
>L'`URL` è un indirizzo web che *identifica univocamente* una risorsa su internet.

>L'`URL` è diviso in ***diverse parti***

>[!example] http\:\/\/www\.azienda\.com/news/

### Protocollo
>[!help] ***http\:\/\/***www\.azienda\.com/news/

Viene scritto l'***identificatore del protocollo*** utilizzato per accedere alla pagina web.

*Solitamente*
- Indica al *browser* quale **protocollo** deve essere utilizzato.

### Host
>[!help] http\:\/\/***www\.azienda\.com***/news/

L'***host*** è il sistema terminale dove la risorsa web è ***immagazzinata***.
- Espresso attraverso il nome del dominio nella gerarchia #addLink DNS, oppure come #addLink Indirizzo IP numerico

### Percorso
>[!help] http\:\/\/www\.azienda\.com ***/news/***

Il ***percorso*** identifica il percorso dove si trova la risorsa che si sta ricercando.

### Parametri
>È possibile inserire parametri alla fine dell'`URL`.

>[!help] http\:\/\/www\.azienda\.com/news/***?p1=v1&p2=v2***

I ***parametri*** sono inseriti dopo un punto *di domanda* messo alla fine del percorso.
- Si possono avere più parametri, ciascuno è *separato dal carattere*: `&`
