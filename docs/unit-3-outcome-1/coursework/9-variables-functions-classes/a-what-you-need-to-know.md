# a. What You Need To Know

!!! info "Key Knowledge - KK 3.1.8"
    Features of a programming language, including:

    - Local and global variables, and constants
    - Functions and methods
    - Classes and objects

---

## Local and global variables

!!! tip "Key Point"
    A **variable** is a named memory location used to store data that may change while a program runs.

### Local variables

!!! tip "Local Variable Definition"
    A local variable:

    - is declared inside a function or method
    - can only be accessed within that function or method
    - exists only while that function or method is executing

**Local variables are used to:**

- limit access to data
- reduce unintended changes
- make programs easier to debug and maintain

---

### Global variables

!!! tip "Global Variable Definition"
    A global variable:

    - is declared outside all functions and methods
    - can be accessed by any part of the program
    - exists for the entire duration of program execution

**Global variables are useful when:**

- many parts of a program need access to the same data

**However, overuse of global variables can:**

- make programs harder to debug
- increase the risk of accidental data modification

---

## Constants

!!! tip "Key Point"
    A **constant** is a named value that cannot be changed once it has been assigned.

**Constants are used to:**

- represent fixed values (e.g. tax rates, limits, file paths)
- improve readability
- prevent accidental changes
- make maintenance easier

!!! info "📌 Exam language tip"
    Constants improve **reliability** and **maintainability** of a program.

---

## Functions and methods

!!! tip "Key Point"
    Functions and methods are **modules of code** used to break a program into smaller, manageable parts.

**This improves:**

- modularity
- reuse of code
- readability

---

### Function (textbook definition)

!!! tip "Function Definition"
    A function is a module of code that:

    - performs a specific task
    - **returns a value** to the part of the program that called it

**Functions are used when:**

- a result is needed for further processing
- a calculation must be reused
- a value must be tested in a condition

**Example: Function (pseudocode)**

```
ALGORITHM checkUmbrellaUsage()
BEGIN
    INPUT isRaining
    INPUT hasUmbrella

    IF isRaining = True THEN
        IF hasUmbrella = True THEN
            RETURN useUmbrella()
        ELSE
            RETURN getWet()
        ENDIF
    ENDIF

    RETURN False
END
```

!!! warning "📌 Why this is a function (exam tooltip)"
    - It uses **RETURN** statements
    - A value is sent back to the calling code
    - The result can be stored or used in a decision

!!! info "📘 Textbook note"
    Functions in pseudocode use parentheses after their name (e.g. `checkUmbrellaUsage()`), even when there are no input parameters.

---

### Method (textbook definition)

!!! tip "Method Definition"
    A method is a module of code that:

    - performs a task
    - **does not return a value**

**Methods are commonly used to:**

- display output
- update data
- carry out procedures

**Methods are often associated with:**

- classes
- objects
- object-oriented programs

---

### Function vs method (very examinable)

| Feature | Function | Method |
|---------|----------|--------|
| Returns a value | ✅ Yes | ❌ No |
| Performs a task | ✅ Yes | ✅ Yes |
| Used in expressions | ✅ Yes | ❌ No |
| Common exam use | Calculations | Procedures |

!!! warning "📌 Examiner focus"
    If a value must be **returned**, a **function** should be used.

    If no value is required, a **method** is appropriate.

---

## Classes and objects

### Class

!!! tip "Class Definition"
    A **class** is a blueprint used to define:

    - **attributes** (data)
    - **behaviours** (methods)

A class describes what an object will have and what it can do, but **it is not the object itself**.

---

### Object

!!! tip "Object Definition"
    An **object** is an instance of a class.

**Objects:**

- are created from a class
- store actual data values
- use the methods defined by the class

---

### Class vs object (exam language)

| Term | Meaning |
|------|---------|
| **Class** | Template or blueprint |
| **Object** | A specific instance created from the class |

**Example:**

- `Student` → class
- `student1` → object

---

## Why these features matter (exam link)

These programming language features help developers:

- organise code logically
- reduce repetition
- improve maintainability
- create scalable solutions

---

## 40+ Exam reminders

!!! tip "Remember"
    - **Local variables** have limited scope
    - **Global variables** have program-wide scope
    - **Constants** prevent accidental data changes
    - **Functions** return values
    - **Methods** do not return values
    - **Classes** define structure; **objects** store real data
