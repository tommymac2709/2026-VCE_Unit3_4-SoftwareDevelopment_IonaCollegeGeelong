# OOP Principles

## Overview

This page demonstrates the four fundamental principles of Object-Oriented Programming:

- **Abstraction** - Focus on relevant features only
- **Encapsulation** - Protect data through controlled access
- **Generalisation** - Identify common features across classes
- **Inheritance** - Create specialised classes from general classes

---

## Quick Reference

!!! tip "When to Use Each Principle"
    - **Abstraction**: When modelling real-world entities - only include attributes and behaviours relevant to your software's purpose
    - **Encapsulation**: When you need to protect data from unintended modification - make attributes private and provide controlled access through methods
    - **Generalisation**: When multiple classes share common attributes or behaviours - create a general class to reduce duplication
    - **Inheritance**: When you need specialised versions of a general class - use inheritance to reuse existing features and add new ones

---

## 1. Abstraction Example

### Student Class (Library System)

A school library system needs to track students for borrowing books. Only relevant information is included.

??? note "Click to view code"
    ```csharp
    public class Student
    {
        public string Name { get; set; } = "";
        public string StudentId { get; set; } = "";
        public int BorrowedBooks { get; set; }
    }
    ```

**What this demonstrates:**
- Only essential attributes are included (name, ID, borrowed books)
- Irrelevant details are excluded (eye colour, favourite food, shoe size)
- The model fits the specific software purpose

---

## 2. Encapsulation Example

### BankAccount Class

A bank account where the balance cannot be changed directly - only through controlled methods.

??? note "Click to view code"
    ```csharp
    public class BankAccount
    {
        private decimal balance; // Private - cannot be accessed directly

        public BankAccount(decimal startingBalance)
        {
            balance = startingBalance;
        }

        // Controlled read access
        public decimal GetBalance()
        {
            return balance;
        }

        // Controlled update with validation
        public void Deposit(decimal amount)
        {
            if (amount > 0)
            {
                balance += amount;
            }
        }

        // Controlled update with validation
        public bool Withdraw(decimal amount)
        {
            if (amount > 0 && amount <= balance)
            {
                balance -= amount;
                return true;
            }
            return false;
        }
    }
    ```

**What this demonstrates:**
- Data (`balance`) and methods are bundled in the same class
- Direct access to `balance` is prevented (private)
- Changes only occur through controlled methods
- Improves reliability and data security

---

## 3. Generalisation Example

### StaffMember Class

Teachers and admin staff share common attributes - place them in one general class.

??? note "Click to view code"
    ```csharp
    public class StaffMember
    {
        public string Name { get; set; } = "";
        public string StaffId { get; set; } = "";
    }
    ```

**What this demonstrates:**
- Common attributes are placed in one class
- Reduces code duplication
- Improves maintainability (changes in one place)

---

## 4. Inheritance Example

### Teacher and AdminStaff Classes

Specialised staff types inherit from the general `StaffMember` class.

??? note "Click to view code"
    ```csharp
    // General class
    public class StaffMember
    {
        public string Name { get; set; } = "";
        public string StaffId { get; set; } = "";
    }

    // Specialised class - inherits from StaffMember
    public class Teacher : StaffMember
    {
        public string Subject { get; set; } = "";
    }

    // Specialised class - inherits from StaffMember
    public class AdminStaff : StaffMember
    {
        public string OfficeLocation { get; set; } = "";
    }
    ```

**What this demonstrates:**
- `Teacher` **is a** `StaffMember` (is-a relationship)
- `AdminStaff` **is a** `StaffMember` (is-a relationship)
- Shared features (`Name`, `StaffId`) are inherited automatically
- Specialised features are added where needed (`Subject`, `OfficeLocation`)

---

## 5. Complete Example - All Principles Together

### Progressive Implementation

This example shows abstraction, encapsulation, generalisation, and inheritance working together.

