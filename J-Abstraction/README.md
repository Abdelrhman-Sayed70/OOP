# Abstraction
- One of the OOP concepts responsible for reusability & security
- **`Hiding`** the internal implementation of methods and only showing the functionality to the user
- Divide tasks between my team members

## Ways to achieve Abstraction
- Abstract Class [Partial Abstraction]
- Interface [Fully Abstraction]

## Abstract Class
- Allows us to build the `blueprints` of the concrete classes [children]
- Abstract class can not be instantiated [can not define an object from it]
- Could contain abstract methods [methods with no implementation], non-abstract (concrete) methods `[partial abstraction]`
- Abstract method also can contain final methods and static methods
- Also it can contain constructors [Usage ?]
- This class must be inherited and the children MUST implement all abstract methods [convert abstract method to concert methods].
- So the child class now are `concrete class` [class in which all of its methods are implemented]
- note: non-abstract class can not have an abstract method
