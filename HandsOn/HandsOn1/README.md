# HandsOn1
- Generate a Package with two public classes: Clinic class and Doctor class.
- Doctor class should contain a string for name, that must be constant (final), a string for working_day ( ex: Saturday, Sunday ..etc.), and a static counter to count the number of generated Doctors objects.
- Implement a parametrized constructor that sets the name and working day
- Clinic class should contain (1) a private array of 3 doctors. (2) A function Insert_doctor, that accepts a doctor object and adds it in the array, and also prints the value of the counter after each insertion. (3) A function display_doctors that prints all the doctors names that work on a given day.
- In main generate a Clinic object and scan data of the 3 doctors and display all doctors who works on saturday.

## Solution
```java
package medical;

public class Doctor {
    private  final String name;
    private String workingDay;
    public static int counter = 0;

    public Doctor(String name, String workingDay) {
        this.name = name;
        this.workingDay = workingDay;
        counter++;
    }

    public String getName() {
        return name;
    }

    public String getWorkingDay() {
        return workingDay;
    }

    public void setWorkingDay(String workingDay) {
        this.workingDay = workingDay;
    }
}
```

```java
package medical;

public class Clinic {
    int clinicDoctorsCount = 3;
    private Doctor []doctors = new Doctor[clinicDoctorsCount];

    public void insertDoctor(Doctor doctor){
        int doctorNumber = Doctor.counter;
        int index = doctorNumber - 1;
        doctors[index] = doctor;
        System.out.println("Doctor " + doctorNumber + " is added");
    }

    public void displayDoctors(String day){
        System.out.print("Doctors working in " + day + " day are: ");
        for(Doctor doctor : doctors){
            if(doctor.getWorkingDay().equals(day))
                System.out.print(doctor.getName() + " ");
        }
    }
}
```

```java
package mainpackage;
import java.util.Scanner;
import medical.*;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        Clinic clinic = new Clinic();

        // Enter clinic doctors data
        int numberOfDoctors = 3;
        System.out.println("Taking doctors data...");
        for(int i = 1; i <= numberOfDoctors; i++){
            System.out.print("Enter doctor " + i + " name: ");
            String doctorName = input.next();

            System.out.print("Enter doctor " + i + " working day: ");
            String workingDay = input.next();

            Doctor doctor = new Doctor(doctorName, workingDay);
            clinic.insertDoctor(doctor);
        }

        // Search for specific doctors
        String searchDay = "SAT";
        clinic.displayDoctors(searchDay);
    }
}
```
