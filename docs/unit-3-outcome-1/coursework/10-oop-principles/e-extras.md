# Extras

!!! abstract "Purpose"
    Additional resources and practice for mastering OOP principles.

---

This section demonstrates abstraction, encapsulation, generalisation and inheritance working together in a single, coherent example.

!!! tip "Important"
    - **In exams**, students explain the principles.
    - **In projects**, students apply them using code like this.

---

## 1) Abstraction — modelling only what matters

**Scenario**

A system manages staff members in a school. Only relevant information is included.

??? note "C# code"
    ```csharp
    public class StaffMember
    {
        public string Name { get; set; } = "";
        public string StaffId { get; set; } = "";
    }
    ```

!!! info "Why this is abstraction"
    - Only essential attributes are included
    - Irrelevant real-world details are excluded
    - The model fits the purpose of the software

---

## 2) Encapsulation — protect data and control access

Now we improve reliability by restricting direct access.

??? note "C# code"
    ```csharp
    public class StaffMember
    {
        private string staffId = "";   // private attribute (encapsulated)

        public string Name { get; set; } = "";

        public void SetStaffId(string id)
        {
            if (id != "")
            {
                staffId = id;          // controlled update
            }
        }

        public string GetStaffId()
        {
            return staffId;            // controlled access
        }
    }
    ```

!!! info "Why this is encapsulation"
    - Data and methods are bundled together
    - Direct access to `staffId` is prevented
    - Changes only occur through methods

!!! warning "📌 Textbook link"
    Encapsulation improves data security and reliability.

---

## 3) Generalisation — identify shared features

Teachers and admin staff share common features, so we generalise them.

??? note "C# code"
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

!!! info "Why this is generalisation"
    - Common attributes and behaviours are placed in one class
    - Duplication is reduced
    - Maintenance is simplified

---

## 4) Inheritance — specialised classes reuse the general class

Now we create specialised staff types.

??? note "C# code"
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

!!! info "Why this is inheritance"
    - `Teacher` **is a** `StaffMember`
    - `AdminStaff` **is a** `StaffMember`
    - Shared features are inherited automatically
    - Specialised features are added where needed

---

## 5) FULL mini-program (all principles together)

!!! success "This example shows:"
    - **abstraction** (relevant features only)
    - **encapsulation** (controlled access)
    - **generalisation** (shared class)
    - **inheritance** (specialised classes)

??? note "Complete working program"
    ```csharp
    using System;

    class Program
    {
        static void Main()
        {
            Teacher t1 = new Teacher();
            t1.Name = "Ms Lim";
            t1.SetStaffId("T204");
            t1.Subject = "Mathematics";

            AdminStaff a1 = new AdminStaff();
            a1.Name = "Mr Patel";
            a1.SetStaffId("A118");
            a1.OfficeLocation = "Office B3";

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
