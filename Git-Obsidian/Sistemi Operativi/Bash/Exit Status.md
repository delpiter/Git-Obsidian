Valore numerico compreso tra 0 e 255 con cui ogni comando dice a chi ha ordinato di eseguire il comando stesso, se il comando è andato a buon fine

Se un comando va a buon fine, l'exit status restituisce 0
- Altrimenti ritorna un valore che indica il tipo di errore accaduto

Istruzione `exit [0-255]`
- Termina uno script e ritorna il valore

Come catturare il risultato di un programma?
- Si utilizza una variabile d'ambiente predefinita: `$?` che viene modificata ogni volta che un programma o un comando termina
- Viene inserito il risultato numerico restituito dal comando o programma


Exit status riservati:
>Alcuni esempi

1.  Errori Generali
127. Command not Found
128. Invalid argument to exit
130. Script terminated by Ctrl + C 
