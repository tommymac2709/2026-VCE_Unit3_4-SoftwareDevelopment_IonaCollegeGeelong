# FOR Loops

!!! info "When to Use FOR Loops"
    Use FOR loops when you know **exactly how many times** to repeat something.

    **Perfect for:** Counting, printing patterns, going through arrays/lists, repeating an exact number of times.

---

## Example 1: Count from 1 to 5

??? note "Click to view code"
    ```csharp
    for (int i = 1; i <= 5; i++)
    {
        Console.WriteLine($"Count: {i}");
    }
    ```

---

## Example 2: Print 5 Stars

??? note "Click to view code"
    ```csharp
    for (int i = 1; i <= 5; i++)
    {
        Console.Write("* ");
    }
    Console.WriteLine();
    ```

---

## Example 3: Display 3 Student Names

??? note "Click to view code"
    ```csharp
    string[] names = { "Alice", "Bob", "Charlie" };

    for (int i = 0; i < names.Length; i++)
    {
        Console.WriteLine($"{names[i]}");
    }
    ```

---

## Example 4: Add Numbers 1 to 5

??? note "Click to view code"
    ```csharp
    int total = 0;

    for (int i = 1; i <= 5; i++)
    {
        total = total + i;
        Console.WriteLine($"Adding {i}, total = {total}");
    }
    ```

---

## Example 5: Display 4 Prices

??? note "Click to view code"
    ```csharp
    float[] prices = { 5.00f, 3.50f, 2.00f, 4.25f };

    for (int i = 0; i < prices.Length; i++)
    {
        Console.WriteLine($"Item {i + 1}: ${prices[i]}");
    }
    ```

---

## Quick Reference

!!! abstract "FOR Loop Pattern"
    ```csharp
    for (int i = 1; i <= 5; i++)
    {
        // Do something 5 times
    }
    ```

    **Key parts:**

    - `int i = 1` - Start at 1
    - `i <= 5` - Keep going until i reaches 5
    - `i++` - Add 1 to i each time
