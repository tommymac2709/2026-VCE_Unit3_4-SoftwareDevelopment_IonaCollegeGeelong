# c. Practical Examples

---

## 1) Selection sort — pseudocode (with inline comments)

```
ALGORITHM selectionSort(arrElements)
{ Purpose: sorts a list of elements }
{ Input: an array of elements }
{ Index values start at 1 }
{ Output: Array, a sorted array of elements }
BEGIN
    n ← number of items in arrElements

    FOR i ← 1 to n DO
        { select the smallest item }
        smallest ← i                      // assume current position is smallest

        { compare smallest to the rest of the array }
        FOR j ← i + 1 to n DO
            IF arrElements[j] < arrElements[smallest] THEN
                { update the index value of smallest }
                smallest ← j              // found a smaller value
            ENDIF
        NEXT

        { the smallest item in the array has been found }
        { so swap it with the current element }
        IF smallest != i THEN
            swap arrElements[smallest] AND arrElements[i]   // move smallest into position i
        ENDIF
    NEXT

    RETURN arrElements
END
```

!!! info "What to notice (exam-useful)"
    - **Outer loop** selects the position being filled (i)
    - **Inner loop** finds the smallest value in the remaining unsorted portion
    - **One swap** per outer loop pass (at most)

---

## 2) Quick sort — pseudocode (with inline comments)

### 2a) quickSort algorithm

```
ALGORITHM quickSort(arrElements, low, high)
{ Purpose: sorts a list of elements }
{ Inputs: an array of elements, two integers representing }
{ the first last element in the array }
{ Index values start at 1 }
BEGIN
    IF low < high THEN
        { run the partition algorithm to know where }
        { to split the array }
        split ← partition(arrElements, low, high)    // split is the pivot's final position

        { run quicksort on the left side }
        quickSort(arrElements, low, split-1)         // sort left partition

        { run quicksort on the right side }
        quickSort(arrElements, split+1, high)        // sort right partition
    ENDIF
END
```

### 2b) partition algorithm (in-place)

```
ALGORITHM partition(arrElements, low, high)
{ Purpose: to split the array into two based on a pivot, }
{ where the left side contains values less than }
{ the pivot and the right side contains values }
{ greater }
{ Inputs: an array of elements, two integers representing }
{ the first last element in the array }
{ Index values start at 1 }
{ Output: integer, index value of the partition point }
BEGIN
    pivot ← arrElements[high]            // choose pivot as last element

    FOR i ← low + 1 to high DO
        IF arrElements[i] < pivot THEN   // value belongs on left side
            IF low != i THEN
                swap arrElements[low] and arrElements[i]   // move smaller value left
            ENDIF
            low ← low + 1                // advance boundary for "< pivot" region
        ENDIF
    NEXT

    swap arrElements[low] and arrElements[high]     // place pivot into correct position
    RETURN low
END
```

!!! info "What to notice (exam-useful)"
    - Quick sort is **"split then sort each side"**
    - **Partition is the key step:** it rearranges elements so pivot ends in the correct position
    - The algorithm shown is **in-place** (sorting happens inside the array)

---

## 3) Linear search — pseudocode (with inline comments)

```
ALGORITHM linearSearch( )
{ Purpose: searches through a list of elements }
{ Output: Boolean, True if item found, False if not }
BEGIN
    INPUT searchList, searchItem
    found ← FALSE                         // assume not found

    FOR eachItem in the searchList DO
        IF eachItem = searchItem THEN
            found ← TRUE                  // found the item
            BREAK {exit loop once found}  // stop early (best case)
        ENDIF
    NEXT

    RETURN found
END
```

!!! info "What to notice (exam-useful)"
    - Works on **sorted or unsorted** lists
    - **Worst case:** item not present → checks every element

---

## 4) Binary search — pseudocode (with inline comments)

```
ALGORITHM binarySearch(arrayList, searchItem)
{ Purpose: searches through a list of elements }
{ Inputs: an array of elements to be searched }
{         and the item being searched for }
{ Output: Boolean, True if item found, False if not }
BEGIN
    found ← FALSE
    iLen ← the length of arrayList
    midP ← the middle index value of arrayList     // midpoint to compare against

    IF searchItem = arrayList[midP] THEN
        found ← TRUE                               // match at the middle
    ELSEIF iLen > 1 THEN                           // only keep searching if more than 1 element remains
        IF searchItem < arrayList[midP] THEN
            low ← first index value of arrayList
            RETURN binarySearch(arrayList[low to midP], searchItem)   // search left half
        ELSEIF searchItem > arrayList[midP] THEN
            high ← iLen
            RETURN binarySearch(arrayList[midP to high], searchItem)  // search right half
        ENDIF
    ENDIF

    RETURN found
END
```

!!! info "What to notice (exam-useful)"
    - **Precondition:** list must be sorted (ascending/descending)
    - Logic is **"compare middle → choose left half or right half"**
    - This version is **recursive** (calls itself on a sub-list)

---

## Mini walk-through (quick check students can do)

### Binary search example

**List (sorted):** `[3, 8, 12, 20, 25, 30, 41]`, **searchItem = 25**

**Step 1:**
- Mid is **20** → 25 is bigger → search right half

**Step 2:**
- New mid is **30** → 25 is smaller → search left half of that half

**Step 3:**
- Mid becomes **25** → **found**

!!! tip "Practice"
    Try tracing this yourself with searchItem = 8 or searchItem = 41
