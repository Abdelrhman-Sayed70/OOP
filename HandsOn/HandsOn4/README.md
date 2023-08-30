# HandsOn4
**`Write a Java program that has these 3 classes`**
- Animal class: which has an abstract sound function
- Cat class: which has a function that overrides the sound function
- Dog class: which has a function that overrides the sound function

**`In main`**
- Create an array of animals that contains 2 cats then 2 dogs then 1 cat.
- Then loop on the array check on the reference of each element in the Animal array, and display a certain message.
  - If it is a cat then display “Cat Object”  and then its sound.
  - If it is a dog then display “Dog Object” and then its sound.


## Solution
```java
public abstract class Animal {
    public abstract void sound();
}
```
```java
public class Dog extends Animal{
    @Override
    public void sound() {
        System.out.println("Dog HO HO");
    }
}
```
```java
public class Cat extends Animal{
    @Override
    public void sound() {
        System.out.println("Cat Meow Meow");
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Animal []animals = new Animal[]{new Cat(), new Cat(), new Dog(), new Dog(), new Cat()};

        for(Animal animal: animals) {
            if (animal instanceof Cat){
                System.out.println("Cat object");
            }
            else if (animal instanceof Dog){
                System.out.println("Dog object");
            }
            animal.sound();
        }
    }
}
```
