# Interface
- **`Contract`**
- A list of method signatures (abstract methods) without abstract keyword, default methods [concrete], static methods [concret]
- Enhance security and code privacy which the implementation can done using APIs
- Class implements all Interface abstract methods
- Interface can extend more than one Interface
- Can be used to achieve multiple inheritances in Java as a class can implement more than one interface
- Naming Convention. end with `able` or start with `Can` [Movable or CanMove]
- Any defined attribute in the interface defined automatically as `public` `static` `final`
- Any defined method in the interface defined as `public` `abstract`
- Interface can not have any constructor
- Can not declare instance from interface
- We can use upcasting


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

## 2 Interfaces contain methods with the same signature
- **Error at implementor classes to avoid `diamond problem`**
- class implements 2 methods with the same signature


## Class has high priority than interface
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
