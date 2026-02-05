# a. What You Need To Know

## Naming Conventions (KK 3.1.9)

A naming convention is an agreed and consistent set of rules used to name solution elements such as variables, functions, methods, classes, objects and interface controls.

The purpose of naming conventions is to make source code readable, meaningful and maintainable, allowing programmers to quickly understand the purpose (and sometimes the data type or structure) of each element.

### Good naming conventions:

- improve code readability and clarity
- support debugging, as variables and controls are easier to identify
- enhance maintainability, especially when code is modified by another programmer
- reduce misunderstandings when working in teams

---

## Common Naming Conventions

### Camel Case

- Words are joined together with no spaces or punctuation
- Each word after the first begins with a capital letter
- Focuses on describing the purpose of the element

**Examples:**

`firstName`, `calculateTotal`, `btnSubmit`

Camel case is widely used in modern programming languages, particularly dynamically typed languages, and is one of the most common conventions used in VCE Software Development.

---

### Snake Case

- Words are joined using underscores
- All letters are typically lowercase
- Improves readability by clearly separating words

**Examples:**

`first_name`, `total_score`, `snake_case`

Snake case is often preferred by programmers who value visual clarity, as each word is clearly separated.

---

### Hungarian Notation

- Uses a lowercase prefix to indicate the data type or structure
- Followed by a camel-case style name describing the purpose
- Prefixes are programmer-defined but meaningful

**Examples:**

- `iNumStudents` (integer)
- `arrScores` (array)
- `strName` (string)
- `btnCalculate` (button)

Hungarian notation is useful in languages that are not dynamically typed, as it immediately communicates the data type or structure being used.

However, it is used less frequently in modern programming due to the prevalence of dynamically typed languages.

---

## Internal Documentation (KK 3.1.11)

Internal documentation refers to the comments and notes written within source code by the developer.

Its purpose is to explain, justify or clarify how the code works for future or new programmers, supporting long-term code maintenance.

### Internal documentation:

- explains why certain data types, structures or algorithms were chosen
- supports maintenance and modification of code over time
- allows programmers to understand code they did not originally write
- has no impact on efficiency or execution, as comments are ignored by the compiler

---

## Purposes of Internal Documentation

### Explaining and justifying code and data structures

Helps programmers understand complex logic, algorithms or design decisions.

### Supporting code maintenance

Makes it easier to update, debug or extend the program without re-analysing the entire solution.

### Placeholder comments (stubs)

Used to indicate future development, such as features or methods that will be implemented later.

---

## Internal Documentation Best Practices

Effective internal documentation should be:

### Relevant and meaningful

Comments should add information that is not already obvious from the code.

### Short and concise

Avoid excessive or verbose comments that clutter the code.

### Non-trivial

Comments should not simply restate what the code already clearly shows.

**Example of poor documentation:**

```
print(x) // prints x
```

### Structured, including:

- Header comments at the top of a program or module (program description, author, date created, version)
- Comments describing functions, methods and parameters
- Clear notes for complex algorithms
- Placeholder comments for future enhancements

Well-written internal documentation, combined with meaningful naming conventions, is a core feature of efficient and maintainable software solutions.

---

!!! tip "🧠 Exam Tip (Very Important)"
    In VCAA exams:

    - Naming conventions are often assessed through explain / justify questions
    - Internal documentation is commonly linked to maintenance, teamwork and future development
    - Avoid saying comments "help beginners" — instead say they support maintenance, future developers, or modifying existing code
