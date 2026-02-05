# c. Practical Examples

## 🎮 Control Structures (KK3.1.8)

### Example 1 – Sequence

```csharp
// Calculates shipping cost step-by-step
double itemPrice = 45.00;
double taxRate = 0.10;
double shippingFee = 8.50;

double tax = itemPrice * taxRate;
double total = itemPrice + tax + shippingFee;
Console.WriteLine($"Total: ${total}");
```

**Focus:** Demonstrates sequence – instructions execute line by line in order.

**Exam link:** "A sequence is a set of instructions that executes line by line" (KK3.1.8).

---

### Example 2 – Selection (single condition)

```csharp
// Checks if a student passes based on their score
int score = 72;

if (score >= 50)
    Console.WriteLine("Pass");
else
    Console.WriteLine("Fail");
```

**Focus:** Selection statement with conditional operator (>=) and Boolean evaluation.

**Exam link:** "Selections are run based on a condition being evaluated as true or false" (KK3.1.8; VCAA 2021 Q7).

---

### Example 3 – Nested selection

```csharp
// Determines discount based on membership status and purchase amount
bool isMember = true;
double purchaseAmount = 120.00;

if (isMember)
{
    if (purchaseAmount >= 100)
        Console.WriteLine("20% discount applied");
    else
        Console.WriteLine("10% discount applied");
}
else
    Console.WriteLine("No discount");
```

**Focus:** Nested selection – multiple conditions handled within the code.

**Exam link:** "Nested selections are useful when multiple conditions must be handled" (KK3.1.8; VCAA 2020 Exam B Q9).

---

### Example 4 – WHILE iteration

```csharp
// Keeps asking for a password until correct
string correctPassword = "secure123";
string userInput = "";

while (userInput != correctPassword)
{
    Console.Write("Enter password: ");
    userInput = Console.ReadLine();
}
Console.WriteLine("Access granted");
```

**Focus:** WHILE iteration – runs while condition is true; unknown number of iterations.

**Exam link:** "WHILE iterations are useful when the programmer does not know when the condition might be met" (KK3.1.8).

---

### Example 5 – DO/WHILE iteration

```csharp
// Menu system that runs at least once
int choice;
do
{
    Console.WriteLine("1. View balance");
    Console.WriteLine("2. Exit");
    Console.Write("Choose option: ");
    choice = int.Parse(Console.ReadLine());

    if (choice == 1)
        Console.WriteLine("Balance: $450.00");

} while (choice != 2);
```

**Focus:** DO/WHILE iteration – always executes at least once (post-test iteration).

**Exam link:** "A DO/WHILE iteration always runs at least once" (KK3.1.8; VCAA 2022 Q11).

---

### Example 6 – FOR iteration

```csharp
// Displays a times table for number 7
int number = 7;

for (int i = 1; i <= 10; i++)
{
    Console.WriteLine($"{number} x {i} = {number * i}");
}
```

**Focus:** FOR iteration – runs a predefined number of times with increment.

**Exam link:** "FOR iterations are particularly useful to perform an action on every element of an array" (KK3.1.8; VCAA 2019 Q14).

---

### Example 7 – Logical operators in selection

```csharp
// Checks eligibility for a driving test
int age = 17;
bool hasLearners = true;
int practiceHours = 50;

if (age >= 18 && hasLearners && practiceHours >= 50)
    Console.WriteLine("Eligible for test");
else
    Console.WriteLine("Not eligible");
```

**Focus:** Logical operators (&&) combining multiple Boolean conditions.

**Exam link:** "Logical operators are used to combine Boolean values in selection statements" (KK3.1.8; VCAA 2020 Q10).

---

## ✅ Validation Techniques (KK3.1.10)

### Example 8 – Existence checking

```csharp
// Ensures a username is provided
Console.Write("Enter username: ");
string username = Console.ReadLine();

if (string.IsNullOrEmpty(username))
    Console.WriteLine("Error: Username cannot be empty");
else
    Console.WriteLine("Username accepted");
```

