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
    class MapConstraint{
        <<Interface>>
        + checkConstraint(Positions)boolean
    }
    class MapConstraintFactory{
        <<Interface>>
        + adjacencyConstraint()MapConstraint
        + singleBlockConstraint()MapConstraint
        + maxNumberOfBlocks(maxBlocks)MapConstraint
        + minNumberOfBlocks(minBlocks)MapConstraint
    }
    class MapConstraintProvider{
        <<Interface>>
        + createNormal()MapConstraintsContainer
        + createSandbox()MapConstraintsContainer
    }
    class Grid{
        <<Interface>>
        + setConstraints(EditorType)
    }
    class MapConstraintsContainer {
        <<Interface>>
        + checkConstraint(Positions,ObjectType)
        + checkBeforeStartConstraints()
    }


    MapConstraintsContainer *-- MapConstraint : "contains many"
    Grid ..> MapConstraintProvider
    MapConstraintProvider ..> MapConstraintFactory
    MapConstraint <.. MapConstraintFactory : "creates"
    MapConstraintProvider ..> MapConstraintsContainer : "creates"
    Grid o-- MapConstraintsContainer
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

