# Final Keyword
it is `non-access modifier` which can be used for 
- variables
- parameters
- methods
- classes

## `Final Variable`
- no modification for this variable more
- known at compile time
- `blank` the final value set later on in a constructor or a block
- set in all class constructors
```java
public class Student {
    final int STUDENT_ID;
    private String name;
    
    public Student(int studentId) {
        this.STUDENT_ID = studentId;
    }

    public Student(int STUDENT_ID, String name) {
        this.STUDENT_ID = STUDENT_ID;
        this.name = name;
    }
}
```

## `Final Static variable`
- final variable and shared for all objects
- can be set in the same line of declaration or in a static block
- can't be set in the constructor
```java
final static float DEGREE_OF_SUCCESS = 50;

// or
static {
    DEGREE_OD_SUCCESS = 50
}
```



## `Final Parameter`
**The parameter can not be changed in the method or constructor**

```java
public Student(final int studentId){
    this.studentId = studentId;
}
```


## `Final Method`
**Method cannot be overridden in child classes**
```java
final public void getInfo(){
    System.out.println("Student Id: " + studentId + ", name: " + name);
}
```

## `Final Class`
**Class cannot be inherited**


## `Final Reference`
**Can not change the reference in memory**
```java
final Student student = new Student(1, "ahmed");
student = new Student(2, "gaber"); // ERROR
```
