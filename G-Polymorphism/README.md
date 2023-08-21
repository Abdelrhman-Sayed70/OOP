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
package mainpackage;

public class Employee {
    private String name;
    private float salary;

    public Employee() {
    }

    public Employee(String name, float salary) {
        this.name = name;
        this.salary = salary;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public float getSalary() {
        return salary;
    }

    public void setSalary(float salary) {
        this.salary = salary;
    }
}
```

```java
package mainpackage;

public class SalariedEmployee extends Employee{
    float bonus;

    public SalariedEmployee(float bonus) {
        this.bonus = bonus;
    }

    public SalariedEmployee(String name, float salary, float bonus) {
        super(name, salary);
        this.bonus = bonus;
    }

    @Override
    public float getSalary() {
        return super.getSalary() + bonus;
    }
}
```

```java
package mainpackage;

public class DailyEmployee extends Employee{
    private float workDayPrice;
    private int dailyRate;

    public DailyEmployee(float workDayPrice, int dailyRate) {
        this.workDayPrice = workDayPrice;
        this.dailyRate = dailyRate;
    }

    public DailyEmployee(String name, float salary, float workDayPrice, int dailyRate) {
        super(name, salary);
        this.workDayPrice = workDayPrice;
        this.dailyRate = dailyRate;
    }

    public float getWorkDayPrice() {
        return workDayPrice;
    }

    public void setWorkDayPrice(float workDayPrice) {
        this.workDayPrice = workDayPrice;
    }

    public int getDailyRate() {
        return dailyRate;
    }

    public void setDailyRate(int dailyRate) {
        this.dailyRate = dailyRate;
    }

    @Override
    public float getSalary(){
        return workDayPrice * dailyRate;
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        SalariedEmployee salariedEmployee = new SalariedEmployee("ahmed", 1000, 200);
        System.out.println(salariedEmployee.getSalary()); // 1200
    }
}
```


## Upcasting
- **Change the object type to the child class**
- Done when method override occurs
- Object can access COMMON attributes & methods [overridden methods] only

```java
Employee salariedEmployee = new SalariedEmployee("ahmed", 1000, 200);
```


## [Interview Question] Can we override the static method?
No it can not be overridden
```java

```
