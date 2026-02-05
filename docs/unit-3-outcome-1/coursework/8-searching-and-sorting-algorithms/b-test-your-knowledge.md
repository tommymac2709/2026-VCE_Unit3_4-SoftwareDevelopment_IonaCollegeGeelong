# b. Test Your Knowledge

Answer all questions using correct algorithm terminology. Read questions carefully — several are designed to reflect common exam traps.

---

## Part A: Multiple-choice questions (1 mark each)

### Question 1

Which algorithm works by repeatedly finding the smallest unsorted value and swapping it into its correct position?

A. Quick sort

B. Binary search

C. Linear search

D. Selection sort

??? note "Answer"
    **D. Selection sort**

    Selection sort repeatedly finds the smallest unsorted value and swaps it into its correct position.

---

### Question 2

Which condition must be met before a binary search can be used correctly?

A. The list must contain numeric values

B. The list must be small

C. The list must be sorted

D. The list must be stored in an array

??? note "Answer"
    **C. The list must be sorted**

    Binary search requires the data to be sorted. If the data is not sorted, binary search will not work correctly.

---

### Question 3

A list contains 10 000 unsorted records. Which algorithm would be the least efficient way to sort the list?

A. Quick sort

B. Selection sort

C. Binary search

D. Linear search

??? note "Answer"
    **B. Selection sort**

    Selection sort is inefficient for large data sets. Quick sort would be much faster for 10,000 records. Note: Binary search and linear search are searching algorithms, not sorting algorithms, so they're not applicable here.

---

### Question 4

Which statement about linear search is correct?

A. It requires sorted data

B. It always checks the middle value first

C. It compares each element sequentially

D. It rearranges the list as it searches

??? note "Answer"
    **C. It compares each element sequentially**

    Linear search checks each element one by one until the target is found. It does not require sorted data, does not check the middle first (that's binary search), and does not rearrange data (searching never rearranges data).

---

### Question 5

Which algorithm uses a divide-and-conquer approach?

A. Selection sort

B. Linear search

C. Binary search

D. Quick sort

??? note "Answer"
    **D. Quick sort**

    Quick sort uses a divide-and-conquer approach by dividing the list into smaller sublists around a pivot value. (Note: Binary search also uses divide-and-conquer, but in this context, the question is asking about sorting algorithms specifically, and quick sort is the clear answer among the options.)

---

## Part B: Short-answer questions

### Question 6

State one difference between sorting and searching algorithms. (1 mark)

??? note "Answer"
    **1 mark:** Sorting algorithms rearrange data into a specific order, while searching algorithms look for a specific item without changing the data.

    (Accept: Sorting changes the order of elements; searching does not change the data)

---

### Question 7

Explain why binary search is more efficient than linear search for large data sets. (2 marks)

??? note "Answer"
    **2 marks:** Binary search divides the search space in half with each comparison, eliminating half of the remaining elements at each step. Linear search must check each element sequentially, which requires many more comparisons for large data sets.

    **1 mark:** Partial explanation (e.g., mentions that binary search is faster but doesn't explain why, or only mentions one algorithm's approach)

---

### Question 8

Describe how selection sort works. Your answer should refer to how elements are compared and moved. (2 marks)

??? note "Answer"
    **2 marks:** Selection sort starts at the first position and searches through the remaining unsorted portion to find the smallest value. It then swaps this smallest value with the value at the current position. This process repeats, moving to the next position each time, until the entire list is sorted.

    **1 mark:** Partial description (e.g., mentions finding smallest value but not the swapping process, or describes process without mentioning comparison)

    **Key elements for full marks:**
    - Finding the smallest value in unsorted portion
    - Swapping it into correct position
    - Repeating the process

---

### Question 9

A student says:

*"Quick sort is always better than selection sort."*

Do you agree or disagree? Justify your response. (2 marks)

??? note "Answer"
    **2 marks - Disagree with clear justification:**

    Disagree. Quick sort is more efficient for large data sets, but selection sort is simpler to understand and implement. For small lists or when simplicity is more important than speed, selection sort may be more appropriate. Quick sort is unnecessarily complex for small data sets.

    **1 mark:** Correct disagreement but weak justification, or correct reasoning without clear position

    **0 marks:** Agree (incorrect), or no justification

    **Key elements for full marks:**
    - Clear disagreement
    - Recognition that quick sort is faster for large data
    - Recognition that selection sort has advantages (simplicity, suitable for small lists)

---

## Part C: Exam-style application

### Question 10

A system stores customer names in alphabetical order. The system must check whether a name already exists before adding a new one.

**a.** Identify the most appropriate searching algorithm to use.

**b.** Justify your choice.

(3 marks)

??? note "Answer"
    **3 marks - Full response:**

    **a.** Binary search

    **b.** The customer names are stored in alphabetical order (sorted), which is the requirement for binary search to work correctly. Binary search is more efficient than linear search for checking whether a name exists because it divides the search space in half with each comparison, making it much faster for large customer lists.

    **2 marks:** Correct algorithm with partial justification (e.g., mentions sorted data but not efficiency, or vice versa)

    **1 mark:** Correct algorithm with minimal or weak justification

    **0 marks:** Incorrect algorithm (e.g., linear search without justification, or a sorting algorithm)

    **Key elements for full marks:**
    - Identifies binary search
    - States data is sorted (meets binary search requirement)
    - Explains efficiency advantage for this scenario
    - Refers to the specific context (customer names, checking existence)

    **Common mistakes:**
    - Choosing linear search (works, but not most appropriate given sorted data)
    - Naming a sorting algorithm (the data is already sorted!)
    - Not mentioning that the data is sorted

---

## Reflection Questions

!!! question "Think About It"
    1. Why can't binary search be used on unsorted data?
    2. When would you choose selection sort over quick sort?
    3. A searching algorithm that "rearranges the list" is a contradiction. Why?
    4. What happens if you try to use binary search on unsorted data?
