//Super Uses, Using Final With Inheritance
import java.util.Scanner;   // Import Scanner class to take input from the user

// Parent class
class School
{
    String schoolName = "Avanthi School"; // Variable that stores the school name

    // Constructor of parent class
    School()
    {
        System.out.println("School constructor is called.");
    }

    // Final method - cannot be overridden by child class
    final void schoolRules()
    {
        System.out.println("Rule: Every student must wear the uniform.");
    }

    // Parent method
    void displaySchool()
    {
        System.out.println("Welcome to " + schoolName);
    }
}

// Child class inheriting School
class Student extends School
{
    String studentName; // Variable to store student name

    // Constructor of child class
    Student(String name)
    {
        super();  // Calls the parent constructor
        studentName = name; // Assigning input name to variable
    }

    // Method to display student details
    void displayStudent()
    {
        super.displaySchool(); // Calling parent method using super

        System.out.println("Student Name: " + studentName);
    }
}

// Main class
public class SuperFinal
{
    public static void main(String[] args)
    {
        Scanner scan = new Scanner(System.in); // Scanner object to read input

        System.out.println("Enter Student Name:");
        String name = scan.nextLine(); // Taking student name input

        Student s = new Student(name); // Creating object of Student class

        s.displayStudent(); // Calling child class method

        s.schoolRules(); // Calling final method from parent class

        scan.close(); // Closing scanner
    }
}
