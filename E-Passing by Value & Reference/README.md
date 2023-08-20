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
