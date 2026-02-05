# Sort Algorithms

!!! info "Key Distinction"
    **Selection sort** is simple but inefficient for large datasets.

    **Quick sort** is faster for large datasets but more complex.

---

## SortAlgorithms Helper Class

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

## Selection Sort Example

**When to use:** Small lists, or when simplicity is more important than speed.

```csharp
int[] numbers = { 64, 25, 12, 22, 11 };

Console.WriteLine("Original: " + string.Join(", ", numbers));

SortAlgorithms.SelectionSort(numbers);

Console.WriteLine("Sorted: " + string.Join(", ", numbers));
// Output: 11, 12, 22, 25, 64
```

!!! tip "Selection Sort Characteristics"
    - Simple and easy to understand
    - Works on unsorted data
    - Inefficient for large datasets
    - Always performs the same number of comparisons

---

## Quick Sort Example

**When to use:** Large datasets where efficiency matters.

```csharp
int[] studentIds = { 1042, 1003, 1099, 1015, 1030 };

Console.WriteLine("Original: " + string.Join(", ", studentIds));

SortAlgorithms.QuickSort(studentIds);

Console.WriteLine("Sorted: " + string.Join(", ", studentIds));
// Output: 1003, 1015, 1030, 1042, 1099
```

!!! tip "Quick Sort Characteristics"
    - Uses divide-and-conquer approach
    - Much faster than selection sort for large datasets
    - More complex to understand and implement
    - Performance depends on pivot selection

---

## Quick Reference

| Feature | Selection Sort | Quick Sort |
|---------|----------------|------------|
| Simple to understand | ✅ Yes | ❌ No |
| Efficient for large lists | ❌ No | ✅ Yes |
| Uses divide-and-conquer | ❌ No | ✅ Yes |
| Suitable for small lists | ✅ Yes | ❌ Overkill |

---

## Full Example with Search

```csharp
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
```

!!! warning "Important"
    Both sorting algorithms modify the array **in place** - the original array is changed.
