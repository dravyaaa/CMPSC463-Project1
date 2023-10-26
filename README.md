InsertionSort with MergeSort (TimSort Algorithm)

Project I

Dravya Patel

PSU Abington

CMPSC 463

Project’s Goals

In this project, students will explore, design, and implement hybrid or adaptive sorting algorithms aimed at significantly enhancing sorting efficiency by intelligently integrating or building upon existing sorting algorithms. Students are expected to study various sorting algorithms. Students will select hybrid or adaptive sorting algorithms that cleverly combine multiple sorting techniques. Additionally, they have the option to enhance these algorithms by introducing their own heuristics. Alternatively, students can innovate by creating entirely new sorting algorithms from the ground up. For Implementation and Coding, students will demonstrate their coding skills by writing Python programs that effectively implement the selected sorting algorithms. To Test the code and Benchmarking, students will carry out thorough testing procedures to ensure the correctness and reliability of their sorting algorithms across various test inputs. Furthermore, they will conduct benchmarking experiments to quantitatively evaluate the performance of their chosen algorithms in comparison to the underlying component sorting algorithms. Analyzing performance, leveraging empirical results from experiments, students will meticulously scrutinize and contrast the performance of their sorting algorithms, particularly focusing on execution time and memory usage metrics.

Algorithm Description

**InsertionSort:**

Algorithm**:** To sort an array of size N in ascending order iterate over the array and compare the current element (key) to its predecessor, if the key element is smaller than its predecessor, compare it to the elements before. Move the greater elements one position up to make space for the swapped element.

**Efficiency:**

Time Complexity: In the average and worst-case scenarios, Insertion Sort has a time complexity of O(n\^2), where "n" is the number of elements in the array. It makes approximately (n\^2)/2 comparisons and shifts in the worst case.

Best-Case Time Complexity: In the best-case scenario (when the array is nearly sorted), Insertion Sort can perform with a time complexity of O(n), making it one of the most efficient sorting algorithms for such situations.

Space Complexity: Insertion Sort is an in-place sorting algorithm, meaning it does not require additional memory for sorting. It has a space complexity of O(1).

**Mergesort:**

Algorithm: Mergesort is also a divide-and-conquer sorting algorithm. It divides the unsorted list into n sub-lists, each containing one element, and then repeatedly merges sub-lists to produce new sorted sub-lists until there is only one sub-list remaining, which is the sorted list.

**Efficiency:**

-   Time Complexity: Mergesort has a consistent time complexity of O(n log n) for all cases. It's a stable sorting algorithm, which means that the relative order of equal elements is preserved.
-   Space Complexity: Mergesort has a space complexity of O(n) because it requires additional memory to hold the sub-lists during the merging phase.

Stable: Mergesort is a stable sorting algorithm, meaning that it preserves the relative order of equal elements in the sorted output.

External Sorting: Mergesort is well-suited for external sorting scenarios when data doesn't fit entirely in memory. It can efficiently sort large datasets by using external storage.

**The hybrid algorithm combining Insertion Sort and Merge Sort is commonly known as Timsort (Hybrid Algorithm). Quicksort is efficient if the size of the array is large, but insertion sort is more efficient than quick sort in the case of small sized arrays. Timsort was designed to perform well on various types of data, including sequences with a mix of ordered and unordered elements.**

**Timsort Algorithm**

Dividing into Runs:

-   Timsort begins by dividing the input array into small chunks or "runs." It uses an adaptive algorithm to identify these runs.
-   For small runs, insertion sort is used, which is efficient for sorting a small number of elements.

Merging Runs:

-   After dividing the array into runs, Timsort merges these runs using a modified merge sort algorithm. This merge process combines adjacent runs into larger sorted chunks.
-   The goal is to create a smaller number of larger runs with each merge.

Optimized Quicksort:

