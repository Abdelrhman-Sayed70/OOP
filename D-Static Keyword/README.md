# Static Modifier
## Static Variable [Class Variable]
- Property will be shared for all objects
- Stored in memory only `once` not for all objects
- Called using class name

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

## Static Method
called using the class name. no need for object


```cpp
package mainpackage;

public class MyMath {

    public static int cube(int n) {
        return n * n * n;
    }
}
```
```java
package mainpackage;

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
