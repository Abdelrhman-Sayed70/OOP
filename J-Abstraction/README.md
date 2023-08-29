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
- Abstract class also can contain `concrete methods [methods with body]` final and static methods.
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


### **In case the inherited class will not override all methods, we can use the abstract keyword for this class**
```java
public abstract class SUVAutopilot extends Car{
    @Override
    public void autopilot(){
        System.out.println("Specified SUVAutopilot");
    }

    abstract void streamingServices();

    abstract void parkingSensors();
}
```


## Upcasting
Reusability, assume you want to create functions that accept an object of each child, you can only create one function of the parent class and pass any child of this parent
```java
public class Main {
    public static void fun(Car car){
        car.autopilot();
    }

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Hatchback puerHatchback = new Hatchback();
        SUV puerSUV = new SUV();
        Car hatchbackCar = new Hatchback();

        fun(puerHatchback); //  Hatchback autopilot
        fun(puerSUV); // SUV autopilot
        fun(hatchbackCar); // Hatchback autopilot
    }
}
```
