## Compilazione
---
Nome del file uguale al nome della classe $\to$ `ClassName.java`

java versione 21

Entra nel cmd nella directory corretta
``` bash
javac ClassName.java
//file compilato (ClassName.class)
java ClassName
```

jvm Cerca il metodo main all'interno di `ClassName` e se lo trova lo esegue

Se devi compilare una cartella intera:
``` bash
javac *.java
```

```mermaid
classDiagram
    Position2D <|-- RobotPosition
    Position2D --o RobotEnvironment
    BaseRobot o-- RobotEnvironment
    Robot <|-- BaseRobot
    <<Interface>> Robot
    <<Interface>> Position2D
    class Position2D {
        getX() int
        getY() int
        plus(Position2D) int
        plus(int, int) int
    }
    class Robot {
        moveUp() boolean
        moveDown() boolean
        moveLeft() boolean
        moveRight() boolean
        recharge() void
        getBatteryLevel() double
        getPosition() Position2D
    }
    class BaseRobot {
        -batteryLevel : double
        -environment : RobotEnvironment
        -robotName : String
        BaseRobot(String)
        #consumeBattery(double)
        #isBatteryEnough(double) boolean
    }
    class RobotEnvironment {
        -position : Position2D
        RobotEnvironment(Position2D)
        move(Position2D) : boolean
        move(int, int) : boolean
    }
```

```mermaid
classDiagram
    Robot <|.. BaseRobot
    BaseRobot <|-- RobotWithTwoArms
    Robot <|-- RobotWithArms
    <<Interface>> Robot
    <<Interface>> RobotWithArms
    RobotWithArms <|.. RobotWithTwoArms
    RobotWithTwoArms o-- BaseArm
    class Robot {
        moveUp() boolean
        moveDown() boolean
        moveLeft() boolean
        moveRight() boolean
        recharge() void
        getBatteryLevel() double
        getPosition() Position2D
    }
    class RobotWithArms {
        pickUp() boolean
        dropDown() boolean
        getItemsCarried() int
    }
    class RobotWithTwoArms {
        RobotWithTwoArms(String)
    }
    class BaseArm {
        BaseArm(String)
        isGrabbing() boolean
        pickUp() void
        dropDown() void
        getConsumptionForPickUp() double
        getConsumptionForDropDown() double
    }
```