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
