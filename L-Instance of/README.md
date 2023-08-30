# Instance Of 
- Test if the object is an instance of a class, subclass, or interface
- Known as `Type Comparison Operator`
- Returns `Null` if the object has a Null value
- The object of the subclass is an instance of a superclass

```java
public abstract class Vehicle {
    public void start(){
        System.out.println("Vehicle");
    }
}
```
```java
public class Bike extends Vehicle{
    @Override
    public void start(){
        System.out.println("Bike");
    }
}
```
```java
public class Car extends Vehicle{
    @Override
    public void start(){
        System.out.println("Car");
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Vehicle obj = new Car();
        Vehicle obj1 = new Bike();
        Car car = new Car();

        boolean b1 = obj instanceof Car; // true
        boolean b2 = obj instanceof Vehicle; // true

        boolean b3 = obj1 instanceof Car; // false
        boolean b4 = obj1 instanceof Vehicle; // true

        boolean b5 = car instanceof Car; // true
        boolean b6 = car instanceof Vehicle; // true

        System.out.println(b1 + "\n" + b2 + "\n" + b3 + "\n" + b4 + "\n" + b5 + "\n" + b6);
    }
}
```