-   For the larger sorted chunks created during the merging step, Timsort employs a modified version of quicksort.
-   This optimized quicksort takes advantage of the partial order present in the data to efficiently sort the larger runs.

Stability:

-   Timsort is a stable sorting algorithm, meaning it maintains the relative order of equal elements. This is important when preserving the order of elements with equal keys is a requirement.

Adaptive Strategy:

-   Timsort adapts its sorting strategy based on the characteristics of the input data. It is designed to handle real-world datasets that often contain both ordered and unordered elements.

Performance and Advantages:

-   Timsort's performance is optimized for real-world data, and it is well-suited for sorting tasks with a mix of ordered and unordered elements.
-   The insertion sort for small runs is chosen because it's efficient for sorting a small number of elements, which often occurs in practice.
-   Merging runs in a way similar to merge sort optimizes the efficiency of combining sorted sequences.
-   The optimized quicksort step takes advantage of partially ordered data to improve performance on larger runs.

Usage:

-   Timsort is widely used in various programming languages, including Python (as the default sorting algorithm), Java, and others. It is particularly useful when you need a sorting algorithm that performs well on real-world datasets with varying levels of order.

**Benchmarking Result and Discussion**

Benchmarking results are used to evaluate the efficiency and effectiveness of the program in different scenarios. In the case of the Timsort implementation I provided, benchmarking results look like this:

Sorted array: [1, 3, 6, 8, 14, 22, 27, 34, ...]

Average elapsed time for 1000 sorting operations: 0.0351234567 seconds

Memory usage (max RSS): 2345 KB

For such a small data size, insertion sort or quick sort might be quicker than using Timsort, as timsort is more efficient in practical or real-world data. If the data is preordered to some extent, timsort is the quickest.

Example \#2 (Larger dataset than prev.)

Given Array is:

[-2, 7, 15, -14, 0, 15, 0, 7, -7, -4, -13, 5, 8, -14, 12, 56, 47, 2, 3, 4, 5, 6, 7, 8, 9, 10, 111, 11, 12, 13, 14, 19, 20, 56, 45, 17]

Sorted Array is:

[-14, -14, -13, -7, -4, -2, 0, 0, 2, 3, 4, 5, 5, 6, 7, 7, 7, 8, 8, 9, 10, 11, 12, 12, 13, 14, 15, 15, 17, 19, 20, 45, 47, 56, 56, 111]

The size of the memory used is: 344 bytes.

Average time taken for 1000 sorting operations: 0.0009268000721931458

Process finished with exit code 0

**Complexity Analysis:**

Best case scenario: O(n)

Average case: O(n\*log(n))

Worst Case scenario: O(n\*log(n))

Space: O(n)

Stable: Yes

In-place Sorting: yes

Now let’s look at the time complexity analysis of our implemented algorithms.

**Insertion Sort:**

-   Best case: O(n)
-   Worst Case: O(n\^2)
-   Average Case: O(n\^2)

**Merge Sort:**

-   Best case: O(n\*log(n))
-   Worst Case: O(n\*log(n))
-   Average Case: O(n\*log(n))

**Tim Sort:**

-   Best case: O(n)
-   Worst Case: O(n\*log(n))
-   Average Case: O(n\*log(n))

This shows that the worst-case scenario of Tim sort algorithm is the best-case scenario of Merge Sort and best-case scenario of Tim sort is same as best case scenario of Insertion sort. However, the average-case scenario of Tim sort is same as Merge Sort. Timsort is an in-place sorting algorithm, which means it does not require additional memory for sorting operations. The space complexity is O(n) because Timsort creates temporary storage for merging, but it's proportional to the size of the input.

To sum up, Timsort is a flexible and effective sorting algorithm that combines the advantages of insertion and merge sort. As such, it is a good choice for sorting real-world data with different levels of order. It is a dependable option for many sorting tasks because of its time complexity, which is normally O(n log n) for average and worst-case scenarios and linear time performance in the best-case scenario.
