# c. Practical Examples

---

## Example 1: Using a breakpoint to trace a logic error

A module is designed to calculate the total cost of items purchased.

**Intended logic**
```
totalCost ← quantity * price
```

**Observed problem**

When `quantity = 3` and `price = 10`, the output produced is `0`.

**How a breakpoint helps**

A breakpoint is placed on the line:

```
totalCost ← quantity * price
```

When execution pauses:

- `quantity = 0`
- `price = 10`

**This shows that:**

- The variable `quantity` has not been assigned correctly before the calculation
- The error occurs before the calculation line

!!! tip "Conclusion"
    The breakpoint allows the developer to inspect variable values at runtime and identify where program logic fails.

---

## Example 2: Using debugging statements to track program flow

A developer suspects that a decision structure is not executing as intended.

**Code with debugging statements**
```
Print "Start calculation"

If score ≥ 50 then
    Print "Pass condition met"
    result ← "Pass"
Else
    Print "Fail condition met"
    result ← "Fail"
End If
```

**Program output**
```
Start calculation
Fail condition met
```

**Given that `score = 65`, this output indicates:**

- The condition is being evaluated incorrectly
- The wrong branch of the decision structure is executing

!!! tip "Conclusion"
    Debugging statements confirm which parts of the code are running and help locate logic errors.

---

## Example 3: Constructing relevant test data

A module only accepts values between 1 and 100 inclusive.

**Appropriate test data**

| Type | Values |
|------|--------|
| **Valid** | 1, 50, 100 |
| **Boundary** | 1, 100 |
| **Invalid** | 0, 101 |

**Using this range ensures:**

- Normal operation is tested
- Edge cases are tested
- Error handling is tested

---

## Example 4: Testing table – expected vs actual output

A module calculates the square of a number.

**Testing table**

| Test data | Expected output | Actual output | Pass / Fail |
|-----------|----------------|---------------|-------------|
| 5 | 25 | 25 | Pass |
| 0 | 0 | 0 | Pass |
| -3 | Error message | 9 | Fail |

**Interpretation**

- The module correctly handles valid data
- The module does not handle invalid data correctly
- Debugging is required to correct how negative values are processed

---

## Example 5: Linking testing and debugging

1. **Testing** identifies that the output does not match expectations
2. A **testing table** records the discrepancy
3. **Debugging techniques** (breakpoints or debugging statements) are used
4. The error is corrected
5. The test is re-run to confirm the fix

This cycle continues until all tests pass.

---

## 40+ Exam Insight

!!! warning "Important"
    **Testing tables do not fix errors.**

    They provide evidence that an error exists and justify the need for debugging.
