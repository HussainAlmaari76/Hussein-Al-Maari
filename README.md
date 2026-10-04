# Hussein-Al-Maari



using System;
using System.Collections.Generic;

class Shape
{
    public virtual double CalculateArea()
    {
        return 0;
    }
}

class Circle : Shape
{
    public double Radius { get; set; }

    public Circle(double radius)
    {
        Radius = radius;
    }

    public override double CalculateArea()
    {
        return Math.PI * Radius * Radius;
    }
}

class Rectangle : Shape
{
    public double Width { get; set; }
    public double Height { get; set; }

    public Rectangle(double width, double height)
    {
        Width = width;
        Height = height;
    }

    public override double CalculateArea()
    {
        return Width * Height;
    }
}

class Program
{
    static void Main()
    {
        List<Shape> shapes = new List<Shape>
        {
            new Circle(5),
            new Rectangle(4, 6)
        };

        foreach (Shape shape in shapes)
        {
            Console.WriteLine(shape.GetType().Name);
            Console.WriteLine(shape.CalculateArea());
        }
    }
}




=======================================



using System;
using System.Collections.Generic;

class Person
{
    public string Name { get; set; }

    public Person(string name)
    {
        Name = name;
    }

    public virtual void DisplayInfo()
    {
        Console.WriteLine("Name: " + Name);
    }
}

class Student : Person
{
    public int StudentId { get; set; }

    public Student(string name, int studentId) : base(name)
    {
        StudentId = studentId;
    }

    public override void DisplayInfo()
    {
        Console.WriteLine("Student: " + Name + ", ID: " + StudentId);
    }
}

class Employee : Person
{
    public double Salary { get; set; }

    public Employee(string name, double salary) : base(name)
    {
        Salary = salary;
    }

    public override void DisplayInfo()
    {
        Console.WriteLine("Employee: " + Name + ", Salary: " + Salary);
    }
}

class Teacher : Person
{
    public string CourseName { get; set; }

    public Teacher(string name, string courseName) : base(name)
    {
        CourseName = courseName;
    }

    public override void DisplayInfo()
    {
        Console.WriteLine("Teacher: " + Name + ", Course: " + CourseName);
    }
}

class Program
{
    static void ShowPerson(Person person)
    {
        person.DisplayInfo();
    }

    static void Main()
    {
        List<Person> people = new List<Person>
        {
            new Student("Ali", 101),
            new Employee("Ahmed", 5000),
            new Teacher("Hassan", "Programming")
        };

        foreach (Person person in people)
        {
            Console.WriteLine(person.GetType().Name);
            person.DisplayInfo();
        }

        ShowPerson(people[0]);
    }
}



==========================================



using System;

class Person
{
    public string Name { get; set; }
    public string Email { get; set; }

    public Person(string name, string email)
    {
        Console.WriteLine("Person Constructor");
        Name = name;
        Email = email;
    }

    public void DisplayBasicInfo()
    {
        Console.WriteLine("Name: " + Name);
        Console.WriteLine("Email: " + Email);
    }
}

class Student : Person
{
    public int StudentId { get; set; }
    public double GPA { get; set; }

    public Student(string name, string email, int studentId, double gpa)
        : base(name, email)
    {
        Console.WriteLine("Student Constructor");
        StudentId = studentId;
        GPA = gpa;
    }
}

class Employee : Person
{
    public int EmployeeId { get; set; }
    public double Salary { get; set; }

    public Employee(string name, string email, int employeeId, double salary)
        : base(name, email)
    {
        Console.WriteLine("Employee Constructor");
        EmployeeId = employeeId;
        Salary = salary;
    }
}

class Teacher : Employee
{
    public string CourseName { get; set; }

    public Teacher(string name, string email, int employeeId, double salary, string courseName)
        : base(name, email, employeeId, salary)
    {
        Console.WriteLine("Teacher Constructor");
        CourseName = courseName;
    }

    public void Teach()
    {
        Console.WriteLine("Teaching: " + CourseName);
    }
}

class Program
{
    static void Main()
    {
        Student student = new Student(
            "Ali",
            "ali@email.com",
            101,
            3.5
        );

        Console.WriteLine();
        student.DisplayBasicInfo();
        Console.WriteLine("Student ID: " + student.StudentId);
        Console.WriteLine("GPA: " + student.GPA);

        Console.WriteLine();

        Teacher teacher = new Teacher(
            "Ahmed",
            "ahmed@email.com",
            201,
            5000,
            "Programming"
        );

        Console.WriteLine();
        teacher.DisplayBasicInfo();
        Console.WriteLine("Employee ID: " + teacher.EmployeeId);
        Console.WriteLine("Salary: " + teacher.Salary);
        teacher.Teach();
    }
}



=========================================



using System;

class Vehicle
{
    public string Brand { get; set; }
    public int Year { get; set; }

    public Vehicle(string brand, int year)
    {
        Brand = brand;
        Year = year;
    }

    public void Start()
    {
        Console.WriteLine(Brand + " started.");
    }
}

class Car : Vehicle
{
    public int NumberOfDoors { get; set; }

    public Car(string brand, int year, int numberOfDoors)
        : base(brand, year)
    {
        NumberOfDoors = numberOfDoors;
    }
}

class Bus : Vehicle
{
    public int Capacity { get; set; }

    public Bus(string brand, int year, int capacity)
        : base(brand, year)
    {
        Capacity = capacity;
    }
}

class Motorcycle : Vehicle
{
    public bool HasSidecar { get; set; }

    public Motorcycle(string brand, int year, bool hasSidecar)
        : base(brand, year)
    {
        HasSidecar = hasSidecar;
    }
}

class Program
{
    static void Main()
    {
        Car car = new Car("Toyota", 2022, 4);
        Bus bus = new Bus("Mercedes", 2020, 50);
        Motorcycle motorcycle = new Motorcycle("Honda", 2023, false);

        car.Start();
        bus.Start();
        motorcycle.Start();
    }
}

