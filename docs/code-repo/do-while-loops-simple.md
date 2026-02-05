# DO/WHILE Loops

!!! info "When to Use DO/WHILE Loops"
    Use DO/WHILE loops when something **must happen at least once**, then check if it should happen again.

    **Perfect for:** Must ask for name, must show menu, must get valid number, must answer question, must enter data.

!!! warning "Key Difference"
    DO/WHILE always runs **AT LEAST ONCE**, even if the condition is false from the start!

---

## Example 1: Must Enter Name (Not Empty)

??? note "Click to view code"
    ```csharp
    string name;

    do
    {
        Console.Write("Enter your name: ");
        name = Console.ReadLine();
    } while (string.IsNullOrEmpty(name));

    Console.WriteLine($"Hello, {name}!");
    ```

---

## Example 2: Must Enter Number Between 1-10

??? note "Click to view code"
    ```csharp
    int num;

    do
    {
        Console.Write("Enter number (1-10): ");
        num = int.Parse(Console.ReadLine());
    } while (num < 1 || num > 10);

    Console.WriteLine($"You entered: {num}");
    ```

---

## Example 3: Show Menu At Least Once

??? note "Click to view code"
    ```csharp
    int option;

    do
    {
        Console.WriteLine("1. Start");
        Console.WriteLine("2. Exit");
        Console.Write("Choose: ");
        option = int.Parse(Console.ReadLine());
    } while (option != 2);

    Console.WriteLine("Goodbye!");
    ```

---

## Example 4: Must Answer Yes or No

??? note "Click to view code"
    ```csharp
    string response;

    do
    {
        Console.Write("Continue? (yes/no): ");
        response = Console.ReadLine();
    } while (response != "yes" && response != "no");

    Console.WriteLine($"You said: {response}");
    ```

---

## Example 5: Must Enter Positive Number

??? note "Click to view code"
    ```csharp
    int amount;

    do
    {
        Console.Write("Enter positive number: ");
        amount = int.Parse(Console.ReadLine());
    } while (amount <= 0);

    Console.WriteLine($"Amount: {amount}");
    ```

---

## Quick Reference

!!! abstract "DO/WHILE Loop Pattern"
    ```csharp
    do
    {
        // Do this at least once
    } while (condition is true);
    ```

    **Key points:**

    - Code runs **FIRST**, then checks condition
    - Always executes **at least once**
    - Perfect for validation and menus
    - Don't forget the semicolon after `while`!
