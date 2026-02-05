# Functions and Methods

!!! info "Key Distinction"
    **Functions** return a value (use RETURN statement).

    **Methods** perform a task without returning a value.

---

## Function Example (Returns a Value)

Functions are used when a result is needed for further processing.

```csharp
public static int CalculateFinalScore(int testScore, int examScore)
{
    int finalScore = testScore + examScore;  // local variable
    return finalScore;  // RETURN value => function
}
```

### How to use functions

```csharp
// The returned value is stored in a variable
int studentResult = CalculateFinalScore(35, 55);

// The result can be reused elsewhere
Console.WriteLine($"Result: {studentResult}");

if (studentResult >= 50)
{
    Console.WriteLine("Pass");
}
```

!!! tip "When to Use Functions"
    - A result is needed for further processing
    - A calculation must be reused
    - A value must be tested in a condition

---

## Method Example (No Return Value)

Methods are used to perform actions without returning a value.

```csharp
public static void DisplayFinalScore(int score)
{
    Console.WriteLine($"Final score: {score}");
    // No return statement - this is a method
}
```

### How to use methods

```csharp
int result = 90;

// Method performs an action (displays output)
DisplayFinalScore(result);

// No value is returned
```

!!! tip "When to Use Methods"
    - Display output to the user
    - Update data
    - Carry out procedures that don't need to return a value

---

## Function vs Method Side-by-Side

```csharp
// Function: returns a value
int result = CalculateFinalScore(40, 50);

// Method: performs an action
DisplayFinalScore(result);
```

!!! info "Recognition Pattern"
    **Functions** are used for **calculations**.

    **Methods** are used for **procedures or actions**.

    This pairing appears frequently in high-scoring SAC solutions.

---

## Complete Example

```csharp
using System;

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

    // Method: displays score
    public static void DisplayFinalScore(int score)
    {
        Console.WriteLine($"Final score: {score}");
    }

    public static void Main()
    {
        // Use a function (returns a value)
        int result = CalculateFinalScore(45, 60);

        // Use methods (actions)
        DisplayMessage("Student Result:");
        DisplayFinalScore(result);

        if (result >= 50)
        {
            DisplayMessage("Status: Pass");
        }
        else
        {
            DisplayMessage("Status: Fail");
        }
    }
}
```

---

## More Function Examples

### Calculate average

```csharp
public static float CalculateAverage(int[] scores)
{
    int total = 0;
    foreach (int score in scores)
    {
        total += score;
    }
    return (float)total / scores.Length;
}
```

### Check if passing

```csharp
public static bool IsPassing(int score)
{
    return score >= 50;
}
```

### Calculate discount

```csharp
public static float ApplyDiscount(float price, float discountRate)
{
    float discount = price * discountRate;
    float finalPrice = price - discount;
    return finalPrice;
}
```

---

## More Method Examples

### Display welcome message

```csharp
public static void DisplayWelcome(string username)
{
    Console.WriteLine($"Welcome, {username}!");
    Console.WriteLine("Please select an option from the menu.");
}
```

### Save data

```csharp
public static void SaveToFile(string data, string filename)
{
    File.WriteAllText(filename, data);
    Console.WriteLine("Data saved successfully.");
}
```

### Clear screen and show header

```csharp
public static void ShowHeader(string title)
{
    Console.Clear();
    Console.WriteLine("=".PadRight(50, '='));
    Console.WriteLine(title.PadLeft((50 + title.Length) / 2));
    Console.WriteLine("=".PadRight(50, '='));
}
```

---

## Quick Reference

| Feature | Function | Method |
|---------|----------|--------|
| Returns a value | ✅ Yes | ❌ No |
| Performs a task | ✅ Yes | ✅ Yes |
| Used in expressions | ✅ Yes | ❌ No |
| Has RETURN statement | ✅ Yes | ❌ No |
| Common use | Calculations | Procedures/Actions |
