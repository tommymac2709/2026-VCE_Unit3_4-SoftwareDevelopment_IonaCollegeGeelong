# c. Practical Examples

## 🧩 Data Types (KK3.1.4)

### Example 1 – Numeric data type

```csharp
// Calculates total cost of movie tickets
int numberOfTickets = 3;
double ticketPrice = 14.50;
double total = numberOfTickets * ticketPrice;
Console.WriteLine($"Total cost: ${total}");
```

**Focus:** Demonstrates numeric data types (int, double) and arithmetic operators (*, +, /).

**Exam link:** Selecting the most efficient data type and performing mathematical operations.

---

### Example 2 – Text (string) data type

```csharp
// Concatenates first and last names
string firstName = "Taylor";
string lastName = "Nguyen";
string fullName = firstName + " " + lastName;
Console.WriteLine("Welcome, " + fullName + "!");
```

**Focus:** Text data type and use of the addition (+) operator for concatenation.

**Exam link:** Representing textual variables and performing basic string operations.

---

### Example 3 – Boolean data type and logical operators

```csharp
// Decides if a user can enter a restricted area
bool isStaff = true;
bool hasPass = false;
if (isStaff && hasPass)
    Console.WriteLine("Access granted.");
else
    Console.WriteLine("Access denied.");
```

**Focus:** Boolean data type, logical operators (&&, ||, !), and conditional logic.

**Exam link:** "Boolean values used in decision-making" (VCAA 2020 Q10 / 2022 Q8).

---

## 🧠 Data Structures (KK3.1.5)

### Example 4 – One-dimensional array

```csharp
// Stores five weekly sales totals and outputs the average
int[] sales = { 150, 200, 180, 220, 190 };
int total = 0;
for (int i = 0; i < sales.Length; i++)
    total += sales[i];
Console.WriteLine("Average sales: " + total / sales.Length);
```

**Focus:** One-dimensional array and use of an index to iterate through elements.

**Exam link:** "Using arrays to store related items of the same data type" (KK3.1.5; 2021 Exam C Q3).

---

### Example 5 – Two-dimensional array

```csharp
// Records temperatures for 3 days and 2 readings per day
int[,] temps = { {18, 22}, {19, 23}, {17, 21} };
for (int day = 0; day < 3; day++)
{
    Console.WriteLine("Day " + (day + 1) + ": "
        + temps[day, 0] + "°C AM, " + temps[day, 1] + "°C PM");
}
```

**Focus:** Two-dimensional array for tabular data (rows × columns).

**Exam link:** Demonstrates accessing data using two indices.

---

### Example 6 – Record (using class/struct)

```csharp
// Defines a record structure for a library book
class Book
{
    public string Title;
    public string Author;
    public bool OnLoan;
}
Book b1 = new Book();
b1.Title = "Tomorrow, and Tomorrow, and Tomorrow";
b1.Author = "Gabrielle Zevin";
b1.OnLoan = false;
Console.WriteLine($"{b1.Title} by {b1.Author}, On loan: {b1.OnLloan}");
```

**Focus:** Record data structure containing fields of varying data types (text + Boolean).

**Exam link:** "Records store related data of differing types" (KK3.1.5; 2020 Exam A Q13).

---

### Example 7 – Nested structure (array of records)

```csharp
// Stores multiple books in an array
Book[] library = new Book[2];
library[0] = new Book { Title = "1984", Author = "George Orwell", OnLoan = false };
library[1] = new Book { Title = "Frankenstein", Author = "Mary Shelley", OnLoan = true };
foreach (Book b in library)
    Console.WriteLine($"{b.Title} ({b.Author}) - On loan: {b.OnLoan}");
```

**Focus:** Combines arrays and records — a common VCAA Unit 3 Outcome 1 structure.

**Exam link:** Typical "array of records" pattern used for storing structured datasets.
