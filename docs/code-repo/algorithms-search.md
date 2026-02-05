# Search Algorithms

!!! info "Key Distinction"
    **Linear search** works on any data (sorted or unsorted).

    **Binary search** requires sorted data but is much faster for large datasets.

---

## SearchAlgorithms Helper Class

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

## Linear Search Example

**When to use:** Data is unsorted, or list is small.

```csharp
int[] numbers = { 42, 15, 8, 23, 4 }; // unsorted
int target = 23;

bool found = SearchAlgorithms.LinearSearch(numbers, target);
Console.WriteLine($"Found {target}: {found}"); // True
```

!!! tip "Linear Search Characteristics"
    - Works on sorted OR unsorted data
    - Simple to implement
    - Checks each element sequentially
    - Inefficient for large lists

---

## Binary Search Example

**When to use:** Data is sorted, and fast searching is required.

```csharp
int[] studentIds = { 1042, 1003, 1099, 1015, 1030 };

// 1) SORT first (required for binary search)
SortAlgorithms.QuickSort(studentIds);
Console.WriteLine("Sorted: " + string.Join(", ", studentIds));

// 2) SEARCH for a target ID
int targetId = 1015;
bool exists = SearchAlgorithms.BinarySearch(studentIds, targetId);
Console.WriteLine($"Binary search: ID {targetId} exists? {exists}");
```

!!! warning "Critical Requirement"
    Binary search **requires sorted data**. If the data is not sorted, binary search will not work correctly.

---

## Quick Reference

| Feature | Linear Search | Binary Search |
|---------|---------------|---------------|
| Requires sorted data | ❌ No | ✅ Yes |
| Checks elements sequentially | ✅ Yes | ❌ No |
| Efficient for large lists | ❌ No | ✅ Yes |
| Simple to implement | ✅ Yes | ❌ More complex |

---

## Usage Templates

### If list is NOT sorted:
```csharp
bool found = SearchAlgorithms.LinearSearch(data, target);
```

### If list IS sorted:
```csharp
bool found = SearchAlgorithms.BinarySearch(sortedData, target);
```

### If you need to sort first:
```csharp
SortAlgorithms.QuickSort(data);
bool found = SearchAlgorithms.BinarySearch(data, target);
```
