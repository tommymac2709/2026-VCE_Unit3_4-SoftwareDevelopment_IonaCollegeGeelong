# WHILE Loops

!!! info "When to Use WHILE Loops"
    Use WHILE loops when you need to **keep going until something happens**.

    **Perfect for:** Counting until target reached, asking until correct answer, adding until total is enough, repeating until user says stop.

---

## Example 1: Count to 5

??? note "Click to view code"
    ```csharp
    int count = 1;

    while (count <= 5)
    {
        Console.WriteLine($"Count: {count}");
        count++;
    }
    ```

---

## Example 2: Keep Asking Until User Says "yes"

??? note "Click to view code"
    ```csharp
    string answer = "";

    while (answer != "yes")
    {
        Console.Write("Type 'yes' to continue: ");
        answer = Console.ReadLine();
    }
    Console.WriteLine("Thank you!");
    ```

---

## Example 3: Add Numbers Until Total Reaches 10

??? note "Click to view code"
    ```csharp
    int sum = 0;
    int number = 1;

    while (sum < 10)
    {
        sum = sum + number;
        Console.WriteLine($"Added {number}, sum = {sum}");
        number++;
    }
    ```

---

## Example 4: Print 4 Stars

??? note "Click to view code"
    ```csharp
    int counter = 0;

    while (counter < 4)
    {
        Console.Write("* ");
        counter++;
    }
    Console.WriteLine();
    ```

---

## Example 5: Keep Doubling Until Over 50

??? note "Click to view code"
    ```csharp
    int value = 1;

    while (value <= 50)
    {
        Console.WriteLine($"Value: {value}");
        value = value * 2;
    }
    ```

---

## Quick Reference

!!! abstract "WHILE Loop Pattern"
    ```csharp
    while (condition is true)
    {
        // Keep doing this
    }
    ```

    **Key points:**

    - Loop continues **while** the condition is true
    - May not run at all if condition is initially false
    - Make sure something inside changes the condition!
