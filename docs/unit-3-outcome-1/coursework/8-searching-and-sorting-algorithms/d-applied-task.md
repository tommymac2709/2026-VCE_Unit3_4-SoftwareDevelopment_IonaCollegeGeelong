# d. Applied Task

These tasks focus on binary search, a highly examinable algorithm in Section B and Section C.

All scenarios assume the data is stored in **ascending order**.

---

## Practice Question 1 – Search for a Student ID (6 marks)

The system below stores all student IDs in ascending order.

When a new student enrols, the algorithm checks whether that ID already exists.

Complete the missing lines so that the binary search correctly sets Found to TRUE if the ID is already in the list.

```
Begin StudentExists(NewID)

    // Read IDs into array in ascending order
    StudentIDs[] ← Read IDs From file

    Found ← False
    Low ← 0
    High ← StudentIDs.Length - 1

    While Found = False And Low ≤ High
        Mid ← RoundDown((Low + High) / 2)

        ______________________________________
        ______________________________________
        ______________________________________

    End While

    If Found Then
        Return True
    Else
        Return False
    End If

End
```

??? note "What a full-mark response must do"
    **6 marks requires:**

    - **Compare** NewID with StudentIDs[Mid]
    - **Update** either Low or High correctly
    - **Set** Found to True when a match is found

    **Example correct solution:**

    ```
    If NewID = StudentIDs[Mid] Then
        Found ← True
    ElseIf NewID < StudentIDs[Mid] Then
        High ← Mid - 1
    Else
        Low ← Mid + 1
    End If
    ```

---

## Practice Question 2 – Locate a Product Price (6 marks)

An e-commerce system stores product prices in ascending order.

The algorithm must determine whether a given price TargetPrice exists in the list.

Fill in the missing lines so the binary search works correctly.

```
Begin PriceCheck(TargetPrice)

    Prices[] ← Read Prices From file
    Exists ← False
    Low ← 0
    High ← Prices.Length - 1

    While Exists = False And Low ≤ High
        Mid ← (Low + High) DIV 2

        ______________________________________
        ______________________________________
        ______________________________________

    End While

    If Exists Then
        Print "Price found."
    Else
        Print "Price not found."
    End If

End
```

??? note "What examiners look for"
    **Full marks requires:**

    - **Correct comparison** against Prices[Mid]
    - **Correct narrowing** of the search space
    - **No changes** to the order of the list (binary search does not sort)

    **Example correct solution:**

    ```
    If TargetPrice = Prices[Mid] Then
        Exists ← True
    ElseIf TargetPrice < Prices[Mid] Then
        High ← Mid - 1
    Else
        Low ← Mid + 1
    End If
    ```

---

## Practice Question 3 – Check Library Book Code (6 marks)

The library's digital catalogue keeps book codes in ascending order.

Before adding a new book, the algorithm must check whether the code already exists.

Fill in the missing pseudocode so the binary search correctly returns False if the book already exists and True if it can be added.

```
Begin CanAddBook(NewCode)

    BookCodes[] ← Read codes From file
    Found ← False
    Low ← 0
    High ← BookCodes.Length - 1

    While Found = False And Low ≤ High
        Mid ← (Low + High) DIV 2

        ______________________________________
        ______________________________________
        ______________________________________

    End While

    If Found Then
        Return False      // cannot add duplicate
    Else
        Return True
    End If

End
```

??? note "Key reasoning students must show"
    **Full marks requires:**

    - **Binary search is used** because the data is sorted
    - **Finding the code** means it must not be added
    - **Logic must update** Low / High, not rearrange the array

    **Example correct solution:**

    ```
    If NewCode = BookCodes[Mid] Then
        Found ← True
    ElseIf NewCode < BookCodes[Mid] Then
        High ← Mid - 1
    Else
        Low ← Mid + 1
    End If
    ```

---

## Common student errors (direct from examiner patterns)

!!! warning "Avoid These Mistakes"
    ❌ **Updating both Low and High in the same iteration**

    ❌ **Forgetting to stop searching once the item is found**

    ❌ **Using binary search logic on unsorted data**

    ❌ **Writing linear search logic inside a binary search loop**

---

## 40+ Exam Tip

!!! tip "Binary Search Mastery"
    In binary search questions, **full marks require correct control of the search range**.

    Simply checking the middle value is not enough — you must show **how the list is reduced**.
