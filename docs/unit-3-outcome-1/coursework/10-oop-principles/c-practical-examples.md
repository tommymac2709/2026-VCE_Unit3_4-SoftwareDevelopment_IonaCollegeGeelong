# Practical Examples

!!! abstract "Purpose"
    See OOP principles in action through C# code examples.

---

These examples use simple C# to demonstrate abstraction, encapsulation, generalisation and inheritance in the same way the textbook describes them. Keep your focus on the principle being shown.

---

## 1. Abstraction (focus on what is relevant)

**Scenario**

A school system needs to store only the details required to manage library borrowing.

✅ **Relevant features for this problem:**

- Student name
- Student ID
- Borrowed book count

❌ **Not relevant (so excluded by abstraction):**

- eye colour
- favourite food
- shoe size

??? note "C# example (abstracted model)"
    ```csharp
    public class Student
    {
        public string Name { get; set; } = "";
        public string StudentId { get; set; } = "";
        public int BorrowedBooks { get; set; }
    }
    ```

!!! info "What this shows"
    - The class includes only the features needed for the specific software purpose.
    - This is **abstraction**: modelling reality with only essential details.

---

## 2. Encapsulation (bundle + restrict access)

**Scenario**

A bank account must prevent the balance being changed directly by other parts of the program.

??? note "C# example (encapsulation)"
    ```csharp
    public class BankAccount
    {
        private decimal balance; // private data (cannot be changed directly outside the class)

        public BankAccount(decimal startingBalance)
        {
            balance = startingBalance;
        }

        public decimal GetBalance()
        {
            return balance; // controlled access (read-only through a method)
        }

        public void Deposit(decimal amount)
        {
            if (amount > 0)
            {
                balance += amount; // controlled update
            }
        }

        public bool Withdraw(decimal amount)
        {
            if (amount > 0 && amount <= balance)
            {
                balance -= amount; // controlled update
                return true;
            }

            return false;
        }
    }
    ```

!!! info "What this shows"
    - Data (`balance`) and behaviour (methods) are bundled in the same class.
    - Direct access to the `balance` is restricted.
    - Changes only occur through controlled methods → improves reliability and protects data.

---

## 3. Generalisation (identify common features)

**Scenario**

A program stores details for different staff types:

- Teacher
- AdminStaff

Both share common data such as:

- Name
- Staff ID

So we create a general class.

??? note "C# example (generalisation)"
    ```csharp
    public class StaffMember
    {
        public string Name { get; set; } = "";
        public string StaffId { get; set; } = "";
    }
    ```

!!! info "What this shows"
    - Shared attributes are placed into one general class.
    - This reduces duplication and improves maintainability.

---

## 4. Inheritance (specialised classes reuse the general class)

**Scenario**

A Teacher is a type of StaffMember, but has extra attributes (e.g. subject).

??? note "C# example (inheritance)"
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

!!! info "What this shows"
    - `Teacher` and `AdminStaff` automatically get `Name` and `StaffId` from `StaffMember`.
    - They add their own specialised attributes.
    - This is **inheritance**: a specialised class is created from a general class ("is-a" relationship).

---

## 5. Putting generalisation + inheritance together (typical exam pattern)

??? note "Usage example"
    ```csharp
    Teacher t1 = new Teacher();
    t1.Name = "Ms Lim";        // inherited from StaffMember
    t1.StaffId = "T204";       // inherited from StaffMember
    t1.Subject = "Maths";      // specialised for Teacher

    AdminStaff a1 = new AdminStaff();
    a1.Name = "Mr Patel";      // inherited
    a1.StaffId = "A118";       // inherited
    a1.OfficeLocation = "B3";  // specialised for AdminStaff
    ```

!!! info "What students should be able to say"
    - **Generalisation** created `StaffMember` with shared features.
    - **Inheritance** allowed `Teacher` and `AdminStaff` to reuse those features and add their own.

---

## 40+ Exam Tip (very useful)

!!! success "Exam Phrasing"
    When asked to identify or justify OOP principles, students should use phrasing like:

    - **Abstraction:** "Only relevant features are included; irrelevant details are ignored."
    - **Encapsulation:** "Data is protected by restricting direct access and using methods to control changes."
    - **Generalisation:** "Common attributes/behaviours are placed into one general class to reduce duplication."
    - **Inheritance:** "A specialised class inherits attributes/methods from a general class (is-a relationship)."
