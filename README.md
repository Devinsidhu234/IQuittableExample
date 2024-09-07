# IQuittableExample
// IQuittable.cs
public interface IQuittable
{
    // Method signature for Quit, which does not return any value
    void Quit();
}
// Employee.cs
public class Employee : IQuittable
{
    public int Id { get; set; }           // Employee ID
    public string FirstName { get; set; } // Employee's first name
    public string LastName { get; set; }  // Employee's last name

    // Implementation of the Quit method from the IQuittable interface
    public void Quit()
    {
        // Implementation could be anything; here, we'll just print a message
        Console.WriteLine($"{FirstName} {LastName} has quit the job.");
    }
}
// Program.cs
using System;

class Program
{
    static void Main(string[] args)
    {
        // Create an Employee object
        Employee employee = new Employee
        {
            Id = 1,
            FirstName = "John",
            LastName = "Doe"
        };

        // Declare a variable of type IQuittable and assign it the Employee object
        IQuittable quittableEmployee = employee;

        // Call the Quit method using the IQuittable reference
        quittableEmployee.Quit(); // Outputs: John Doe has quit the job.
    }
}
