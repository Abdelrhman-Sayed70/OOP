# Inheritance
- Sub-class can inherit attributes, methods, and nested classes from its superclass.
- Constructors `can not` be inherited as they are not members of a class, although super-class constructors can be called from sub-class

## Inheritance Types
- **Single Inheritance**: `one` class extends `one` class. `class B extends class A`
- **Multi-level Inheritance**: `class B extends class A and class C extends class B`
- **Hierarchical Inheritance**: one class is the superclass for more than one child class `class B extends class A and Class C extends class A`
- **Multiple Inheritance**: one class inherits from more than one class. it is `forbidden` in Java. but it can be done using the `interface` concept

![image](https://github.com/Abdelrhman-Sayed70/OOP/assets/99830416/72084f0f-6582-43b7-8724-8481b0d82f91)

## Relationship between child & parent class
`IS-A relationship`
**Developer IS-A Employee**

## Specialization & Generalization
if we have an `employee` class & `developer` class which extends the `employee` class
- `Specialization`: object created from child class is **specialized** object
- `Generalization`: object created from the parent class is **generalized** object

## Protected Access Modifier
**Protected access modifier used in parent class, so the attributes are visible in the super, child class, and all package classes**

## Constructors
- any sub-class constructor **MUST** call **ONLY** one of superclass constructors
- we can call parent constructor from sub-classes using `super` keyword at the first line of the sub-class constructor
- or the default [no-arg] constructor will be invoked automatically If you do not invoke any

```java
public class Employee {
    private String name;
    private String email;
    private String phone;
    private String department;
    private String address;
    int birthDate;

    public Employee(){
        System.out.println("Parent No-arg constructor");
    }

    public Employee(String name, String email, String phone, String department, String address, int birthDate) {
        this.name = name;
        this.email = email;
        this.phone = phone;
        this.department = department;
        this.address = address;
        this.birthDate = birthDate;
        System.out.println("Parent arg constructor");
    }
}
```

```java
public class Developer extends Employee{
    String projectName;

    public Developer(String projectName) {
        this.projectName = projectName;
        // Parent no-arg constructor will be invoked automatically -> super();
    }

    public Developer(String name, String email, String phone, String department, String address, int birthDate, String projectName) {
        super(name, email, phone, department, address, birthDate); // Parent constructor is invoked
        this.projectName = projectName;
    }
}
```

```java
public static void main(String[] args) {
    Scanner input = new Scanner(System.in);

    // Parent No-arg constructor
    Developer developer = new Developer("MRG");

    // Parent arg constructor
    Developer developer1 = new Developer("ahmed", "se", "011", "cs", "cairo", 2001, "VCS");
}
```
