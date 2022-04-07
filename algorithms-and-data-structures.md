## Sorting algorithms

<details>
<summary>What are the most known sorting algorithms?</summary>

The most known sorting algorithms are
* insertion
* selection
* bubble
* shell
* merge
* heap
* quick sort
</details>

<details>
<summary>How does the bubble sorting algorithm work? What is its time complexity?</summary>

The **bubble sorting** algorithm loops the array from left to right. Each time the left item is larger than the right item, the two items are swapped. The process continues until there are no more items to swap.

The bubble sorting algorithm has time complexity O(n2)
</details>

<details>
<summary>How does the selection sorting algorithm work? What is its time complexity?</summary>

The **selection sorting** algorithm scans an array, find the minimum value and put it to position 0, scan again the array from position 1 and put the minimum value to position 1 and so on for positions 2...n

The selection sorting algorithm has time complexity O(n2)
</details>

<details>
<summary>How does the intertion sorting algorithm work? What is its time complexity?</summary>

The **insertion sorting** algorithm can be useful when you know that your array is almost sorted and the array is pretty small.

The insertion sorting algorithm is like sorting cards: you scroll the array and when you find a smaller value, you put it in the right position.

The insertion sorting algorithm has time complexity O(n2)

</details>

<details>
<summary>How does the merge sorting algorithm work? What is its time complexity?</summary>

The **merge sorting** algorithm uses the divide and conquer strategy and its steps are:
- Divide array in parts recursively until you have 1 item per part
- sort each pair of numbers into a temporary larger array
- sort each couple of temporary arrays into a temporary larger array
- the temporary arrays are sorted with bubble or insertion
- repeat until you are done

The merge sorting algorithm has time complexity O(nlogn).

</details>

<details>
<summary>How does the quick sort algorithm work? What is its average and worst time complexity?</summary>

**Quick sort** uses a divide and conquer approach. It uses a pivoting technique to split the array.
Pivot is took at a random position and start swapping items so that items to the left (right) of the pivot
are smaller (larger). After that we do the same recursively for each subarray

Its worst case of time complexity is on2 when the chosen pivot is the min or max value of the array so that all the other items must be swapped.
</details>



