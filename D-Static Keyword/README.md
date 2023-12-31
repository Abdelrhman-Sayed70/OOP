# Static Modifier

## Static Variable [Class Variable]
- Property will be shared for all objects
- Stored in memory only `once` not for all objects
- Called using class name
- Can be called inside static & non-static methods

### System to create a unique ID for each student
```java
package mainpackage;

public class Student {
    private String name;
    private int id;
    static String college = "IT";
    static int idCnt = 1;

    public Student(String name) {
        this.name = name;
        this.id = idCnt++;
    }
}
```

## Static Method [Class Method]
- Called using the class name. no need for an object
- Can access only static data and static methods
- Can not be referred by `this` or `super` keywords 

  
```cpp
public class MyMath {
    public static int cube(int n) {
        return n * n * n;
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        System.out.println(MyMath.cube(3));
    }
}
```

## Static block 
- in a static block [static method for example] we cannot access non-static data members.
- also we cannot use `super` `this` keywords
- main is a static method. why? To allow JVM to call the main method without creating an object from the class which enhances the memory
- Static block used to initialize static data members


## Static Class
- it is a class defined inside another class
- Can not be a class with static keyword except inner [nested] class [class inside a class]
- Increase Encapsulation concept & security 



## Trace
```java
public class Example {
    public int a = 10;
    public static int b = 10;

    public void instanceMethod(){
        a += 10;
    }

    public static void staticMethod(){
        b += 10;
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Example example = new Example();
        example.instanceMethod();
        Example.staticMethod();
        System.out.println(example.a); // a = 20
        System.out.println(example.b); // b = 20

        example = new Example();
        example.instanceMethod();
        Example.staticMethod();
        System.out.println(example.a); // a = 20
        System.out.println(example.b); // b = 30
    }
}
```
