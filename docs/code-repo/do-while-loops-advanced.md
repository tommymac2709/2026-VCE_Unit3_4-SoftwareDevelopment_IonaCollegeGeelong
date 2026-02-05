# DO/WHILE Loops - Advanced

!!! info "When to Use DO/WHILE Loops"
    Use DO/WHILE loops when something **must run AT LEAST ONCE**, then check if it should happen again.

    **Perfect for:** Menus (must show first), validation (must ask once), surveys/forms, registration/booking, any system where first attempt is guaranteed.

!!! warning "Key Difference"
    DO/WHILE always runs **AT LEAST ONCE**, even if the condition is false from the start!

---

## Example 1: Menu System - Always Show Menu First

??? note "Click to view code"
    ```csharp
    int menuChoice;

    do
    {
        Console.WriteLine("--- CAFE MENU ---");
        Console.WriteLine("1. Order Coffee");
        Console.WriteLine("2. View Orders");
        Console.WriteLine("3. Exit");
        Console.Write("Choose option: ");
        menuChoice = int.Parse(Console.ReadLine());

        if (menuChoice == 1)
            Console.WriteLine("Coffee ordered!");
        else if (menuChoice == 2)
            Console.WriteLine("Viewing orders...");

    } while (menuChoice != 3);
    Console.WriteLine("Goodbye!");
    ```

---

## Example 2: Survey - Must Answer At Least One Question

??? note "Click to view code"
    ```csharp
    string answer;

    do
    {
        Console.Write("Rate our service (1-5): ");
        answer = Console.ReadLine();

        if (answer != "1" && answer != "2" && answer != "3" && answer != "4" && answer != "5")
        {
            Console.WriteLine("Invalid rating!");
        }

    } while (answer != "1" && answer != "2" && answer != "3" && answer != "4" && answer != "5");
    Console.WriteLine($"Thank you for rating us {answer} stars!");
    ```

---

## Example 3: Registration - Must Enter Valid Email

??? note "Click to view code"
    ```csharp
    string email;

    do
    {
        Console.Write("Enter email address: ");
        email = Console.ReadLine();

        if (!email.Contains("@"))
        {
            Console.WriteLine("Invalid email - must contain @");
        }

    } while (!email.Contains("@"));
    Console.WriteLine($"Registered: {email}");
    ```

---

## Example 4: Gym Booking - Book At Least One Session

??? note "Click to view code"
    ```csharp
    List<string> sessions = new List<string>();
    string continueBooking;

    do
    {
        Console.Write("Enter session time (e.g., 9am): ");
        string session = Console.ReadLine();
        sessions.Add(session);
        Console.WriteLine($"Booked! Total sessions: {sessions.Count}");

        Console.Write("Book another? (y/n): ");
        continueBooking = Console.ReadLine();

    } while (continueBooking == "y");
    Console.WriteLine($"Booking complete: {sessions.Count} sessions booked");
    ```

---

## Example 5: Quiz - Must Answer At Least One Question

??? note "Click to view code"
    ```csharp
    string quizAnswer;
    int attempts = 0;

    do
    {
        attempts++;
        Console.Write("What is 5 + 3? ");
        quizAnswer = Console.ReadLine();

        if (quizAnswer != "8")
        {
            Console.WriteLine($"Wrong! Try again (Attempt {attempts})");
        }

    } while (quizAnswer != "8");
    Console.WriteLine($"Correct! You got it in {attempts} attempts");
    ```

---

## Assessment Use Cases

!!! tip "When to Use in Your Software Module"
    - Menu systems (always display menu)
    - Data validation (must prompt user)
    - Registration forms (must collect info)
    - Booking systems (must make at least one booking)
    - Survey/quiz systems (must answer)
