# Method Overloading
- Compile time polymorphism [static - early binding] polymorphism
- Allows the use of the `same method` with `different signatures` [parameter list types or numbers]
- Increase the reusability of the code
- Single action in different ways

```java
package mainpackage;

public class Test {
    public int sum(int a, int b) {
        return a + b;
    }

    public float sum(float a, float b) {
        return a + b;
    }

    public int sum(int a, int b, int c) {
        return a + b + c;
    }
}
```
