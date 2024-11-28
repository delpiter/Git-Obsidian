- Game Programming Patterns Robert Nystrom
## Game Patterns
### Game Loop
>[!info]
>Control loop ruling the execution of a game
```java
while(true){
	processInput();
	update();
	render();
}
```
#### To avoid
Disaccoppiare la potenza del computer dalla resa del gioco
- Il programma deve comportarsi allo stesso modo su computer di potenza diversa
#### Real Time sync
```java
double lastTime = getCurrentTime()
while(true){
double current = getCurrentTime()
double elapsed = current - lastTime
ProcessInput()
}

```
Fissato un certo frame rate
- Se necessario il game loop aspetta per processare il prossimo frame
- Vengono "loccati" gli fps
- Elapsed conterrà la varizione di tempo dall'ultimo ciclo

### Modeling
>Game Object

> World
### Command
#### Input Processing
Lettura degli input asincroni
Necessità di riuscire a catturare un input in un qualsiasi momento
- Incapsulo la rischista come un oggetto
Comando generale con esecuzione
- Implementazione concreta del comando
- Possibile gestire una stessa esecuzione con diversi input
Gestione asincrona di eventi
```java
public interface Command{
	void execute(World scene);
}

public class Move Down implements Command{
	@override
	public void execute(World scene){
		
	}
}
```
Dove devono essere elaborati i comandi?
Il game engine è l'oggetto che deve eseguire i comandi
- Dalla funzione del game loop
```java
processInput()
```
Controlla la coda dei comandi e li processa uno alla volta
- Coda dei comandi è un parametro privato del game engine
- Sarà il gestore dell'interfaccia grafica che ascolterà i comandi
	- Nel nostro caso [swing](https://en.wikipedia.org/wiki/Swing_(Java))

Pattern mvc
- La view notifica il controller che un evento è accaduto
- Il game engine è il controller che gestisce le notifiche della view
	- Esso accoderà il comando alla coda dei comandi
	- Il model andrà a gestire gli eventi

Ogni sistema con una gui ha un thread specifico che gestisce gli eventi input
- EventDispatcher

Catena:
- tasto premuto
- Eventdispatcher loop cattura il comando
- controller (game engine) controlla all'interno del singolo game loop controllerà la lista dei comandi
#### Gestione collisioni
Concetto di bounding box
- Una semplice forma geometrica o un insieme di forme geometriche che rappresenta l'oggetto
Gestito dal model
```java
updateScene()
```
```java
public interface BoundingBox{
	bool isCollidingWith(P2d p, double radius)
}
```

### Observer
### Event Queue
### Component
Applicare un modello che da estrema flessibilità
- Permette alla singola entità di gestirsi da sola
Cambiamento puramente strutturale
Pattern adottato dal unity engine
Modellare ogni singolo componente del gioco come game object configurato in un modo specifico
### Factory
- Design pattern che serve a creare un oggetto con particolari configurazioni
## Modelling the Game
Start modeling the game
- Definisco tutti i concetti del gioco
Separazione dei concetti
- Model e graphics
## Game State + Events
Introduco un oggetto che rappresenta lo stato del gioco
- Sempre gestito all'interno del game loop
- Observer Pattern
## Game over
- Definisce la conclusione del game loop
Gestito dal game state


## FOMO
Fear of Missing Out