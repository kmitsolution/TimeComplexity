### **Quadratic Time Complexity (O(n²))**

**Definition:**
An algorithm is said to have **quadratic time complexity (O(n²))** when its execution time grows quadratically as the size of the input increases. This means that as the input size (`n`) doubles, the time taken by the algorithm increases by a factor of four (2²).

### **Key Idea:**
For an algorithm to be **O(n²)**, it must have two nested loops, each iterating over the entire input. This is because each element needs to be compared or interacted with every other element. As a result, the number of operations grows as the square of the input size (`n`).

### **Basic Example:**

A typical example of an **O(n²)** algorithm is one that uses **nested loops** to perform a task. Each loop runs from `1` to `n`, so the total number of iterations is the square of `n`.

### **Example 1: Bubble Sort**

Bubble sort is a simple sorting algorithm where you compare adjacent elements in a list and swap them if they are in the wrong order. The process repeats until the entire list is sorted.

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):  # Outer loop
        for j in range(0, n-i-1):  # Inner loop
            if arr[j] > arr[j+1]:  # Swap if elements are in the wrong order
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr
```

- **Time Complexity**: **O(n²)**

#### Explanation:
- **Outer loop** runs `n` times.
- **Inner loop** runs `n - i - 1` times in each iteration of the outer loop, but in the worst case, the inner loop also runs `n` times.

- So, for each element, the algorithm performs a comparison with every other element. In total, this results in approximately `n * n` operations, hence the **O(n²)** time complexity.

### **Example 2: Selection Sort**

Selection sort is another simple sorting algorithm where the minimum element is repeatedly selected from the unsorted portion of the array and swapped with the first unsorted element.

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):  # Outer loop
        min_index = i
        for j in range(i + 1, n):  # Inner loop
            if arr[j] < arr[min_index]:
                min_index = j
        arr[i], arr[min_index] = arr[min_index], arr[i]  # Swap
    return arr
```

- **Time Complexity**: **O(n²)**

#### Explanation:
- **Outer loop** runs `n` times.
- **Inner loop** runs `n - i` times for each iteration of the outer loop.

- Like bubble sort, each element is compared with every other element, leading to quadratic time complexity.

### **Example 3: Checking for Duplicates in an Unsorted List**

If you have a list of numbers and you want to check if there are any duplicates, you could use a brute-force method where you compare every element with every other element.

```python
def has_duplicates(arr):
    n = len(arr)
    for i in range(n):  # Outer loop
        for j in range(i + 1, n):  # Inner loop
            if arr[i] == arr[j]:
                return True  # Found a duplicate
    return False  # No duplicates found
```

- **Time Complexity**: **O(n²)**

#### Explanation:
- The function uses two nested loops: the outer loop runs `n` times, and the inner loop compares each element with the remaining elements.
- This results in `n * (n-1) / 2` comparisons, which simplifies to **O(n²)**.

---

### **Example 4: Matrix Multiplication**

Multiplying two matrices is another example of an **O(n²)** algorithm. Let's say we have two square matrices (A and B) of size `n x n` and we want to calculate their product (C = A * B).

```python
def matrix_multiply(A, B):
    n = len(A)
    C = [[0] * n for _ in range(n)]  # Resultant matrix

    for i in range(n):  # Loop through rows of A
        for j in range(n):  # Loop through columns of B
            for k in range(n):  # Loop through columns of A and rows of B
                C[i][j] += A[i][k] * B[k][j]

    return C
```

- **Time Complexity**: **O(n³)**, but notice that this is a more general example and in case of optimizations or special cases, matrix multiplication might have better performance (like **O(n².81)** in some algorithms).

#### Explanation:
- There are three nested loops: each one iterates `n` times.
- The result is an **O(n³)** time complexity for matrix multiplication. But if you are talking about other algorithms where you need to compare elements pairwise (like with two-dimensional arrays), the idea of nested loops is what results in quadratic growth.

---

### **Why O(n²) Time Complexity Happens**

- **Nested Loops**: The most common scenario where **O(n²)** occurs is in algorithms with **nested loops**. If you have an outer loop running `n` times and an inner loop also running `n` times, the total number of iterations becomes proportional to `n * n`.
  
- **Pairwise Comparisons**: Any algorithm that needs to compare each element to every other element (like sorting or checking for duplicates) will likely have a quadratic time complexity.

---

### **Comparing O(n²) with Other Complexities**

| **Time Complexity** | **Description**                                      | **Example**                                        |
|---------------------|------------------------------------------------------|----------------------------------------------------|
| **O(1)**            | Constant time. The execution time does not depend on the input size. | Accessing an element in an array.                 |
| **O(n)**            | Linear time. The execution time grows linearly with input size. | Iterating through a list.                         |
| **O(n²)**           | Quadratic time. Execution time grows quadratically with input size. | Bubble sort, selection sort, checking duplicates. |
| **O(n log n)**      | Linearithmic time. Common in efficient sorting algorithms. | Merge sort, quick sort.                          |
| **O(n³)**           | Cubic time. Common in matrix multiplication.         | 3D matrix operations or nested loops with 3 levels. |

---

### **When to Avoid O(n²) Algorithms**

- **Performance**: **O(n²)** algorithms are inefficient for large datasets, especially when `n` becomes large. Sorting algorithms like bubble sort or selection sort are simple but inefficient with **O(n²)** time complexity.
- **Scalability**: If you are working with a large amount of data, an **O(n²)** algorithm might cause performance issues. In such cases, more optimized algorithms (like **O(n log n)** for sorting) are preferred.

---

### **Conclusion**

- **O(n²)** time complexity happens when an algorithm involves nested loops, typically when you need to compare each element with every other element.
- **Examples**: Bubble sort, selection sort, checking for duplicates, and certain matrix operations.
- **Performance**: These algorithms are not optimal for large datasets because their execution time grows quickly as the input size increases.

If you'd like to dive deeper into any of the examples or need further clarification, feel free to ask!
