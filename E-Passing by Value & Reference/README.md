# Passing by Value & Reference

Primitive data types are passed by value and no option to call it by reference `java does not support`
```java
static void fun(int n){
    n++;
}
public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    int n = 1;
    fun(n);
    System.out.println(n); // 1 
}
```

But when we pass objects the call will be by `reference`
```java
public class Main {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Test test = new Test();
        test.number = 5;
        fun(test);
        System.out.println(test.number); // 6

    }

    static void fun(Test test){
        test.number++;
    }
}

class Test{
    int number;
}
```

## Trace
```java
package mainpackage;

public class Balloon {
    private String color;

    public Balloon(){

    }

    public Balloon(String color){
        this.color = color;
    }

    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }
}
```
```java
package mainpackage;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Balloon balloon1 = new Balloon("Red");
        Balloon balloon2 = new Balloon("Blue");

        System.out.println("Balloon 1 color: " + balloon1.getColor()); // Red
        System.out.println("Balloon 2 color: " + balloon2.getColor()); // Blue

        foo(balloon2);
        System.out.println(balloon2.getColor()); // Green
    }

    public static void foo(Balloon balloon){
        balloon.setColor("Green");
        balloon = new Balloon("Black"); // does not affect the original ballon2
    }
}
```

