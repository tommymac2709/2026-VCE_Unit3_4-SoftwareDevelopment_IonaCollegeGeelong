# a. What You Need To Know

!!! info "Key Knowledge - KK 3.1.12"
    Algorithms for sorting and searching, including:

    - Selection sort
    - Quick sort
    - Binary search
    - Linear search

---

## What is an algorithm?

!!! tip "Key Point"
    An algorithm is a step-by-step set of instructions used to solve a problem or perform a task.

In software development, algorithms are used to:

- **sort** data into a particular order
- **search** data to find a specific value

Algorithms are typically represented using **pseudocode**, which describes the logic of a solution without being tied to a specific programming language.

---

## Sorting vs searching (do not confuse these)

!!! warning "Important"
    | Sorting | Searching |
    |---------|-----------|
    | Rearranges data into a specific order | Looks for a specific item |
    | Changes the order of elements | Does not change the data |
    | Often done before searching | Depends on the data order |

    A common exam mistake is describing a searching algorithm as if it rearranges data — **it does not**.

---

## Selection sort

### What it does

!!! tip "Key Point"
    Selection sort repeatedly finds the smallest unsorted value and swaps it into its correct position.

### How it works (conceptually)

1. Start at the first position in the list
2. Find the smallest value in the remaining unsorted portion
3. Swap it with the current position
4. Move to the next position
5. Repeat until the list is sorted

### Key characteristics

- Simple and easy to understand
- Works on unsorted data
- Inefficient for large data sets
- Always performs the same number of comparisons, regardless of data order

!!! info "When to use"
    Selection sort is useful for small lists or when simplicity is more important than speed.

---

## Quick sort

### What it does

!!! tip "Key Point"
    Quick sort sorts data by dividing the list into smaller sublists around a chosen value called a **pivot**.

### How it works (conceptually)

1. Choose a pivot value
2. Partition the list so:
    - values smaller than the pivot are placed on the left
    - values larger than the pivot are placed on the right
3. Recursively apply the same process to each sublist
4. Continue until all sublists contain one element

### Key characteristics

- Uses a divide-and-conquer approach
- Much faster than selection sort for large data sets
- More complex to understand and implement
- Performance depends on pivot selection

!!! info "When to use"
    Quick sort is typically preferred when efficiency matters and the data set is large.

---

## Linear search

### What it does

!!! tip "Key Point"
    Linear search checks each element in a list one by one until the target value is found or the list ends.

### How it works (conceptually)

1. Start at the first element
2. Compare it to the search value
3. If it matches, stop
4. If not, move to the next element
5. Continue until found or the list ends

### Key characteristics

- Works on unsorted or sorted data
- Simple to implement
- Inefficient for large lists
- Worst-case scenario: every element must be checked

!!! info "When to use"
    Linear search is suitable when:

    - the list is small
    - the data is unsorted
    - simplicity is required

---

## Binary search

### What it does

!!! tip "Key Point"
    Binary search repeatedly divides a sorted list in half to locate a target value.

### Critical precondition

!!! warning "Important"
    ⚠ Binary search **requires the data to be sorted**.

    If the data is not sorted, binary search will not work correctly.

### How it works (conceptually)

1. Find the middle element of the list
2. Compare it to the target value
3. If it matches, stop
4. If the target is smaller, search the left half
5. If the target is larger, search the right half
6. Repeat until found or the search space is empty

### Key characteristics

- Very efficient for large lists
- Much faster than linear search
- Only works on sorted data
- More complex logic than linear search

!!! info "When to use"
    Binary search is preferred when:

    - the data is sorted
    - fast searching is required
    - the list is large

---

## Comparing searching algorithms (exam focus)

| Feature | Linear search | Binary search |
|---------|---------------|---------------|
| Requires sorted data | ❌ No | ✅ Yes |
| Checks elements sequentially | ✅ Yes | ❌ No |
| Efficient for large lists | ❌ No | ✅ Yes |
| Simple to implement | ✅ Yes | ❌ More complex |

!!! warning "Exam trap"
    A common exam trap is choosing binary search without checking whether the data is sorted.

---

## Comparing sorting algorithms (exam focus)

| Feature | Selection sort | Quick sort |
|---------|----------------|------------|
| Simple to understand | ✅ Yes | ❌ No |
| Efficient for large lists | ❌ No | ✅ Yes |
| Uses divide-and-conquer | ❌ No | ✅ Yes |
| Suitable for small lists | ✅ Yes | ❌ Overkill |

!!! warning "Important"
    Examiners reward answers that **justify the choice** of algorithm, not just name it.

---

## 40+ Exam reminders

!!! tip "Remember"
    - **Searching does not rearrange data**
    - **Binary search requires sorted data**
    - **Quick sort is faster, but more complex**
    - **Selection sort is simple, but inefficient**
    - **Always link algorithm choice to data size and structure**
