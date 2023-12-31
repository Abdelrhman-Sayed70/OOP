# Exceptions
- `Error` Represents serious problems and hard to solve, like library incompatibility, infinite recursion, memory leak
- `Exceptions` **unwanted or unexpected** event, that occurs during the program execution i.e. run time. Solved using programmer

# Try-Catch
- `try` block that contains the code that can throw an exception
- `catch` block which contains an Exception object and catch block. this block will be executed if the try block throws the mentioned exception in the catch object
- The `Exception` class is the parent of all exception classes
- **If the exception is the same as in catch, it will be handled and the try block will not be executed and the rest of the code will be done**
- It can contain multiple catch statements
```java
int []arr = new int[2];
try {
    System.out.println("start of try");
    System.out.println(arr[2]);
    System.out.println("rest of try");
}
catch (Exception exception){
    System.out.println(exception);
    System.out.println("rest of catch");
}
System.out.println("rest of code");
System.out.println(arr[0]);
```
```
start of try
java.lang.ArrayIndexOutOfBoundsException: Index 2 out of bounds for length 2
rest of catch
rest of code
0
```

# Finally
- Used to clean up code such as closing file such as closing files or closing connection
- Get executed whether the exception occurred or not
- For each `try` block there can be 0 or more `catch` blocks but only one `finally` block
- Finally block will be executed even return is called
- Can't be executed if the program exits [by calling `System.exit()` or by causing `fetal error`]
