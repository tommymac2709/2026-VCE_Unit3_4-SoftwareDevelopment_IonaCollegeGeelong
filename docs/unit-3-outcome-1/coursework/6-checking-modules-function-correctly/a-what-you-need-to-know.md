# a. What You Need To Know

!!! info "Key Knowledge - KK 3.1.14"
    Debugging and testing techniques for checking modules function correctly, including:

    - Use of breakpoints
    - Use of debugging statements
    - Construction of relevant test data
    - Test cases comparing expected and actual output in testing tables

---

## What is debugging?

!!! tip "Key Point"
    Debugging is the process of identifying, locating and correcting errors in a software module so that it functions as intended.

**Debugging occurs during development**

It is used after an error has been detected through testing or during execution

Debugging focuses on logic errors and runtime errors, not validation rules

Debugging ensures that individual modules function correctly before being integrated into a complete software solution.

---

## Breakpoints

!!! tip "Key Point"
    A breakpoint is a marker placed at a specific line of code that temporarily halts program execution.

**Breakpoints are used to:**

- Pause execution at a chosen point
- Inspect the current values of variables
- Step through code one line at a time
- Observe how data changes as the program runs

**This allows the developer to:**

- Trace program logic
- Identify where an error first occurs
- Confirm whether a module is behaving as expected

**Breakpoints are especially useful when:**

- A program produces unexpected output
- An error occurs only under certain conditions
- A loop or decision structure behaves incorrectly

---

## Debugging statements

!!! tip "Key Point"
    Debugging statements are temporary output statements added to code to display variable values or execution progress while the program runs.

**They are used to:**

- Display the value of variables at specific points
- Confirm whether sections of code are being executed
- Track changes in data during processing

**Examples include:**

- Printing variable values
- Displaying messages when a branch of code is executed

!!! warning "Important"
    Once the error has been identified and corrected, debugging statements are removed from the final solution.

---

## What is testing?

!!! tip "Key Point"
    Testing is the process of running a module using test data to determine whether it produces the expected output.

**Testing is used to:**

- Confirm that modules function correctly
- Detect errors before a solution is released
- Provide evidence that requirements have been met

!!! warning "Important"
    Testing is not the same as debugging:

    - **Testing** identifies errors
    - **Debugging** fixes errors

---

## Test data

!!! tip "Key Point"
    Test data is data that is deliberately chosen to check whether a module works correctly.

**Relevant test data should include:**

- **Valid data** – data that should be accepted and processed correctly
- **Invalid data** – data that should be rejected or handled safely
- **Boundary data** – data at the limits of acceptable values

**Using a range of test data helps ensure that:**

- The module behaves correctly under normal conditions
- Errors occur where expected
- Edge cases have been considered

---

## Testing tables

!!! tip "Key Point"
    A testing table is used to record and compare the results of testing.

**A testing table typically includes:**

- The test case or test data
- The expected output
- The actual output
- An indication of whether the test passed or failed

**Testing tables are used to:**

- Clearly compare expected and actual results
- Identify discrepancies
- Provide evidence of testing during development

!!! warning "Important"
    If the actual output does not match the expected output:

    - An error exists
    - Debugging is required
    - The test is repeated after corrections are made

---

## Key exam reminders (40+ focus)

!!! info "Remember for Exams"
    - Use "expected output" and "actual output" precisely
    - Do not confuse testing with validation
    - Breakpoints and debugging statements are debugging techniques, not testing techniques
    - Testing tables provide evidence, not fixes
