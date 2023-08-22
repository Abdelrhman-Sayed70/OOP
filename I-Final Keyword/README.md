# Final Keyword
it is `non-access modifier` which can be used for 
- variables
- parameters
- methods
- classes

## `Final Variable`
- no modification for this variable more
- known at compile time
```java
final int STUDENT_ID = 1;
```

**For the final field in the class, all constructors must have this field to set**
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
```
