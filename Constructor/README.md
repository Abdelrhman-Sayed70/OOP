# Constructor
- A constructor in Java is a special method that is used to initialize objects.
- The constructor is called when an object of a class is created. It can be used to set initial values for object attributes:
- All classes have constructors by default: if you do not create a class constructor yourself, Java creates one for you.

## Creating Constructor Rules
- Its name is the same as the class name
- Can not have a return type
- Must has `public` access modifier

## Constructor Types
- Default constructor

- Copy Constructor

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

## Constructor Chaining
The constructor calls another constructor in the same class using `this` keywords

```java
package mainpackage;

public class Product {
    private String name;
    private float price;
    private String color;
    private int quantity; // added recently

    public Product(){
        
    }

    public Product(String name, float price, String color) {
        this.name = name;
        this.price = price;
        this.color = color;
    }

    // added to set quantity
    public Product(String name, float price, String color, int quantity) {
        this(name, price, color); // constructor chaining
        this.quantity = quantity;
    }
}
```


## Copy Constructor
The constructor takes an object as an argument

```cpp
public Product(String name, float price, String color) {
    this.name = name;
    this.price = price;
    this.color = color;
}

public Product(Product product){
    this(product.name, product.price, product.color);
}
```

```java
Product product = new Product("camera", 100, "red", 5);
Product product1 = new Product(product);
```

## Notes
- Any object call **`only one`** constructor
- 1 class can have more than 1 constructor with different signature `overloading`
- A constructor can call another constructor using `this` keyword `Constructor chaining`

