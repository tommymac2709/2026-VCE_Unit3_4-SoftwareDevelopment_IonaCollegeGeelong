# WHILE Loops - Advanced

!!! info "When to Use WHILE Loops"
    Use WHILE loops when you **DON'T know how many times** to repeat.

    **Perfect for:** User keeps entering data until they quit, password attempts until correct, searching until found, game loops, processing until condition changes.

---

## Example 1: Login System - Keep Asking Until Correct Password

??? note "Click to view code"
    ```csharp
    string correctPassword = "abc123";
    string userInput = "";

    while (userInput != correctPassword)
    {
        Console.Write("Enter password: ");
        userInput = Console.ReadLine();

        if (userInput != correctPassword)
            Console.WriteLine("Incorrect! Try again.");
    }
    Console.WriteLine("Access granted!");
    ```

---

## Example 2: ATM System - Withdraw Until Balance is Low

??? note "Click to view code"
    ```csharp
    float balance = 100.00f;

    while (balance >= 20)  // Keep allowing withdrawals while balance allows
    {
        Console.WriteLine($"Current balance: ${balance}");
        Console.Write("Withdraw $20? (y/n): ");
        string response = Console.ReadLine();

        if (response == "y")
            balance = balance - 20;
        else
            break;  // Exit loop if user says no
    }
    Console.WriteLine($"Final balance: ${balance}");
    ```

---

## Example 3: Inventory Search - Find Item in Stock

??? note "Click to view code"
    ```csharp
    string[] inventory = { "Laptop", "Mouse", "Keyboard", "Monitor", "Printer" };
    string searchItem = "Keyboard";
    int index = 0;
    bool found = false;

    while (index < inventory.Length && !found)
    {
        if (inventory[index] == searchItem)
        {
            found = true;
            Console.WriteLine($"Found {searchItem} at position {index + 1}");
        }
        index++;
    }
    ```

---

## Example 4: Game Menu - Keep Playing Until User Quits

??? note "Click to view code"
    ```csharp
    bool playing = true;
    int score = 0;

    while (playing)
    {
        Console.Write("Roll dice? (y/n): ");
        string input = Console.ReadLine();

        if (input == "y")
        {
            Random rand = new Random();
            int roll = rand.Next(1, 7);
            score = score + roll;
            Console.WriteLine($"You rolled: {roll} | Score: {score}");
        }
        else
        {
            playing = false;
        }
    }
    Console.WriteLine($"Game over! Final score: {score}");
    ```

---

## Example 5: Shopping Cart - Add Items Until Finished

??? note "Click to view code"
    ```csharp
    List<string> cart = new List<string>();
    bool shopping = true;

    while (shopping)
    {
        Console.Write("Add item (or type 'done'): ");
        string item = Console.ReadLine();

        if (item == "done")
        {
            shopping = false;
        }
        else
        {
            cart.Add(item);
            Console.WriteLine($"Added to cart. Total items: {cart.Count}");
        }
    }
    Console.WriteLine($"Checkout complete with {cart.Count} items");
    ```

---

## Assessment Use Cases

!!! tip "When to Use in Your Software Module"
    - Login systems with retry
    - ATM withdrawals until balance low
    - Search functions
    - Add items to cart until "done"
    - Game scoring until user quits
