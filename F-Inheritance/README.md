# Inheritance
- Sub-class can inherit attributes, methods, and nested classes from its superclass.
- Constructors `can not` be inherited as they are not members of a class, although super-class constructors can be called from sub-class

## Inheritance Types
- **Single Inheritance**: `one` class extends `one` class. `class B extends class A`
- **Multi-level Inheritance**: `class B extends class A and class C extends class B`
- **Hierarchical Inheritance**: one class is the superclass for more than one child class `class B extends class A and Class C extends class A`
- **Multiple Inheritance**: one class inherits from more than one class. it is `forbidden` in Java. but it can be done using the `interface` concept

![image](https://github.com/Abdelrhman-Sayed70/OOP/assets/99830416/72084f0f-6582-43b7-8724-8481b0d82f91)



## Specialization & Generalization
if we have an `employee` class & `developer` class which extends the `employee` class
- `Specialization`: object created from child class is **specialized** object
- `Generalization`: object created from parent class is **generalized** object