**Focus:** Existence checking – verifies required data is not empty or null.

**Exam link:** "Existence checking verifies data has been provided" (KK3.1.10; VCAA 2021 Exam A Q8).

---

### Example 9 – Type checking

```csharp
// Validates that age input is numeric
Console.Write("Enter age: ");
string input = Console.ReadLine();
int age;

if (int.TryParse(input, out age))
    Console.WriteLine($"Age recorded: {age}");
else
    Console.WriteLine("Error: Age must be a number");
```

**Focus:** Type checking – confirms data is of the correct data type.

**Exam link:** "Type checking confirms data is the correct data type for its intended use" (KK3.1.10).

---

### Example 10 – Range checking

```csharp
// Validates exam score is within acceptable range
Console.Write("Enter exam score: ");
int score = int.Parse(Console.ReadLine());

if (score >= 0 && score <= 100)
    Console.WriteLine("Score accepted");
else
    Console.WriteLine("Error: Score must be between 0 and 100");
```

**Focus:** Range checking – ensures values fall within acceptable boundaries.

**Exam link:** "Range checking ensures numeric values fall within minimum and maximum boundaries" (KK3.1.10; VCAA 2022 Q9).

---

## ⚠️ Types of Errors (KK3.1.13)

### Example 11 – Syntax error

```csharp
// Missing semicolon causes syntax error
int count = 5  // Syntax error: missing semicolon
Console.WriteLine(count);
```

**Focus:** Syntax error – violates C# grammatical rules; program won't compile.

**Exam link:** "Syntax errors occur when code violates programming language rules" (KK3.1.13; VCAA 2020 Q12).

---

### Example 12 – Logic error

```csharp
// Calculates average incorrectly (logic error)
int[] scores = { 80, 90, 70 };
int total = 0;

for (int i = 0; i < scores.Length; i++)
    total += scores[i];

int average = total / scores.Length;  // Logic error: should divide by scores.Length
Console.WriteLine($"Average: {average}");
```

**Focus:** Logic error – program runs but produces incorrect result (120 instead of 80).

**Exam link:** "Logic errors occur when the program produces incorrect results" (KK3.1.13; VCAA 2021 Q13).

---

### Example 13 – Runtime error: Divide by zero

```csharp
// Attempts to calculate average with zero items
int total = 150;
int count = 0;

double average = total / count;  // Runtime error: divide by zero
Console.WriteLine($"Average: {average}");
```

**Focus:** Runtime error (divide by zero) – program crashes during execution.

**Exam link:** "Divide by zero is a runtime error" (KK3.1.13; VCAA 2019 Q15).

---

### Example 14 – Runtime error: Index out of range

```csharp
// Attempts to access array element that doesn't exist
int[] temperatures = { 18, 22, 19 }; LENGTH = 3
                       0    1   2

for (int i = 0; i <= temperatures.Length; i++)  // Should be i < temperatures.Length
    Console.WriteLine(temperatures[i]);  // Runtime error when i = 3
```

**Focus:** Runtime error (index out of range) – accessing invalid array index.

**Exam link:** "Index out of range occurs when attempting to access an array element using an invalid index" (KK3.1.13; VCAA 2022 Q14).

---

### Example 15 – Runtime error: Overflow

```csharp
// Calculation exceeds maximum value for byte data type
byte maxValue = 255;
byte result = (byte)(maxValue + 1);  // Runtime error: overflow

Console.WriteLine($"Result: {result}");
```

**Focus:** Runtime error (overflow) – calculation produces result too large for data type.

**Exam link:** "Overflow occurs when a calculation produces a result too large for the data type" (KK3.1.13).

---

### Example 16 – Runtime error: Type mismatch

```csharp
// Attempts operation on incompatible data types
string text = "Hello";
int number = 5;

int result = text + number;  // Runtime error: cannot add string and int
Console.WriteLine(result);
```

**Focus:** Runtime error (type mismatch) – operation performed on incompatible data types.

**Exam link:** "Type mismatch occurs when an operation is performed on incompatible data types" (KK3.1.13).
