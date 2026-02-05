# d. Applied Task

## Scenario

A software module is designed to calculate the final price of an item after applying a discount.

**Module rules**

**Input:**

- `price` (must be between $1 and $500)
- `discountRate` (must be between 0 and 0.5)

**Calculation:**

```
finalPrice ← price − (price × discountRate)
```

---

## Task 1: Construct relevant test data (6 marks)

Create three test cases that would be appropriate for testing this module.

Your test data must include:

- at least one valid test case
- at least one boundary test case
- at least one invalid test case

Complete the table below.

| Test case | price | discountRate | Type of data |
|-----------|-------|--------------|--------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## Task 2: Testing table – expected vs actual output (6 marks)

The developer runs the module using your test data and records the following results.

Complete the testing table by:

- calculating the expected output
- comparing it to the actual output
- identifying whether each test passes or fails

| Test case | Expected output | Actual output | Pass / Fail |
|-----------|-----------------|---------------|-------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## Task 3: Debugging analysis (4 marks)

One of the test cases fails.

**a.** Explain how testing identified that an error exists.

**b.** Describe one debugging technique that could be used to locate the error.

**c.** Explain what the developer would look for when using this debugging technique.

---

## Task 4: Reflection (4 marks)

Explain why it is important to:

- use testing tables during development, and
- apply debugging techniques after an error has been identified.

Your response must refer to expected output and actual output.

---

## What a 40+ response looks like

!!! tip "High-scoring responses will:"
    - Use correct VCAA terminology consistently
    - Clearly distinguish between testing and debugging
    - Select appropriate test data, not random values
    - Explicitly compare expected vs actual output
    - Describe debugging techniques in terms of what they reveal, not just what they are

---

## Common mistakes to avoid

!!! warning "Don't do this:"
    - Confusing validation with testing
    - Saying debugging "checks input data"
    - Failing to justify test data choices
    - Describing debugging without linking it to the identified error
