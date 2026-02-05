# c. Practical Examples

## 🧩 Naming Conventions (KK3.1.9)

### Example 1 – Camel case naming convention

```csharp
// Stores and displays a student's full name
string firstName = "Alex";
string lastName = "Morgan";
string fullName = firstName + " " + lastName;
Console.WriteLine("Student: " + fullName);
```

**Focus:** Camel case naming convention – meaningful variable names with no spaces and capital letters for new words.

**Exam link:** "Camel casing improves readability and consistency of variable names" (KK3.1.9).

---

### Example 2 – Snake case naming convention

```csharp
// Stores the maximum allowed score
int max_score = 100;
int student_score = 85;
if (student_score <= max_score)
    Console.WriteLine("Score accepted");
```

**Focus:** Snake case naming convention – words separated by underscores and written in lowercase.

**Exam link:** Snake case improves readability by clearly separating words (KK3.1.9).

---

### Example 3 – Hungarian notation for interface controls

```csharp
// Button click event to calculate total
int iQuantity = 3;
double dPrice = 9.99;
double dTotalCost = iQuantity * dPrice;
Console.WriteLine("Total cost: $" + dTotalCost);
```

**Focus:** Hungarian notation – prefixes (i, d) indicate data type, followed by camel case describing purpose.

**Exam link:** "Hungarian notation identifies object or data type through prefixes" (KK3.1.9).

---

### Example 4 – Comparing naming conventions (purpose vs type)

```csharp
// Camel case – describes purpose only
int totalScore = 78;
// Hungarian notation – describes type and purpose
int iTotalScore = 78;
Console.WriteLine(totalScore);
Console.WriteLine(iTotalScore);
```

**Focus:** Difference between camel case and Hungarian notation.

**Exam link:** Common "compare and explain" task in Section B questions (KK3.1.9).

---

## 📝 Internal Documentation (KK3.1.11)

### Example 5 – Header comment (program-level documentation)

```csharp
/*
Program: Student Average Calculator
Author: J. Smith
Date: 12/03/2026
Version: 1.0
Description: Calculates and displays the average of student test scores.
*/
int[] scores = { 70, 85, 90 };
int total = 0;
for (int i = 0; i < scores.Length; i++)
    total += scores[i];
Console.WriteLine("Average: " + total / scores.Length);
```

**Focus:** Header comments provide high-level information about the program.

**Exam link:** "Header comments support maintenance and future development" (KK3.1.11).

---

### Example 6 – Explaining and justifying code logic

```csharp
// Use a FOR loop because the number of scores is known
for (int i = 0; i < scores.Length; i++)
{
    // Accumulate total score for average calculation
    total += scores[i];
}
```

**Focus:** Internal documentation explaining why a structure or decision was chosen.

**Exam link:** "Internal documentation explains and justifies code structures" (KK3.1.11).

---

### Example 7 – Poor vs effective internal documentation

```csharp
// Poor comment – repeats obvious code
print(x); // prints x

// Effective comment – explains purpose
// Display final calculated score to the user
print(x);
```

**Focus:** Comments should not restate what the code already shows.

**Exam link:** Best-practice internal documentation (KK3.1.11).

---

### Example 8 – Placeholder comment (stub for future development)

```csharp
// TODO: Add login authentication feature in next version
// This will validate username and password against stored records
Console.WriteLine("Welcome to the system");
```

**Focus:** Placeholder comments indicate planned future functionality.

**Exam link:** "Stubs are used to mark future development" (KK3.1.11).

---

### Example 9 – Internal documentation for team-based development

```csharp
// Validate score before processing
// Must be between 0 and 100 to prevent invalid averages
if (score < 0 || score > 100)
{
    Console.WriteLine("Invalid score entered");
}
```

**Focus:** Internal documentation supports collaboration, testing and maintenance.

**Exam link:** "Comments assist future programmers and testers" (KK3.1.11).
