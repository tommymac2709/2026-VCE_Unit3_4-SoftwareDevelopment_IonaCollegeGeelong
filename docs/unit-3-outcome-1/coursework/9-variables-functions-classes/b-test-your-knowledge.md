# b. Test Your Knowledge

---

## Part A: Multiple-choice questions (1 mark each)

### Question 1

Which statement best describes a local variable?

A. It can be accessed anywhere in the program

B. It exists for the entire execution of the program

C. It is declared inside a function or method and has limited scope

D. It cannot change once assigned

??? note "Answer"
    **C. It is declared inside a function or method and has limited scope**

    A local variable is declared inside a function or method, can only be accessed within that function or method, and exists only while that function or method is executing.

---

### Question 2

Why are constants preferred over variables for fixed values such as tax rates or file paths?

A. They reduce memory usage

B. They allow values to change dynamically

C. They improve reliability and prevent accidental modification

D. They are only accessible within one function

??? note "Answer"
    **C. They improve reliability and prevent accidental modification**

    Constants cannot be changed once assigned, which prevents accidental modification and improves the reliability and maintainability of the program.

---

### Question 3

Which feature distinguishes a function from a method, according to the textbook?

A. A function is always shorter

B. A function is always part of a class

C. A function returns a value

D. A function uses selection structures

??? note "Answer"
    **C. A function returns a value**

    The key distinction is that a function returns a value to the part of the program that called it, while a method does not return a value.

---

### Question 4

Which statement about global variables is correct?

A. They can only be accessed inside one method

B. They reduce the risk of unintended data changes

C. They can be accessed by any part of the program

D. They are automatically constants

??? note "Answer"
    **C. They can be accessed by any part of the program**

    Global variables are declared outside all functions and methods and can be accessed by any part of the program. They exist for the entire duration of program execution.

---

### Question 5

Which pairing is correct?

A. Class → specific instance

B. Object → blueprint

C. Class → defines attributes and behaviours

D. Object → cannot call methods

??? note "Answer"
    **C. Class → defines attributes and behaviours**

    A class is a blueprint used to define attributes (data) and behaviours (methods). An object is a specific instance created from the class.

---

## Part B: Short-answer questions

### Question 6

State one advantage of using local variables instead of global variables. (1 mark)

??? note "Answer"
    **1 mark:** Local variables limit access to data, reducing unintended changes and making programs easier to debug and maintain.

    (Accept: Local variables reduce the risk of accidental data modification / Local variables have limited scope / Local variables make debugging easier)

---

### Question 7

Explain why a constant improves the maintainability of a program. (2 marks)

??? note "Answer"
    **2 marks:** A constant represents a fixed value that cannot be changed once assigned. If the value needs to be updated (e.g., a tax rate changes), it only needs to be changed in one place (the constant declaration), rather than searching through the entire program to find all occurrences of that value.

    **1 mark:** Partial explanation (e.g., mentions that constants can't be changed but doesn't explain how this helps maintainability, or mentions updating values but not the centralization benefit)

    **Key elements for full marks:**
    - Constants prevent accidental changes
    - Changes only need to be made in one place
    - Improves reliability/maintainability

---

### Question 8

Identify whether each of the following should be implemented as a function or a method, and justify your choice:

**a.** Calculating the average score of a student

**b.** Displaying a confirmation message to the user

(4 marks)

??? note "Answer"
    **4 marks - Full response:**

    **a.** Function. A function should be used because a value (the average) must be returned for further processing or use in the program. (2 marks)

    **b.** Method. A method should be used because the task is to display output, which does not require returning a value to the calling code. (2 marks)

    **1 mark each:** Correct identification without justification

    **Key elements for full marks:**
    - Identifies function for (a) and method for (b)
    - Justifies based on whether a value is returned
    - Links to the specific purpose (calculation vs display)

---

## Part C: Exam-style application

### Question 9

A program stores a maximum allowed number of login attempts and checks this value in multiple parts of the program.

**a.** Identify the most appropriate feature to store this value.

**b.** Justify your answer.

(3 marks)

??? note "Answer"
    **3 marks - Full response:**

    **a.** Constant

    **b.** A constant is appropriate because the maximum number of login attempts is a fixed value that should not change during program execution. Using a constant prevents accidental modification and improves reliability. Since multiple parts of the program need access to this value, a constant ensures consistency across the program.

    **2 marks:** Correct feature with partial justification (e.g., mentions it's fixed but not the benefits, or mentions reliability but not the fixed nature)

    **1 mark:** Correct feature with minimal justification

    **Key elements for full marks:**
    - Identifies constant
    - States the value is fixed/shouldn't change
    - Mentions benefit (prevents modification, improves reliability, ensures consistency)
    - References the context (multiple parts of program)

---

### Question 10

A developer creates a Car class and then creates an object called myCar.

**a.** Identify which is the class and which is the object.

**b.** Explain the difference between a class and an object.

(3 marks)

??? note "Answer"
    **3 marks - Full response:**

    **a.** `Car` is the class, `myCar` is the object. (1 mark)

    **b.** A class is a blueprint or template that defines the attributes and behaviours that objects of that type will have. An object is a specific instance created from the class that stores actual data values. The class describes what an object will have and can do, but the object is the actual entity that exists in memory. (2 marks)

    **1 mark for (b):** Partial explanation (e.g., states class is a blueprint but doesn't explain what an object is, or vice versa)

    **Key elements for full marks:**
    - Correctly identifies Car as class and myCar as object
    - Explains class as blueprint/template
    - Explains object as instance with actual data
    - Shows relationship between class and object

---

## Common mistakes to avoid (examiner patterns)

!!! warning "Don't Make These Mistakes"
    ❌ Saying a method "returns a value"

    ❌ Describing a global variable as safer than a local variable

    ❌ Confusing a class with an object

    ❌ Using programming-language-specific terms instead of textbook language

---

## 40+ Exam Tip

!!! tip "Always link your answer to purpose"
    Examiners reward explanations that **justify why** a feature is used, not just **what** it is.
