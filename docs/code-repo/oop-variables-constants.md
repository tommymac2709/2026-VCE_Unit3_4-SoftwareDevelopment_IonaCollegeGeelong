# Variables and Constants

!!! info "Key Concepts"
    **Local variables** have limited scope (inside one function/method).

    **Global variables** can be accessed throughout the program.

    **Constants** are fixed values that cannot change.

---

## Constants Pattern

Use constants for fixed values that must not change.

```csharp
public static class AppConfig
{
    // Constant: fixed value that must not change
    public const int MAX_ATTEMPTS = 3;
    public const int MAX_SCORE = 100;

    // Constant: fixed rate (example)
    public const decimal TAX_RATE = 0.10m;
}
```

### How to use constants

```csharp
if (attempts >= AppConfig.MAX_ATTEMPTS)
{
    Console.WriteLine("No attempts remaining.");
}

if (rawScore > AppConfig.MAX_SCORE)
{
    finalScore = AppConfig.MAX_SCORE;
}
```

!!! tip "Why Use Constants"
    - Prevents accidental modification
    - Changes only need to be made in one place
    - Improves reliability and maintainability

---

## Global Variables Pattern

Use global variables when multiple parts of the program need access to the same data.

```csharp
public static class AppState
{
    // Global variable: used across multiple modules
    public static int TotalStudents = 0;
    public static string CurrentUser = "";
}
```

### How to use global variables

```csharp
public static void AddStudent(string name)
{
    // ... add student logic ...
    AppState.TotalStudents++;  // Update global variable
}

public static void DisplayStats()
{
    Console.WriteLine($"Total students: {AppState.TotalStudents}");
    Console.WriteLine($"Current user: {AppState.CurrentUser}");
}
```

!!! warning "Use Globals Sparingly"
    Global variables increase the risk of unintended modification. Use local variables when possible.

---

## Local Variables Example

Local variables only exist inside the function/method where they are declared.

```csharp
public static void AddStudentScore(int score)
{
    int adjustedScore;   // local variable

    if (score > AppConfig.MAX_SCORE)
    {
        adjustedScore = AppConfig.MAX_SCORE;
    }
    else
    {
        adjustedScore = score;
    }

    // adjustedScore only exists in this method
    AppState.TotalStudents++;  // global variable updated
}
```

!!! tip "Advantages of Local Variables"
    - Limit access to data
    - Reduce unintended changes
    - Make programs easier to debug and maintain

---

## Complete Example

```csharp
// Global constants
public static class AppConfig
{
    public const int MAX_SCORE = 100;
}

// Global state
public static class AppState
{
    public static int TotalStudents = 0;
}

public class Program
{
    public static void Main()
    {
        int score1 = 85;  // local variable
        int score2 = 110; // local variable

        ProcessScore(score1);
        ProcessScore(score2);

        Console.WriteLine($"Total students: {AppState.TotalStudents}");
    }

    public static void ProcessScore(int rawScore)
    {
        int finalScore;  // local variable

        if (rawScore > AppConfig.MAX_SCORE)
        {
            finalScore = AppConfig.MAX_SCORE;
        }
        else
        {
            finalScore = rawScore;
        }

        Console.WriteLine($"Final score: {finalScore}");
        AppState.TotalStudents++;
    }
}
```

---

## Quick Reference

| Feature | Scope | Can Change | Best Use |
|---------|-------|------------|----------|
| **Constant** | Global | ❌ No | Fixed values (tax rate, max score) |
| **Global Variable** | Global | ✅ Yes | Data needed across modules |
| **Local Variable** | Limited | ✅ Yes | Temporary data in one function |
