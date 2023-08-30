# Method Overriding
- Run Time polymorphism [dynamic or late binding] polymorphism
- Called run time as JVM doesn't know which function will invoke until creating a space in memory

## Rules for Method Overriding
- There must be an inheritance relationship
- The overridden method will be in the sub-class
- The overridden method in the sub-class MUST have the same method signature [name & param list]
- The access of the overridden method [in child class] should be more or equal not less </br> For example, a protected method in the super-class can be made public, but not private, in the subclass. Doing so will generate a compile-time error.
- `Private` methods, `Final` methods, and `Parent Constructor` cannot be overridden. Doing so generate a compile-time error
- `Static` method can not be overridden. Doing so will make `method hiding`
  - Parent obj = new Parent() calls the method at parent class
  - Child obj = new Child() calls the method at child class
  - Parent obj = new Child calls the method at parent class as static method cannot be overridden
- The overridden method must have the same type as the base method

```java
public class Parent {
    public void instanceMethod(){
        System.out.println("parent instance method");
    }

    public static void abstractMethod(){
        System.out.println("parent static method");
    }
}
```
```java
public class Child extends Parent{
    @Override
    public void instanceMethod(){
        System.out.println("child instance method");
    }

    // static method can not be overridden [method hiding]
    public static void abstractMethod(){
        System.out.println("child static method");
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Parent parent = new Parent();
        Child child = new Child();
        Parent obj = new Child();

        parent.instanceMethod(); // parent instance method
        parent.abstractMethod(); // parent static method

        child.instanceMethod(); // child instance method
        child.abstractMethod(); // child static method

        obj.instanceMethod(); // child instance method
        obj.abstractMethod(); // parent static method [static method cannot be overridden]
    }
}
```

---
# Upcasting
- Casting to supertype or Change the object type to the child class
- Generalization
- Always Possible
- Object can access only **`COMMON`** attributes & methods
```java
Parent obj = new Child();
```

### `Usage`
Reusability, Assume you want to create functions that accept an object of each child, you can only create one function of the parent class and pass any child of this parent


# Downcasting
- Casting to subtype
- Specification
- Not possible directly
- Can be applied using upcasting and downcasting

```java
Child obj = new Parent(); // Compile time error
```
```java
Parent upCasting = new Child();
Child downCasting = (Child) upCasting; // Ok
```
