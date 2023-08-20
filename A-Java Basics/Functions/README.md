## Method Prototype & Signature
**`Method Signature`**
- Method name
- Parameter list

**`Method Prototype`**
- Return type
- Method name
- Parameter list

## Function Components
- **Function prototype** → return type, function name, function params
- **Function body** → function logic

## Function vs Methods
- Methods → declared in a class 
- Functions → declared outside a class

## Parameters vs Arguments
- Parameters → used in the prototype of the function
- Arguments → used when invoking the function

## Static Function
**`Function called without using object`**
```java
public class Main {
    public static void main(String[] args) {
        myMethod();
    }

    static void myMethod(){
        System.out.println("this is a method");
    }
}
```
