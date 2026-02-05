# b. Test Your Knowledge

**Debugging and Testing Techniques (KK3.1.14)**

Answer the following questions using VCAA terminology. Where appropriate, use full sentences and correct technical language.

---

## Part 1: Knowledge recall (1 mark each)

### Question 1
Define the term debugging as it applies to software development.

??? note "Answer"
    Debugging is the process of identifying, locating and correcting errors in a software module so that it functions as intended.

---

### Question 2
What is the purpose of using a breakpoint during program execution?

??? note "Answer"
    A breakpoint temporarily halts program execution at a specific line, allowing the developer to inspect variable values and trace program logic to identify errors.

---

### Question 3
State one reason why debugging statements are removed once development is complete.

??? note "Answer"
    Debugging statements are temporary tools used during development and should be removed to keep the final code clean and professional. (Accept: They are not needed in production code / They clutter the output / They are only for development purposes)

---

### Question 4
Identify the key difference between testing and debugging.

??? note "Answer"
    Testing identifies errors by comparing expected and actual output, while debugging locates and corrects those errors.

---

## Part 2: Understanding and explanation (2 marks each)

### Question 5
Explain how using breakpoints can help a developer identify a logic error in a module.

??? note "Answer"
    **2 marks:** A breakpoint pauses execution at a specific line, allowing the developer to inspect variable values at that point. This helps identify where values become incorrect or where program logic fails to execute as intended.

    **1 mark:** Partial explanation (e.g., only mentions pausing execution OR only mentions checking values)

---

### Question 6
Describe how debugging statements assist in tracing the flow of execution through a program.

??? note "Answer"
    **2 marks:** Debugging statements display messages or variable values as the program runs, confirming which sections of code are executed and in what order. This helps identify if a particular branch or loop is being reached correctly.

    **1 mark:** Partial explanation (e.g., only mentions displaying output OR only mentions confirming execution)

---

### Question 7
Explain why it is important to test modules using more than one type of test data.

??? note "Answer"
    **2 marks:** Different types of test data (valid, invalid, boundary) check different aspects of the module. Valid data confirms normal operation, invalid data checks error handling, and boundary data identifies errors at the limits of acceptable values.

    **1 mark:** Mentions need for different types but doesn't explain why each is important

---

## Part 3: Application and exam-style questions

### Question 8
A developer runs a module and the output produced does not match the expected output.

a. What process should occur first: testing or debugging?

b. Justify your answer.

??? note "Answer"
    **a.** Debugging

    **b.** Testing has already occurred (the module was run and output compared to expected output). Now debugging is required to locate and correct the error that was identified during testing. (2 marks for clear justification)

---

### Question 9
Consider the following testing table entry:

| Test data | Expected output | Actual output |
|-----------|----------------|---------------|
| 10 | 100 | 0 |

a. What does the testing table indicate about the module?

b. What should the developer do next?

??? note "Answer"
    **a.** The module is producing incorrect output (actual output does not match expected output), indicating an error exists. (1 mark)

    **b.** The developer should use debugging techniques (such as breakpoints or debugging statements) to locate and correct the error, then retest the module. (1-2 marks depending on detail)

---

### Question 10
A student claims that adding a message to display a variable's value is a testing technique.

Do you agree or disagree?

Justify your response using correct terminology.

??? note "Answer"
    **Disagree.** Adding messages to display variable values is a debugging statement, which is a debugging technique, not a testing technique. Testing involves running a module with test data and comparing expected and actual output. (2 marks for clear disagreement with correct terminology)

---

## Part 4: Exam traps (read carefully)

### Question 11
A program correctly rejects invalid input but produces incorrect calculations for valid input.

Which of the following best describes the situation?

A. Validation has failed

B. Testing has failed

C. Debugging is required

D. The module is complete

(Circle the correct option and justify your choice.)

??? note "Answer"
    **C. Debugging is required**

    **Justification:** The program correctly handles validation (rejects invalid input), but testing has revealed an error in the calculation logic. Debugging is needed to locate and fix this error. (2 marks)

    **Why not the others:**
    - A is incorrect: validation is working correctly
    - B is incorrect: testing has succeeded (it identified the problem)
    - D is incorrect: there is an error that needs fixing

---

## 40+ Exam Tip

!!! warning "Important"
    - If a question mentions **expected vs actual output**, the examiner is testing your understanding of **testing**, not validation.
    - If a question asks how an error is **found or corrected**, it is almost always **debugging**.
