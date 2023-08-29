# HandsOn3
**`Create an Employee class (Abstract class) which contains:`**
- employeeName as a string, paymentPerHour as a integer number. All the parameters are protected.
- Parametrized constructor to fill the attributes.
- CalculateSalary() function. This function returns an integer number. The salary of the employee is calculated using the following equation: paymentPerHour * 8.

**`Create Contractor class which is derived from Employee class. This class contains:`**
- WorkingHours as a private integer attribute.
- Parametrized constructor to fill all attributes.
- Implementation of calculateSalary function. The salary of the contractor is calculated using the following equation: paymentPerHour * WorkingHour

**`Create FullTimeEmployee class which is derived from Employee class. This class contains:`**
- overtime as a private integer attribute that represents additional working hours.
- Parametrized constructor to fill all attributes.
- Implementation of calculateSalary function. The salary of the FullTimeEmployee is calculated using the following equation: paymentPerHour * (8 + overtime).

**`In another package, create a class that contains the main function:`**
- Create 2 objects from Contractor class and FullEmployee class.
- Display the salary of every employee.

## Solution
```java
package work;

public abstract class Employee {
    protected String name;
    protected int paymentPerHour;

    public Employee(String name, int paymentPerHour){
        this.name = name;
        this.paymentPerHour = paymentPerHour;
    }

    public int calculateSalary(){
        return paymentPerHour * 8;
    }
}
```
```java
package work;

public class Contractor extends Employee{
    private int workingHours;

    public Contractor(String name, int paymentPerHour, int workingHours) {
        super(name, paymentPerHour);
        this.workingHours = workingHours;
    }

    @Override
    public int calculateSalary() {
        return workingHours * paymentPerHour;
    }
}
```
```java
package work;

public class FullTimeEmployee extends Employee{
    private int overtime;

    public FullTimeEmployee(String name, int paymentPerHour, int overtime) {
        super(name, paymentPerHour);
        this.overtime = overtime;
    }

    @Override
    public int calculateSalary(){
    return paymentPerHour * (8 + overtime);
    }
}
```
```java
package mainpackage;
import work.Contractor;
import work.Employee;
import work.FullTimeEmployee;

import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Employee contractor = new Contractor("contractor", 10,5);
        Employee fullTimeEmployee = new FullTimeEmployee("Full Time", 20, 5);

        System.out.println("contractor salary: " + contractor.calculateSalary());
        System.out.println("full time employee: " + fullTimeEmployee.calculateSalary());
    }
}
```
