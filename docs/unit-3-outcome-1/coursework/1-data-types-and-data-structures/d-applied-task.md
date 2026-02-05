# d. Applied Task

## 🧑‍💻 VCE Software Development – Student Task Sheet

**Unit 3 Outcome 1 – Data Types and Data Structures (KK 3.1.4 & 3.1.5)**

Based on Nelson/Cengage 2nd Ed. Chapter 1 – Introduction to Programming

---

## 🔹 Task 1 – Choosing the right data type

**Context:**

You are developing a program to manage a small gym's membership system.

**Instructions:**

1. Declare three variables to store:
    - member's name
    - membership fee
    - whether the member has paid (true/false).
2. Write pseudocode that prints a message such as:
   ```
   Welcome Jordan – Membership paid: True
   ```
3. Modify your pseudocode so the membership fee is shown to two decimal places.
4. In a short comment, justify why you selected each data type.

---

## 🔹 Task 2 – Working with Boolean logic

**Context:**

The gym has restricted access between 9 p.m. and 5 a.m.

**Instructions:**

1. Create Boolean variables for isStaff, hasPass, and afterHours.
2. Use a decision structure to print:
    - "Access granted" only if the user is staff and has a pass; otherwise "Access denied".
3. Add one extra logical condition that restricts entry after hours.
4. Comment each conditional statement with a plain-English explanation.

---

## 🔹 Task 3 – Array of daily steps

**Context:**

A fitness tracker app records the number of steps each day for a week.

**Instructions:**

1. Create an integer array named steps containing seven values.
2. Calculate and print:
    - the total steps
    - the average steps per day.
3. Add a statement to print "Goal achieved!" if the average ≥ 10 000.
4. Comment on how the index is used to access array elements.

---

## 🔹 Task 4 – Two-dimensional data

**Context:**

You are collecting temperature readings (°C) for three days, morning and afternoon.

**Instructions:**

1. Create a two-dimensional array temps[3,2].
2. Store six temperature values of your choice.
3. Display output in this format:
   ```
   Day 1: AM – 18°C, PM – 23°C
   Day 2: AM – …
   ```
4. Add code that calculates and prints the average temperature across all readings.

---

## 🔹 Task 5 – Record structure (class)

**Context:**

A gym wants to store information about each member: name, age, and active status.

**Instructions:**

1. Define a Member class with the three fields above.
2. Create two Member objects and assign them values.
3. Use Console.WriteLine() to display each member's details in one line.
4. Add one Boolean field isTrainer and display a message if the member is a trainer.

---

## 🔹 Task 6 – Array of records

**Context:**

You are extending the gym system to manage multiple members.

**Instructions:**

1. Create an array of five Member objects.
2. Populate the array with sample data (names, ages, active status).
3. Use a loop to print only the active members.
4. Add code that counts how many members are active and prints the total.
