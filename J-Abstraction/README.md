# Abstraction
- One of the OOP concepts responsible for reusability & security
- **`Hiding`** the internal implementation of methods and only showing the functionality to the user
- Divide tasks between my team members

## Ways to achieve Abstraction
- Abstract Class [Partial Abstraction]
- Interface [Fully Abstraction]

## Abstract Class
- Allows us to build the `blueprints` of the concrete classes [children]
- Abstract class can not be instantiated [can not define an object from it]
- Could contain abstract methods [methods with no implementation], non-abstract (concrete) methods `[partial abstraction]`
- Abstract method also can contain final methods and static methods
- Also it can contain constructors [Usage ?] useful for child classes
- This class must be inherited and the children MUST implement all abstract methods [convert abstract method to concert methods].
- So the child class now are `concrete class` [class in which all of its methods are implemented]
- Non-abstract class can not have an abstract method
- There are no abstract variables
- Constructor can not have abstract keyword
- The method `CAN'T` be static and abstract at the same time, as static method can't be overridden
- Can't add `abstract` to `private` method or class, as they will be forbidden to access them in child then we cannot override it

```java
public abstract class Car {
    float height;
    float width;
    int numberOfWheels;

    public Car(){}

    public Car(float height, float width, int numberOfWheels) {
        this.height = height;
        this.width = width;
        this.numberOfWheels = numberOfWheels;
    }

    abstract void autopilot();

    abstract void streamingServices();

    abstract void parkingSensors();
}
```
```java
public class SUV extends Car{
    @Override
    void autopilot() {
        System.out.println("SUV autopilot");
    }

    @Override
    void streamingServices() {
        System.out.println("SUV streamingServices");
    }

    @Override
    void parkingSensors() {
        System.out.println("SUV parkingSensors");
    }
}
```
```java
public class Hatchback extends Car{
    @Override
    void autopilot() {
        System.out.println("Hatchback autopilot");
    }

    @Override
    void streamingServices() {
        System.out.println("Hatchback streamingServices");
    }

    @Override
    void parkingSensors() {
        System.out.println("Hatchback parkingSensors");
    }
}
```
