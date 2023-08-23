# Interface
- **`Contract`**
- A list of method signatures (abstract methods) without abstract keyword
- Enhance security and code privacy which the implementation can done using APIs
- Class implements all Interface methods
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
