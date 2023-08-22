# Final Keyword
it is `non-access modifier` which can be used for 
- variables
- parameters
- methods
- classes

## `Final Variable`
- no modification for this variable more
- known at compile time
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

**`final static variable`**
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
