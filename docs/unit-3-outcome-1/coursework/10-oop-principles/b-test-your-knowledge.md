# Test Your Knowledge

!!! abstract "Purpose"
    Test your understanding of OOP principles with these practice questions.

---

!!! info "Instructions"
    Answer all questions using precise textbook terminology.

    Marks are awarded for clear explanations, not just naming a principle.

---

## Part A: Multiple-choice questions (1 mark each)

**1. Which statement best describes abstraction?**

A. Preventing direct access to data
B. Creating specialised classes from a general class
C. Focusing only on relevant features and ignoring unnecessary detail
D. Grouping similar classes together

??? note "Answer"
    **C.** Focusing only on relevant features and ignoring unnecessary detail

---

**2. Which principle is primarily concerned with protecting data from unintended modification?**

A. Abstraction
B. Encapsulation
C. Generalisation
D. Inheritance

??? note "Answer"
    **B.** Encapsulation

---

**3. A developer identifies common attributes shared by Car, Truck and Motorcycle and creates a Vehicle class.**

**Which OOP principle is being applied?**

A. Encapsulation
B. Inheritance
C. Abstraction
D. Generalisation

??? note "Answer"
    **D.** Generalisation

---

**4. Which statement about inheritance is correct?**

A. It allows objects to hide unnecessary detail
B. It prevents access to attributes
C. It allows specialised classes to reuse features of a general class
D. It combines data and methods into a single class

??? note "Answer"
    **C.** It allows specialised classes to reuse features of a general class

---

**5. Which relationship best describes inheritance, as defined in the textbook?**

A. has-a
B. uses-a
C. contains-a
D. is-a

??? note "Answer"
    **D.** is-a

---

## Part B: Short-answer questions

**6. Explain what is meant by abstraction in object-oriented programming.** (2 marks)

??? note "Answer"
    Abstraction is the process of identifying the essential features of an object while ignoring unnecessary or irrelevant details. It focuses on what an object does, not how it does it, allowing developers to model real-world entities in a simplified way appropriate for the problem being solved.

---

**7. Describe one advantage of encapsulation.**

**Your answer should refer to data protection or reliability.** (2 marks)

??? note "Answer"
    Encapsulation improves data security and program reliability by restricting direct access to data and ensuring it can only be accessed or modified through controlled methods. This protects data from unintended modification by keeping attributes private and providing public methods to interact with the data.

---

**8. Explain why generalisation can improve the maintainability of a program.** (2 marks)

??? note "Answer"
    Generalisation improves maintainability by identifying common attributes and behaviours shared by multiple classes and creating a general class to represent these features. This reduces duplication of code, meaning changes to shared features only need to be made in one place rather than multiple classes.

---

## Part C: Exam-style application

**9. A system stores information about different types of employees.**

**All employees have a name and employee ID, but only managers have a department.**

a. Identify the OOP principle used to place the shared attributes into one class.

b. Identify the OOP principle that allows the Manager class to be created from the Employee class.

c. Justify your answers.

(4 marks)

??? note "Answer"
    a. Generalisation

    b. Inheritance

    c. Generalisation is used to identify the common attributes (name and employee ID) shared by all employees and create a general Employee class containing these features. This reduces code duplication. Inheritance is then used to create the Manager class from the Employee class, allowing Manager to automatically acquire the shared attributes while adding its own specific attribute (department). This supports code reuse.

---

**10. A student states:**

**"Encapsulation and abstraction mean the same thing because they both hide details."**

**Do you agree or disagree?**

**Justify your response.** (3 marks)

??? note "Answer"
    Disagree. While both principles involve managing complexity, they serve different purposes. Abstraction is about focusing on relevant features and ignoring unnecessary details when modelling an object - it decides what features matter. Encapsulation is about protecting data from unintended modification by restricting direct access and providing controlled methods - it improves data security and reliability. Abstraction is about relevance, while encapsulation is about data protection.

---

## Common mistakes to avoid (examiner patterns)

!!! danger "❌ Common Errors"
    - Describing abstraction as "making code private"
    - Using inheritance when generalisation has not been identified
    - Confusing generalisation with inheritance
    - Describing encapsulation without mentioning data protection

---

## 40+ Exam Tip

!!! success "High-scoring answers clearly link the principle to its purpose."
    Naming the principle alone is rarely sufficient.
