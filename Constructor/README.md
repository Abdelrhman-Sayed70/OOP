# Constructor
- A constructor in Java is a special method that is used to initialize objects.
- The constructor is called when an object of a class is created. It can be used to set initial values for object attributes:
- All classes have constructors by default: if you do not create a class constructor yourself, Java creates one for you.

## Creating Constructor Rules
- It's name is the same of class name
- Can not have a return type
- Must has `public` access modifier

## Constructor Types
- Default constructor

- No arg constructor

- Parameterized constructor

## Default Constructor
- No argument constructor created by Java automatically
- Initialize all attributes to their default values
- Can be overridden

`Default constructor`
```java
public Product(){
}
```


`Default Overriden constructor`
```java
public Product(){
    this.name = "No Name";
    this.description = "No description";
}
```

## 

## Notes
- Any object call **`only one`** constructor
- 1 class can have more than 1 constructor with different signature `overloading`
- A constructor can call another constructor using `this` keyword


