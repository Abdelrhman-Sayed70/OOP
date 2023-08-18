# Method Overloading
- Multiple methods can have the same name with different signature
- Changing `parameters datatype` or/and `# params` will make an overload
- Changing `return type`  does not make overloading
- Known at `compile time`

```java
static int add(int a, int b){
    return a + b;
}

static float add(float a, float b){
    return a + b;
}

static int add (int a, int b, int c) {
    return a + b + c;
}
```

## Can we override the main function?
`yes`
```cpp
public static void main(int n) {
    System.out.println(n);
}

public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    int n = input.nextInt();
    main(n);
}
```
