# Method Overloading
- Multiple methods can have the same name with different signature
- Changing `parameters datatype` or/and `# params` will make an overload
- Changing `return type`  does not make overloading

```java
import java.util.Scanner;
import static java.lang.Math.max;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        int x = input.nextInt();
        int y = input.nextInt();
        int z = input.nextInt();

        System.out.println(add(x,y,z));
    }

    static int add(int a, int b){
        return a + b;
    }

    static float add(float a, float b){
        return a + b;
    }

    static int add (int a, int b, int c) {
        return a + b + c;
    }
}
```
