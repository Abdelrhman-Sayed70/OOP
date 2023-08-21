# Polymorphis
**means `many forms` achieved by using:**
- Method Overloading
- Method Overriding


## Method Overloading
- **compile time** polymorphism [static - early binding] polymorphism
- allows the use of the same method with different signatures [parameter list types or numbers]
- increase the reusability of the code
- single action in different ways

## Method Overriding
**run time** polymorphism [dynamic or late binding] polymorphism

**`Rules for method overriding`** 
- There must be an inheritance relationship
- Overridden method will be in the sub-class
- The overridden method in the sub-class MUST have the same method signature [name & param list]

```java
public class Parent {
    public void print(){
        System.out.println("Parent");
    }
}
```
```java
public class Child extends Parent{
    @Override
    public void print(){
        System.out.println("Child");
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Parent parent = new Parent();
        Child child = new Child();
        

        parent.print(); // Parent
        child.print(); // Child
    }
}
```

## Upcasting
- **Change the object type to the child class**
- Done when method override occurs
- Object can access COMMON attributes & methods [overridden methods] only

```java
Parent obj = new Child(); // upcasting
obj.print(); // Child
```


## [Interview Question] Can we override the static method?
No, it can not be overridden
```java
public class Parent {
    public static void print(){
        System.out.println("Parent");
    }
}
```
```java
public class Child extends Parent{
    public static void print(){
        System.out.println("Child");
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Parent parent = new Parent();
        Child child = new Child();
        Parent obj = new Child(); // upcasting

        parent.print(); // Parent
        child.print(); // Child
        obj.print(); // Parent [no override done for print method]
    }
}
```
