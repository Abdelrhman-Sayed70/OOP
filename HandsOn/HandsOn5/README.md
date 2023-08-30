# HAndsOn5

Create an interface (Called Measurable) that has a constant float attribute PI = 3.14 and two 
methods float getArea() and void show() to display the value of the area to the user (use 
getArea()).

Create 2 Classes (Rectangle, Circle) that implement the Measurable interface:
- Rectangle class has two integer attributes: breadth and length. 
- Circle class has one integer attribute: radius.


The two classes Rectangle and Circle should calculate the area as follows: 
- Rectangle Area = breadth * length 
- Circle Area= 2*PI*(radius)²

```java
public interface Measurable {
    public static final float PI = 3.14f;

    float getArea();
    void show();
}
```
```java
public class Circle implements Measurable{
    private int radius;

    public Circle(int radius) {
        this.radius = radius;
    }

    @Override
    public float getArea() {
        return (2 * PI * radius * radius);
    }

    @Override
    public void show() {
        System.out.println(getArea());
    }
}
```
```java
public class Rectangle implements Measurable{
    private int length, width;

    Rectangle(int length, int width){
        this.length = length;
        this.width = width;
    }

    @Override
    public float getArea() {
        return width * length;
    }

    @Override
    public void show() {
        System.out.println(getArea());
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Measurable measurable = null;

        System.out.println("Enter R for Rectangle or C for Circle");
        char ch = input.next().charAt(0);
        if (ch == 'R'){
            measurable = new Rectangle(2,3);
        }
        else if (ch == 'C'){
            measurable = new Circle(5);
        }

        measurable.show();
    }
}
```
