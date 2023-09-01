# Exceptions
- `Error` Represents serious problems and hard to solve, like library incompatibility, infinite recursion, memory leak
- `Exceptions` **unwanted or unexpected** event, that occurs during the program execution i.e. run time. Solved using programmer

```java
int []arr = new int[2];
try{
    System.out.println(arr[3]);
}
catch (Exception e){
    System.out.println(e);
}
```

- If the exception is the same as in catch, it will be handled and the try block will not be executed and the rest of the code will be done

```java
int []arr = new int[2];
try {
    System.out.println(arr[2]);
    System.out.println("rest of try");
}
catch (Exception exception){
    System.out.println(exception);
    System.out.println("rest of catch");
}
System.out.println("rest of code");
```
```
java.lang.ArrayIndexOutOfBoundsException: Index 2 out of bounds for length 2
rest of catch
rest of code
```
