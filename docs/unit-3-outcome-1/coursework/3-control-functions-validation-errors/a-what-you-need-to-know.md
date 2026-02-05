# a. What You Need To Know

## Instructions and Control Structures

Control structures determine the flow of execution in code. There are three fundamental control structures in programming: sequences, selections and iterations.

---

## Arithmetic, logical and conditional operators

Arithmetic, logical and conditional operators are fundamental concepts in programming, each serving a distinct purpose in manipulating data and controlling the flow of execution in code.

### Arithmetic operators

Arithmetic operators are used to perform mathematical operations. They are similar to the operations performed in basic mathematics and are used to manipulate numerical values.

| Operator | Description | Example | Result if a=10, b=5 |
| --- | --- | --- | --- |
| + | Addition | a + b | 15 |
| - | Subtraction | a - b | 5 |
| * | Multiplication | a * b | 50 |
| / | Division | a / b | 2 |
| % | Modulus (Remainder) | a % b | 0 |

---

### Logical operators

Logical operators are used to perform logical operations, primarily in selection statements, to determine the truthfulness of an expression. They are used to combine or invert Boolean values (true or false).

| Operator | Description | Example | Result if condition1 = true, condition2 = false |
| --- | --- | --- | --- |
| && | Logical AND | condition1 && condition2 | false |
| \|\| | Logical OR | condition1 \|\| condition2 | true |
| ! | Logical NOT | !condition1 | false |

---

### Conditional operators

Conditional operators are used to compare two values or expressions. They are fundamental in control structures such as selections and iterations, as they help in decision-making processes by evaluating conditions.

| Operator | Description | Example | Result if a=10, b=5 |
| --- | --- | --- | --- |
| == | Equal to | a == b | false |
| != | Not equal to | a != b | true |
| > | Greater than | a > b | true |
| < | Less than | a < b | false |
| >= | Greater than or equal to | a >= b | true |
| <= | Less than or equal to | a <= b | false |

---

## Control structures

!!! tip "Key Point"
    There are **three fundamental control structures** in programming: sequences, selections and iterations.

### Sequence

A sequence is a set of instructions that executes line by line, a little bit like a recipe. Every line of code in the sequence is run in the order that it is written.

---

### Selection - IF if (3 > 2) … DO SOMETHING

A selection statement is a control structure that allows a programmer to write lines of code that are only run when a particular requirement is met. The code within a selection statement can contain instructions, sequences, other selection statements or iterations. Selections are Boolean, in that they are run based on the result of a condition being evaluated as either true or false. If the condition evaluates as 'true', the code within that selection statement is executed. If it evaluates as 'false', it is not executed.

!!! tip "Key Point"
    Selections are **Boolean** - they run based on a condition being evaluated as either **true or false**.

**Alternative execution ELSE-IF:** Another form of a selection statement involves an alternative execution. This means that if the condition is not met, alternative code will run.

**Nested selection:** Selection statements can also be placed inside each other. This type of selection is referred to as a nested selection. This control structure is useful when multiple conditions must be handled within the code.

---

### Iteration

#### WHILE

A WHILE iteration is a section of code that is run when, and for as long as, a condition is met. These types of iterations are useful when the programmer does not know when the condition might be met, such as when running sections of code based on user input that will only cease when a user inputs a particular key sequence.

**Key elements of WHILE iterations:**

- They are used when it is unknown how many times the iteration will execute.
- The condition being tested within the WHILE iteration must be met at least once for the code within it to be executed; this acts as a pre-test iteration.
- If the condition being tested within the WHILE iteration is always true, the iteration will never terminate; this creates an infinite loop.

---

#### DO/WHILE

A DO/WHILE iteration is similar to a WHILE iteration in that it executes code within the iteration for as long as a condition is met.

The difference between a WHILE and a DO/WHILE is that a WHILE iteration may not run if the condition being tested is never true, whereas a DO/WHILE iteration always runs at least once; this is referred to as a post-test iteration.

!!! info "WHILE vs DO/WHILE"
    **WHILE:** Pre-test iteration - may not run at all if condition is initially false
    **DO/WHILE:** Post-test iteration - always runs **at least once**

**Key elements of DO/WHILE iterations:**

- They are used when it is unknown how many times the iteration will execute.
- The code within the DO/WHILE iteration will always execute at least once.
- If the condition being tested within the DO/WHILE iteration is always true, the iteration will never terminate; this creates an infinite loop.

---

#### FOR

A FOR iteration is a section of code that is run a predefined number of times. These types of iterations are particularly useful to perform an action on every element of an array, or to perform a basic search through a set of elements in a data structure. FOR iterations need three pieces of information to execute. The first is a starting point, the second is the end condition, and the third is a statement called an increment that increases the starting point so that it approaches the end condition.

**Key elements of FOR iterations:**

- The iteration runs for a set number of times and this must be known beforehand.
- The iteration will only execute the code inside it if the end condition is being met; it may not execute the code at all.
- Unlike WHILE and DO/WHILE iterations, it is very rare for a FOR iteration to not terminate; this occurs only if the increment and end condition are unrelated. This type of occurrence would be considered a logic error.

---

## Validation Techniques

Validation techniques ensure data meets specific criteria before processing.

**Existence checking:** Verifies that required data has been provided and is not empty or null.

**Type checking:** Confirms that data is of the correct data type (e.g., numeric, text, Boolean) for its intended use.

**Range checking:** Ensures that numeric or date values fall within acceptable minimum and maximum boundaries.

!!! warning "Order Matters"
    Validation must be performed in order: **Existence → Type → Range**. Check data exists before checking its type, and check type before checking range.

---

## Types of Errors

Errors in programming can be categorized into three main types:

### Syntax errors

Syntax errors occur when code violates the grammatical rules of the programming language. The program cannot be compiled or executed until these are corrected.

### Logic errors

Logic errors occur when the program runs without crashing but produces incorrect results due to flawed reasoning or incorrect implementation of the intended algorithm.

### Runtime errors

Runtime errors occur during program execution when an operation cannot be completed. Common runtime errors include:

- **Overflow:** When a calculation produces a result too large for the data type to store
- **Index out of range:** When attempting to access an array element using an invalid index value
- **Type mismatch:** When an operation is performed on incompatible data types
- **Divide by zero:** When attempting to divide a number by zero, which is mathematically undefined

!!! info "Distinguishing Error Types"
    **Syntax:** Won't compile/run at all
    **Logic:** Runs but wrong output
    **Runtime:** Crashes during execution
