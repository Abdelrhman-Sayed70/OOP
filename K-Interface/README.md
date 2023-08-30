# Interface
- **`Contract`**
- Enhance security and code privacy which the implementation can done using APIs

## `Interface Methods`
- All methods by default are `public` and `abstract`
- Although the interface can contain:
     - `default` methods [concrete] with the default keyword
     - `static` methods [concrete]
     - `private` methods [concrete]

    
- Method naming convention. end with `able` or start with `Can` [Movable or CanMove]

## `Implementor class of the Interface`
- Subclass must implement all Interface abstract methods and can override the default methods

## `Interface Attributes`
- Any defined attribute in the interface defined automatically as `public` `static` `final`
- Any defined method in the interface defined as `public` `abstract`
- Can not declare instance from interface
- We can use upcasting

## `Interface`
- Interface can extend more than one interface
- Can be used to achieve multiple inheritances in Java as a class can implement more than one interface
- Interface can not have any constructor


```java
public interface Movable {
    void moveUp();
    void moveDown();
    void moveLeft();
    void moveRight();
}
```
```java
public interface SelfDrivable {
    void destination(String destination);
    void drive();
}
```
```java
public class CarV1 implements Movable, SelfDrivable{
    protected int x;
    protected int y;
    protected int numberOfPassengers;

    public CarV1(){}

    public CarV1(int x, int y) {
        this.x = x;
        this.y = y;
    }

    @Override
    public void moveUp() {
        y++;
    }

    @Override
    public void moveDown() {
        y--;
    }

    @Override
    public void moveLeft() {
        x--;
    }

    @Override
    public void moveRight() {
        x++;
    }

    @Override
    public void destination(String destination) {
        System.out.println("destination: " + destination);
    }

    @Override
    public void drive() {
        System.out.println("drive");
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        SelfDrivable carV1 = new CarV1();
        carV1.drive();
    }
}
```

## Interface Attributes
- **By default all attributes in the interface are `public` `static` `final`**
- So we can put all variables that can take those properties

```java
public interface AppConstants {
    String APP_NAME = "APP";
    String LIGHT_MODE = "#FFF";
    String DARK_MODE = "#222";
}
```
**But we know that interface is a contract so its better to deal in it with methods, so it's better to create class for the above constants**
```java
public final class Constants {
    public static final String APP_NAME = "APP";
    public static final String LIGHT_MODE = "#FFF";
    public static final String DARK_MODE = "#222";
}
```

## Interface Concrete Methods [with body]
- Default methods
- Static methods
- Private methods

## Default Method
- The interface can contain concrete methods with the default keyword [WHY ?]
- To avoid problems of all implementor classes when adding new methods.
- This method can be overridden in the implementor classes with a public access modifier
- `This decreases abstraction`

```java
public interface SelfDrivable {
    void destination(String destination);

    void drive();

    default void defaultMethod(){
        System.out.println("default method");
    }
}
```
```java
public void defaultMethod(){
    System.out.println("CarV1 Default");
}
```

## 2 Interfaces Contain Methods with The Same Signature
- **Error at implementor classes to avoid `diamond problem`**
- class implements 2 methods with the same signature


## Class Has High Priority Than Interface
```java
public interface MyInterface {
    static void print(){
        System.out.println("Interface");
    }
}
```
```java
public class MyClass {
    public MyClass(){
        System.out.println("Parent Class Constructor");
    }

    public void print(){
        System.out.println("Class");
    }
}
```
```java
public class MagicClass extends MyClass implements MyInterface{
    public MagicClass(){
        System.out.println("Magic Class Constructor");
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        MagicClass magicClass = new MagicClass();
        magicClass.print();
    }
}
```
```
Parent Class Constructor
Magic Class Constructor
Class
```





## Functional Interface
**Interface contains single method**
```java
@FunctionalInterface
public interface MyFunctionalInterface {
    void singleMMethod();
}
```
