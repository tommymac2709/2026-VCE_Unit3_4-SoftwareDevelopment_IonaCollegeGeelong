# d. Applied Task

## 🧑‍💻 VCE Software Development – Student Task Sheet

**Unit 3 Outcome 1 – Naming Conventions, Internal Documentation, Debugging and Testing**

---

## Scenario

You are part of a development team creating a school event booking system.

The software allows students to:

- enter their name
- select the number of tickets
- calculate and display the total cost

The project will be maintained by multiple programmers over time.

---

## 🔹 Task 1 – Naming Conventions

(6 marks)

A section of code from the system is shown below.

```
int x = 3;
double y = 12.50;
double z = x * y;
Console.WriteLine(z);
```

**a.** Rename all variables using camel case so that their purpose is clear.

(3 marks)

**b.** Rename the same variables using Hungarian notation.

(3 marks)

---

## 🔹 Task 2 – Explaining Naming Convention Choices

(4 marks)

Explain two reasons why consistent naming conventions are important when developing software in a team environment.

Your response should refer to:

- readability
- maintenance
- debugging
- collaboration

---

## 🔹 Task 3 – Internal Documentation

(6 marks)

The following code calculates and displays the total cost of tickets.

```
int ticketCount = 4;
double ticketPrice = 15.00;
double total = ticketCount * ticketPrice;
Console.WriteLine("Total cost: $" + total);
```

**a.** Add a header comment for this program.

Your comment should include:

- program purpose
- author
- date

(3 marks)

**b.** Add two internal comments that explain or justify the code logic.

Avoid comments that simply repeat what the code does.

(3 marks)

---

## 🔹 Task 4 – Placeholder Comments (Stubs)

(4 marks)

The system will later be extended to:

- apply a discount for students
- validate user input

**a.** Write two placeholder comments indicating where these future features will be added.

(2 marks)

**b.** Explain why placeholder comments are useful during software development.

(2 marks)

---

## 🔹 Task 5 – Applied Reasoning (Exam-style)

(5 marks – Section C style)

A student claims:

> "Internal documentation is unnecessary because it does not affect how fast the program runs."

Explain why this statement is incorrect.

Your answer should refer to:

- the role of the compiler
- maintenance
- future development

---

!!! info "🧠 Examiner-style Marking Guidance"
    High-scoring responses will:

    - Use correct terminology: camel case, Hungarian notation, readability, maintainability
    - Avoid vague statements such as "makes it better"
    - Explain why, not just what
    - Clearly distinguish between code functionality and code maintenance
