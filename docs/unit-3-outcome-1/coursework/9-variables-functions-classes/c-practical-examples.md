# c. Practical Examples

The examples below demonstrate how local and global variables, constants, functions, methods, classes and objects are used in a real C# program.

!!! info "Note"
    These examples are **illustrative**, not examinable code.

---

## 1. Local vs global variables (with constants)

**Example scenario:** A program tracks student scores and enforces a maximum allowed score.

### Global constant and global variable

```csharp
// Global constant (accessible everywhere, cannot change)
const int MAX_SCORE = 100;

// Global variable (accessible everywhere)
int totalStudents = 0;
```

**Why these are global:**

- `MAX_SCORE` is a **constant** because its value must never change
- `totalStudents` is **global** because it is used across multiple parts of the program

---

### Local variables inside a method

```csharp
void AddStudentScore(int score)
{
    int adjustedScore;   // local variable

    if (score > MAX_SCORE)
    {
        adjustedScore = MAX_SCORE;
    }
    else
    {
        adjustedScore = score;
    }

    totalStudents++;
}
```

!!! info "What this shows"
    **adjustedScore is local:**

    - declared inside the method
    - only exists while the method runs

    **totalStudents is global:**

    - updated inside the method
    - retains its value after the method finishes

!!! tip "📌 Exam link"
    Local variables reduce unintended interference between different parts of a program.

---

## 2. Function example (returns a value)

**Scenario:** The program needs to calculate a student's final mark.

```csharp
int CalculateFinalScore(int testScore, int examScore)
{
    int finalScore = testScore + examScore;
    return finalScore;
}
```

### Using the function

```csharp
int studentResult = CalculateFinalScore(35, 55);
```

!!! info "Why this is a function"
    - It **returns a value**
    - The returned value is **stored in a variable**
    - The result can be **reused elsewhere** in the program

!!! tip "📌 Exam language"
    A function is appropriate because a value must be **returned for further processing**.

---

## 3. Method example (does not return a value)

**Scenario:** The program needs to display a message to the user.

```csharp
void DisplayResult(int score)
{
    Console.WriteLine("Final score: " + score);
}
```

### Using the method

```csharp
DisplayResult(studentResult);
```

!!! info "Why this is a method"
    - It **performs a task**
    - It **does not return a value**
    - It produces an **output** rather than a result for reuse

!!! tip "📌 Exam language"
    A method is appropriate because **no value needs to be returned**.

---

## 4. Function vs method (side-by-side use)

```csharp
int result = CalculateFinalScore(40, 50);  // function
DisplayResult(result);                     // method
```

!!! info "What students should recognise"
    - **Functions** are used for **calculations**
    - **Methods** are used for **procedures or actions**

    This pairing appears frequently in high-scoring SAC solutions.

---

## 5. Class example (blueprint)

**Scenario:** The program stores student details.

```csharp
class Student
{
    public string Name;
    public int Score;

    public void PrintDetails()
    {
        Console.WriteLine(Name + ": " + Score);
    }
}
```

!!! info "What this class defines"
    - **Attributes:** Name, Score
    - **Behaviour:** PrintDetails()

!!! warning "📌 Important"
    A class **does not store real data by itself**.

---

## 6. Object example (instance of a class)

### Creating and using an object

```csharp
Student student1 = new Student();
student1.Name = "Alex";
student1.Score = 85;

student1.PrintDetails();
```

!!! info "What this shows"
    - `student1` is an **object**
    - It is created **from the Student class**
    - It **stores actual values**
    - It can **call the class's methods**

!!! tip "📌 Exam language"
    A class is a **blueprint**; an object is a **specific instance** created from that blueprint.

---

## 7. Putting it all together (mini program flow)

```csharp
const int MAX_SCORE = 100;

Student s = new Student();
s.Name = "Jordan";

int rawScore = CalculateFinalScore(45, 60);

if (rawScore > MAX_SCORE)
{
    s.Score = MAX_SCORE;
}
else
{
    s.Score = rawScore;
}

s.PrintDetails();
```

!!! info "This short example demonstrates"
    ✅ a constant

    ✅ a function

    ✅ a class

    ✅ an object

    ✅ a method

    ✅ local and global scope

---

## Summary comparison table

| Feature | Example from above | Key characteristic |
|---------|-------------------|-------------------|
| **Global constant** | `MAX_SCORE` | Accessible everywhere, cannot change |
| **Global variable** | `totalStudents` | Accessible everywhere, can change |
| **Local variable** | `adjustedScore` | Limited scope, temporary |
| **Function** | `CalculateFinalScore()` | Returns a value |
| **Method** | `DisplayResult()` | Performs task, no return value |
| **Class** | `Student` | Blueprint defining attributes & behaviours |
| **Object** | `student1` | Instance with actual data |

---

## Quick reference: When to use what

!!! tip "Decision guide"
    **Use a constant when:**

    - The value must never change (e.g., MAX_SCORE, TAX_RATE)

    **Use a local variable when:**

    - The data is only needed within one function/method
    - You want to limit scope and reduce errors

    **Use a global variable when:**

    - Multiple parts of the program need access to the same data
    - (But use sparingly due to debugging risks)

    **Use a function when:**

    - You need to calculate and return a value

    **Use a method when:**

    - You need to perform an action without returning a value

    **Use a class when:**

    - You need a blueprint for creating multiple similar objects

    **Use an object when:**

    - You need to store and work with specific data instances
