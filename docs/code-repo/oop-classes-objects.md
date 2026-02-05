# Classes and Objects

!!! info "Key Distinction"
    **Class** = Blueprint or template (defines structure).

    **Object** = Specific instance created from the class (stores actual data).

---

## Class Example (Blueprint)

A class defines what attributes and behaviors objects will have.

```csharp
public class Student
{
    // Attributes (data)
    public string Name { get; set; } = "";
    public int Score { get; set; }

    // Behaviour (method)
    public void PrintDetails()
    {
        Console.WriteLine($"{Name}: {Score}");
    }
}
```

!!! warning "Important"
    A class **does not store real data by itself** - it's just a blueprint.

---

## Object Example (Instance)

An object is created from a class and stores actual values.

```csharp
// Create an object from the Student class
Student student1 = new Student();
student1.Name = "Alex";
student1.Score = 85;

// Call the object's method
student1.PrintDetails();  // Output: Alex: 85
```

!!! tip "What This Shows"
    - `student1` is an **object**
    - It is created **from the Student class**
    - It **stores actual values**
    - It can **call the class's methods**

---

## Multiple Objects from One Class

You can create many objects from the same class, each with different data.

```csharp
// Create first student
Student student1 = new Student();
student1.Name = "Alex";
student1.Score = 85;

// Create second student
Student student2 = new Student();
student2.Name = "Jordan";
student2.Score = 92;

// Create third student
Student student3 = new Student();
student3.Name = "Taylor";
student3.Score = 78;

// Each object stores different data
student1.PrintDetails();  // Alex: 85
student2.PrintDetails();  // Jordan: 92
student3.PrintDetails();  // Taylor: 78
```

---

## More Complex Class Example

```csharp
public class Book
{
    // Attributes
    public string Title { get; set; } = "";
    public string Author { get; set; } = "";
    public int Year { get; set; }
    public bool IsAvailable { get; set; } = true;

    // Methods
    public void BorrowBook()
    {
        if (IsAvailable)
        {
            IsAvailable = false;
            Console.WriteLine($"{Title} has been borrowed.");
        }
        else
        {
            Console.WriteLine($"{Title} is not available.");
        }
    }

    public void ReturnBook()
    {
        IsAvailable = true;
        Console.WriteLine($"{Title} has been returned.");
    }

    public void PrintDetails()
    {
        string status = IsAvailable ? "Available" : "Borrowed";
        Console.WriteLine($"{Title} by {Author} ({Year}) - {status}");
    }
}
```

### Using the Book class

```csharp
Book book1 = new Book();
book1.Title = "Clean Code";
book1.Author = "Robert Martin";
book1.Year = 2008;

book1.PrintDetails();  // Clean Code by Robert Martin (2008) - Available
book1.BorrowBook();    // Clean Code has been borrowed.
book1.PrintDetails();  // Clean Code by Robert Martin (2008) - Borrowed
book1.ReturnBook();    // Clean Code has been returned.
```

---

## Complete Example

```csharp
using System;

public class Student
{
    public string Name { get; set; } = "";
    public int Score { get; set; }

    public void PrintDetails()
    {
        Console.WriteLine($"{Name}: {Score}");
    }

    public string GetGrade()
    {
        if (Score >= 80) return "A";
        if (Score >= 60) return "B";
        if (Score >= 40) return "C";
        return "F";
    }
}

public class Program
{
    public static void Main()
    {
        // Create objects from Student class
        Student s1 = new Student();
        s1.Name = "Alex";
        s1.Score = 85;

        Student s2 = new Student();
        s2.Name = "Jordan";
        s2.Score = 72;

        // Use object methods
        s1.PrintDetails();
        Console.WriteLine($"Grade: {s1.GetGrade()}");

        s2.PrintDetails();
        Console.WriteLine($"Grade: {s2.GetGrade()}");
    }
}
```

---

## Another Example: Car Class

```csharp
public class Car
{
    // Attributes
    public string Make { get; set; } = "";
    public string Model { get; set; } = "";
    public int Year { get; set; }
    public double FuelLevel { get; set; } = 100.0;

    // Methods
    public void Drive(double distance)
    {
        double fuelUsed = distance * 0.08;  // 8L per 100km
        if (fuelUsed <= FuelLevel)
        {
            FuelLevel -= fuelUsed;
            Console.WriteLine($"Drove {distance}km. Fuel remaining: {FuelLevel:F1}L");
        }
        else
        {
            Console.WriteLine("Not enough fuel!");
        }
    }

    public void Refuel(double amount)
    {
        FuelLevel += amount;
        if (FuelLevel > 100) FuelLevel = 100;
        Console.WriteLine($"Refueled. Fuel level: {FuelLevel:F1}L");
    }

    public void PrintDetails()
    {
        Console.WriteLine($"{Year} {Make} {Model} - Fuel: {FuelLevel:F1}L");
    }
}
```

### Using the Car class

```csharp
Car myCar = new Car();
myCar.Make = "Toyota";
myCar.Model = "Camry";
myCar.Year = 2020;

myCar.PrintDetails();      // 2020 Toyota Camry - Fuel: 100.0L
myCar.Drive(200);          // Drove 200km. Fuel remaining: 84.0L
myCar.Drive(500);          // Drove 500km. Fuel remaining: 44.0L
myCar.Refuel(30);          // Refueled. Fuel level: 74.0L
```

---

## Quick Reference

| Term | Meaning | Example |
|------|---------|---------|
| **Class** | Blueprint/template | `Student` |
| **Object** | Specific instance | `student1` |
| **Attributes** | Data/properties | `Name`, `Score` |
| **Methods** | Behaviors/actions | `PrintDetails()` |

!!! tip "Exam Language"
    "A class is a blueprint; an object is a specific instance created from that blueprint."