??? note "Step 1: Abstraction - Model only what matters"
    ```csharp
    public class StaffMember
    {
        public string Name { get; set; } = "";
        public string StaffId { get; set; } = "";
    }
    ```

    **Why this is abstraction:**
    - Only essential attributes included
    - Irrelevant real-world details excluded
    - Model fits the software purpose

??? note "Step 2: Encapsulation - Protect data"
    ```csharp
    public class StaffMember
    {
        private string staffId = "";   // Private (encapsulated)

        public string Name { get; set; } = "";

        // Controlled update
        public void SetStaffId(string id)
        {
            if (id != "")
            {
                staffId = id;
            }
        }

        // Controlled access
        public string GetStaffId()
        {
            return staffId;
        }
    }
    ```

    **Why this is encapsulation:**
    - Data and methods bundled together
    - Direct access to `staffId` prevented
    - Changes only through methods

??? note "Step 3: Generalisation - Shared features"
    ```csharp
    public class StaffMember
    {
        protected string staffId = "";

        public string Name { get; set; } = "";

        public void SetStaffId(string id)
        {
            staffId = id;
        }

        public string GetStaffId()
        {
            return staffId;
        }
    }
    ```

    **Why this is generalisation:**
    - Common attributes in one class
    - Duplication reduced
    - Maintenance simplified

??? note "Step 4: Inheritance - Specialised classes"
    ```csharp
    public class Teacher : StaffMember
    {
        public string Subject { get; set; } = "";
    }

    public class AdminStaff : StaffMember
    {
        public string OfficeLocation { get; set; } = "";
    }
    ```

    **Why this is inheritance:**
    - Specialised classes created from general class
    - Shared features inherited automatically
    - New features added where needed

??? note "Full Working Program"
    ```csharp
    using System;

    // General class with encapsulation
    public class StaffMember
    {
        protected string staffId = "";

        public string Name { get; set; } = "";

        public void SetStaffId(string id)
        {
            staffId = id;
        }

        public string GetStaffId()
        {
            return staffId;
        }
    }

    // Specialised class
    public class Teacher : StaffMember
    {
        public string Subject { get; set; } = "";
    }

    // Specialised class
    public class AdminStaff : StaffMember
    {
        public string OfficeLocation { get; set; } = "";
    }

    class Program
    {
        static void Main()
        {
            // Create a Teacher
            Teacher t1 = new Teacher();
            t1.Name = "Ms Lim";
            t1.SetStaffId("T204");
            t1.Subject = "Mathematics";

            // Create AdminStaff
            AdminStaff a1 = new AdminStaff();
            a1.Name = "Mr Patel";
            a1.SetStaffId("A118");
            a1.OfficeLocation = "Office B3";

            // Display details
            PrintStaffDetails(t1);
            PrintStaffDetails(a1);
        }

        static void PrintStaffDetails(StaffMember staff)
        {
            Console.WriteLine("Name: " + staff.Name);
            Console.WriteLine("ID: " + staff.GetStaffId());
            Console.WriteLine();
        }
    }
    ```

---

## Exam Tips

!!! warning "Key Points for Exams"
    **Abstraction:**
    - "Only relevant features are included; irrelevant details are ignored."
    - About **relevance**, not hiding code

    **Encapsulation:**
    - "Data is protected by restricting direct access and using methods to control changes."
    - About **data protection**, not just grouping code

    **Generalisation:**
    - "Common attributes/behaviours are placed into one general class to reduce duplication."
    - Comes **before** inheritance

    **Inheritance:**
    - "A specialised class inherits attributes/methods from a general class (is-a relationship)."
    - Describes **is-a** relationship, not has-a

!!! success "High-Scoring Structure"
    **identify → explain → link to benefit**

    Example: "Encapsulation is used because data is protected by restricting access, which improves reliability."

---

## How Principles Work Together

The textbook presents these principles as linked, not isolated:

1. **Abstraction** → decide what features matter
2. **Encapsulation** → protect and control those features
3. **Generalisation** → identify common features across classes
4. **Inheritance** → reuse those features in specialised classes
