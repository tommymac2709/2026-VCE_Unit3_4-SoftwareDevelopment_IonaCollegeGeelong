# e. Extras

These C# implementations are drop-in helpers. The key skill is knowing **when to call them** and **how to use their returned results**.

---

## 1) Drop-in algorithm code (paste once)

### SearchAlgorithms.cs

??? note "Click to view SearchAlgorithms.cs"
    ```csharp
    public static class SearchAlgorithms
    {
        // Works on sorted OR unsorted arrays
        public static bool LinearSearch(int[] data, int target)
        {
            for (int i = 0; i < data.Length; i++)
            {
                if (data[i] == target) return true;
            }
            return false;
        }

        // Requires data sorted ascending
        public static bool BinarySearch(int[] data, int target)
        {
            int low = 0;
            int high = data.Length - 1;

            while (low <= high)
            {
                int mid = (low + high) / 2;

                if (data[mid] == target) return true;
                if (target < data[mid]) high = mid - 1;
                else low = mid + 1;
            }

            return false;
        }
    }
    ```

---

### SortAlgorithms.cs

??? note "Click to view SortAlgorithms.cs"
    ```csharp
    public static class SortAlgorithms
    {
        // Sorts the array IN PLACE (the original array changes)
        public static void SelectionSort(int[] data)
        {
            for (int i = 0; i < data.Length - 1; i++)
            {
                int smallestIndex = i;

                for (int j = i + 1; j < data.Length; j++)
                {
                    if (data[j] < data[smallestIndex])
                        smallestIndex = j;
                }

                // swap into position
                int temp = data[i];
                data[i] = data[smallestIndex];
                data[smallestIndex] = temp;
            }
        }

        // Public wrapper (students call this)
        public static void QuickSort(int[] data)
        {
            QuickSortRecursive(data, 0, data.Length - 1);
        }

        private static void QuickSortRecursive(int[] data, int low, int high)
        {
            if (low < high)
            {
                int pivotIndex = Partition(data, low, high);
                QuickSortRecursive(data, low, pivotIndex - 1);
                QuickSortRecursive(data, pivotIndex + 1, high);
            }
        }

        private static int Partition(int[] data, int low, int high)
        {
            int pivot = data[high];
            int i = low - 1;

            for (int j = low; j < high; j++)
            {
                if (data[j] < pivot)
                {
                    i++;
                    Swap(data, i, j);
                }
            }

            Swap(data, i + 1, high);
            return i + 1;
        }

        private static void Swap(int[] data, int i, int j)
        {
            int temp = data[i];
            data[i] = data[j];
            data[j] = temp;
        }
    }
    ```

---

## 2) FULL program example (Console) — shows correct use

This demonstrates a realistic sequence:

1. Load data (already in memory here)
2. Sort it
3. Use binary search (only after sorting)
4. Show results to the user

```csharp
using System;

class Program
{
    static void Main()
    {
        int[] studentIds = { 1042, 1003, 1099, 1015, 1030 };

        Console.WriteLine("Original IDs: " + string.Join(", ", studentIds));

        // 1) SORT first (required for binary search)
        SortAlgorithms.QuickSort(studentIds);
        Console.WriteLine("Sorted IDs:   " + string.Join(", ", studentIds));

        // 2) SEARCH for a target ID
        int targetId = 1015;

        bool existsBinary = SearchAlgorithms.BinarySearch(studentIds, targetId);
        Console.WriteLine($"Binary search: ID {targetId} exists? {existsBinary}");

        // 3) Show linear search as comparison (works even if unsorted)
        int target2 = 2000;
        bool existsLinear = SearchAlgorithms.LinearSearch(studentIds, target2);
        Console.WriteLine($"Linear search: ID {target2} exists? {existsLinear}");
    }
}
```

**Expected output (example):**

```
Original IDs: 1042, 1003, 1099, 1015, 1030
Sorted IDs:   1003, 1015, 1030, 1042, 1099
Binary search: ID 1015 exists? True
Linear search: ID 2000 exists? False
```

!!! info "What students must understand"
    - `QuickSort` **changes the array in place**
    - `BinarySearch` returns **true/false** based on whether the item exists
    - Binary search is **only valid once sorted**

---

## 3) Typical GUI usage (WinForms/WPF pattern)

This is how it looks inside a button click, which matches how many students build their Outcome 1 modules.

```csharp
// Example: Button click event handler
private void btnCheckId_Click(object sender, EventArgs e)
{
    int[] studentIds = { 1042, 1003, 1099, 1015, 1030 };

    // Sort (so binary search works)
    SortAlgorithms.SelectionSort(studentIds); // or QuickSort(studentIds)

    int targetId = int.Parse(txtStudentId.Text);

    bool exists = SearchAlgorithms.BinarySearch(studentIds, targetId);

    lblResult.Text = exists
        ? "That Student ID already exists."
        : "Student ID is available.";
}
```

!!! tip "Key learning"
    The algorithm functions are called **inside the module logic**, usually after input is read and before output is displayed.

---

## 4) "Correct order" templates (students can memorise)

### If list is NOT sorted:

```csharp
SortAlgorithms.QuickSort(data);
bool found = SearchAlgorithms.BinarySearch(data, target);
```

---

### If list IS already sorted:

```csharp
bool found = SearchAlgorithms.BinarySearch(sortedData, target);
```

---

### If you can't guarantee sorting:

```csharp
bool found = SearchAlgorithms.LinearSearch(data, target);
```

---

## 40+ Exam link (what they write, not code)

!!! warning "Important"
    When asked to **justify algorithm choice**, students should write things like:

    ✅ *"Binary search is appropriate because the list is sorted and the algorithm halves the search space each iteration."*

    ✅ *"Linear search is appropriate because the list is unsorted."*

    **Not just:** "I used binary search" (no justification = no marks)
