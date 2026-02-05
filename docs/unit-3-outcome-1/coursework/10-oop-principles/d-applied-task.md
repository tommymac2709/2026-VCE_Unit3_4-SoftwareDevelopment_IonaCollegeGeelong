# Applied Task

!!! abstract "Purpose"
    Apply your knowledge of OOP principles to solve practical problems.

---

!!! info "Instructions"
    Read each scenario carefully.

    Marks are awarded for correct identification of the OOP principle and clear justification using textbook language.

---

## Task 1: Abstraction (4 marks)

A software developer is designing a system to manage car rentals.

**The system needs to:**

- store a car's registration number
- store whether the car is available
- calculate rental costs

**The system does not store:**

- the colour of the driver's clothing
- the driver's favourite music
- the number of doors in the rental office

**a. Identify the OOP principle being applied.** (1 mark)

**b. Explain how this principle is being used in the system.** (3 marks)

---

## Task 2: Encapsulation (5 marks)

A `BankAccount` class stores an account balance.

The balance cannot be changed directly by other parts of the program.

Instead, the balance can only be updated using `deposit()` and `withdraw()` methods.

**a. Identify the OOP principle being applied.** (1 mark)

**b. Explain how this principle improves the reliability or security of the program.** (4 marks)

---

## Task 3: Generalisation (5 marks)

A school system stores information about:

- Teacher
- AdminStaff
- SupportStaff

**All three store:**

- name
- staff ID

**a. Identify the OOP principle used to place the shared attributes into one class.** (1 mark)

**b. Describe how this principle reduces code duplication.** (4 marks)

---

## Task 4: Inheritance (6 marks)

Using the scenario in Task 3, the developer creates a general `StaffMember` class and then creates a `Teacher` class from it.

**a. Identify the OOP principle that allows Teacher to be created from StaffMember.** (1 mark)

**b. Explain how this principle supports code reuse.** (3 marks)

**c. State the relationship between Teacher and StaffMember using correct terminology.** (2 marks)

---

## Task 5: Linking principles together (6 marks)

A developer:

- identifies common attributes across several classes
- places them into one general class
- creates specialised classes from that general class

**a. Identify two OOP principles used in this process.** (2 marks)

**b. Explain how these principles work together to improve maintainability.** (4 marks)

---

## Common mistakes to avoid (examiner patterns)

!!! danger "❌ Common Errors"
    - Saying abstraction means "hiding data"
    - Describing encapsulation without mentioning controlled access
    - Using inheritance without first identifying generalisation
    - Forgetting to describe the is-a relationship

---

## 40+ Exam Tip

!!! success "High-scoring responses always follow this structure:"
    **identify → explain → link to benefit**

    **Example:**

    "Encapsulation is used because data is protected by restricting access, which improves reliability."
