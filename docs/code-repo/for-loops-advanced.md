# FOR Loops - Advanced

!!! info "When to Use FOR Loops"
    Use FOR loops when you know **exactly how many times** to repeat something.

    **Perfect for:** Processing all items in arrays/lists, displaying data sets, generating tables, processing bookings/appointments.

---

## Example 1: Shopping Cart - Calculate Total for All Items

??? note "Click to view code"
    ```csharp
    string[] items = { "Coffee", "Sandwich", "Cookie", "Juice" };
    float[] prices = { 5.00f, 8.50f, 3.00f, 4.50f };
    float total = 0;

    for (int i = 0; i < items.Length; i++)
    {
        Console.WriteLine($"{items[i]}: ${prices[i]}");
        total = total + prices[i];
    }
    Console.WriteLine($"TOTAL: ${total}");
    ```

---

## Example 2: Timetable - Show All Periods in a School Day

??? note "Click to view code"
    ```csharp
    string[] periods = { "Period 1", "Period 2", "Recess", "Period 3", "Period 4", "Lunch", "Period 5" };

    for (int i = 0; i < periods.Length; i++)
    {
        Console.WriteLine($"{i + 1}. {periods[i]}");
    }
    ```

---

## Example 3: Class Roll - Display All Students

??? note "Click to view code"
    ```csharp
    List<string> classRoll = new List<string> { "Alice", "Bob", "Charlie", "Diana", "Ethan" };

    for (int i = 0; i < classRoll.Count; i++)
    {
        Console.WriteLine($"Student {i + 1}: {classRoll[i]}");
    }
    ```

---

## Example 4: Times Table - Generate 7x Table

??? note "Click to view code"
    ```csharp
    int number = 7;

    for (int i = 1; i <= 10; i++)
    {
        Console.WriteLine($"{number} x {i} = {number * i}");
    }
    ```

---

## Example 5: Appointment System - Show All Bookings

??? note "Click to view code"
    ```csharp
    string[] times = { "9:00 AM", "10:00 AM", "11:00 AM", "2:00 PM", "3:00 PM" };
    string[] clients = { "John", "Sarah", "Mike", "Emma", "Lisa" };

    for (int i = 0; i < times.Length; i++)
    {
        Console.WriteLine($"{times[i]} - {clients[i]}");
    }
    ```

---

## Assessment Use Cases

!!! tip "When to Use in Your Software Module"
    - Shopping cart total calculator
    - Student grade averages for all students
    - Generate reports for all records
    - Display all products in inventory
    - Process all bookings for the day
