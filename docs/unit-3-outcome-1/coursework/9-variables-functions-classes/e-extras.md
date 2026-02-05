# e. Extras

This page provides drop-in C# templates (like we did for file I/O) and shows exactly how they are used inside a program.

!!! info "Programming Support (Non-examinable)"
    Exams assess the **concepts** (scope, return values, class vs object), not syntax.

---

## 1) Constants + scope (the "one place to change it" pattern)

```csharp
public static class AppConfig
{
    // Constant: fixed value that must not change
    public const int MAX_ATTEMPTS = 3;

    // Constant: fixed rate (example)
    public const decimal TAX_RATE = 0.10m;
}
```

### How it's used

```csharp
if (attempts >= AppConfig.MAX_ATTEMPTS)
{
    Console.WriteLine("No attempts remaining.");
}
```

---

## 2) Global vs local variables (safe pattern)

### Global variable example (program-wide state)

```csharp
public static class AppState
{
    // Global variable: used across multiple modules
    public static int TotalStudents = 0;
}
```

### Local variable example (inside a method)

```csharp
public static void AddStudent(string name)
{
    int nameLength = name.Length; // local variable
    AppState.TotalStudents++;     // global variable updated
}
```

!!! warning "Teacher note"
    Use globals sparingly — locals reduce unintended changes.

---

## 3) Function vs method templates (C#)

### Function (returns a value)

```csharp
public static int CalculateFinalScore(int testScore, int examScore)
{
    int finalScore = testScore + examScore; // local variable
    return finalScore;                      // RETURN value => function (VCAA concept)
}
```

**How it's used**

```csharp
int result = CalculateFinalScore(35, 55);
```

---

### Method (does not return a value)

```csharp
public static void DisplayFinalScore(int score)
{
    Console.WriteLine($"Final score: {score}"); // action only, no return value
}
```

**How it's used**

```csharp
DisplayFinalScore(result);
```

---

### ✅ Correct order students should copy

```csharp
int result = CalculateFinalScore(35, 55); // function
DisplayFinalScore(result);                // method
```

---

## 4) Class + object templates (drop-in)

### Class (blueprint)

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

### Object (instance) + usage

```csharp
Student student1 = new Student();
student1.Name = "Alex";
student1.Score = 85;

student1.PrintDetails();
```

---

## 5) FULL mini-program example (shows everything working together)

This demonstrates:

- constants
- global + local variables
- function + method usage
- class + object creation

```csharp
using System;

public static class AppConfig
{
    public const int MAX_SCORE = 100;
    public const decimal TAX_RATE = 0.10m;
}

public static class AppState
{
    public static int TotalStudents = 0; // global variable
}

public class Student
{
    public string Name { get; set; } = "";
    public int Score { get; set; }

    public void PrintDetails()
    {
        Console.WriteLine($"{Name}: {Score}");
    }
}

public class Program
{
    // Function: returns a value
    public static int CalculateFinalScore(int testScore, int examScore)
    {
        int finalScore = testScore + examScore;  // local variable
        return finalScore;
    }

    // Method: performs an action (no return)
    public static void DisplayMessage(string msg)
    {
        Console.WriteLine(msg);
    }

    public static void Main()
    {
        // Create an object from a class
        Student s = new Student();
        s.Name = "Jordan";

        // Use a function (returns a value)
        int rawScore = CalculateFinalScore(45, 60);

        // Use a constant to enforce a rule
        if (rawScore > AppConfig.MAX_SCORE)
        {
            s.Score = AppConfig.MAX_SCORE;
        }
        else
        {
            s.Score = rawScore;
        }

        // Update a global variable
        AppState.TotalStudents++;

        // Use methods (actions)
        DisplayMessage("Student saved:");
        s.PrintDetails();
        DisplayMessage($"Total students recorded: {AppState.TotalStudents}");
    }
}
```

---

## 40+ Exam phrasing (students should memorise)

!!! tip "Essential exam phrases"
    ✅ *"A local variable is only accessible within the function/method where it is declared."*

    ✅ *"A global variable can be accessed throughout the program, which can increase risk of unintended modification."*

    ✅ *"A constant is used for fixed values to improve reliability and maintainability."*

    ✅ *"A function returns a value using a RETURN statement."*

    ✅ *"A method performs a task and does not return a value."*

    ✅ *"A class is a blueprint; an object is an instance created from the class."*
