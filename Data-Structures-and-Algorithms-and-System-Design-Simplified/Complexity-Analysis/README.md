# Complexity Analysis

## What is it?

Complexity analysis is a way to represent the time and space taken by an algorithm based on it's input size.

There are two complexities which are extremely important: **Time Complexity** and **Space Complexity**.

**Space complexity**: The amount of memory needed to run an algorithm.

**Time complexity**: How long it takes for an algorithm to run.

**Big O notation** is a formal way to show the **upper** bound of an algorithm's complexity. It is is written O(n), where n is the size of the input and O indicates that the time needed to run the algorithm grows no faster than the function inside the O.

Lesser known notations are **Big Omega (Ω)** notation, which shows the lower bound of an algorithm's complexity as the time required to run the algorithm grows no slower than the function inside the Omega, and **Big Theta (Θ)** notation, which shows the exact bound of an algorithm's complxity as the time required grows at the same rate as the function inside the Theta. I normally never use these notations, but there may be some instances where they're needed so it's good to keep them in mind.

## Why is complexity analysis even important?

Algorithms are a finite number of steps that solve a problem. Space and time complexities give us an idea of their **efficiency**. Being efficient in programming, and in life, is very important if you want to succeed. Big O notation shows us how efficient an algorithm is.

## Space and time complexities

**Space complexity** is the amount of memory required by an algorithm to run.

For example, a sorting algorithm called Merge Sort takes an extra n (where n is the size of the input, in this case an array of integers) space O(n) to run, but Selection Sort and Insertion Sort don't take extra space and run with **constant space** O(1).

**Time complexity** is the number of steps it take for an algorithm to finish.

<img width="518" alt="time complexity" src="https://github.com/user-attachments/assets/0107d175-10e3-4d00-807f-4a0cdef5cfb4">

## Big O: Notation and Examples:

Put simply, Big O notation is a way to measure how well an algorithm scales as the amount of input data increases. It describes the worst case scenario for the number of operations an algorithm will perform. It is often used to compare the efficiency of different algorithms for the same problem.

### Here are the most common complexities:

O(1): an algorithm that runs at constant time, meaning the run time is always the same regardless of the input size.

O(log n): an algorithm that has a run time that increases logarithmically with the input size.

O(n): a linear time algorithm, meaning the run time increases linearly with the input size.

O(n log(n)): an algorithm with a runtime that increases linearly with the input size multiplied by the logarithm of the input size.

O(n<sup>2</sup>): an algorithm with a run time proportional to the square of the input size.

O(2<sup>n</sup>): an algorithm with a run time that grows exponentially, i.e., doubles with each additional element in the input.

<img width="515" alt="big o complexity" src="https://github.com/user-attachments/assets/d5086f40-36cd-4d32-a8bc-9d0d3a5f8194">

### Examples:

O(1), constant run time: Selecting an item with an array index.
```python
def get_first_element(lst):
    """
    This function returns the first element of a list.
    It has a constant time complexity O(1).
    """
    if lst:
        return lst[0]
    return None

# Example usage
example_list = [10, 20, 30, 40, 50]
print(get_first_element(example_list))  # Output: 10

```

O(log n), logarithmic runtime: binary search.
```python
def binary_search(arr, target):
    """
    This function performs a binary search on a sorted array.
    It has a logarithmic time complexity O(log n).
    """
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = left + (right - left) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

# Example usage
sorted_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
target = 7
print(binary_search(sorted_list, target))  # Output: 6
```

O(n), linear runtime: finding the largest number in an array using a for loop.
```python
def find_maximum(arr):
    """
    This function finds the maximum element in an array.
    It has a linear time complexity O(n).
    """
    if not arr:
        return None
    max_element = arr[0]
    for element in arr:
        if element > max_element:
            max_element = element
    return max_element

# Example usage
example_list = [10, 20, 30, 40, 50]
print(find_maximum(example_list))  # Output: 50
```

O(n log n), linearithmic runtime: merge sort.
```python
def merge_sort(arr):
    """
    This function performs a merge sort on an array.
    It has a time complexity of O(n log n).
    """
    if len(arr) > 1:
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]

        merge_sort(left_half)
        merge_sort(right_half)

        i = j = k = 0

        while i < len(left_half) and j < len(right_half):
            if left_half[i] < right_half[j]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1

        while i < len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1

        while j < len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1

# Example usage
example_list = [38, 27, 43, 3, 9, 82, 10]
merge_sort(example_list)
print(example_list)  # Output: [3, 9, 10, 27, 38, 43, 82]
```

O(n<sup>2</sup>), quadratic runtime: bubble sort with 2 nested loops.
```python
def bubble_sort(arr):
    """
    This function performs a bubble sort on an array.
    It has a quadratic time complexity O(n^2).
    """
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

# Example usage
example_list = [64, 34, 25, 12, 22, 11, 90]
bubble_sort(example_list)
print(example_list)  # Output: [11, 12, 22, 25, 34, 64, 90]
```

O(2<sup>n</sup>), exponential runtime: Fibonnaci sequence.
```python
def fibonacci(n):
    """
    This function calculates the nth Fibonacci number.
    It has an exponential time complexity O(2^n).
    """
    if n <= 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n-1) + fibonacci(n-2)

# Example usage
n = 10
print(fibonacci(n))  # Output: 55
```

O(n!), factorial runtime: generate all permutations of a list.
```python
def generate_permutations(lst):
    """
    This function generates all permutations of a list.
    It has a factorial time complexity O(n!).
    """
    if len(lst) == 0:
        return [[]]
    permutations = []
    for i in range(len(lst)):
        element = lst[i]
        remaining_elements = lst[:i] + lst[i+1:]
        for p in generate_permutations(remaining_elements):
            permutations.append([element] + p)
    return permutations

# Example usage
example_list = [1, 2, 3]
print(generate_permutations(example_list))  
# Output: [[1, 2, 3], [1, 3, 2], [2, 1, 3], [2, 3, 1], [3, 1, 2], [3, 2, 1]]
```

## Theta Notation
Theta notation, written as Θ(f(n)), tell us the **exact growth rate** of an algorithm's running time as n gets very large. It gives a tight bound, meaning it captures both the maximum growth O(n) and the minimum growth Ω(n). Simply put, if an algorithm's runtime is Θ(f(n)), the algorithm will take "about f(n)" steps for large inputs with only small variations (which are multiplicative constants) allowed. 

The key idea is that theta notation means the run time is **at most** proportional to f(n) (Big-O) and **at least** proportional to f(n) (Omega).

### Example
Imagine we're trying to look for a number in an unsorted list of n integers. In the worst case, we might have to traverse the entire array. In the best case, we find it right at the beginning. If we analyze the **average case**, we check about half the list, so the runtime is **roughly proportional to n**. The runtime for linear search is Θ(n), meaning the runtime is never worse than n steps (O(n)) and you usually need at least n steps on average for large lists Ω(n).

### Example 2
Bubble sort is a sorting algorithm that repeatedly compares and swaps elements in a list of size n until it is sorted. For a list of size n, the algorithm runs through n elements and performs n<sup>2</sup> comparisons in the worst case.

So the runtime is Θ(n<sup>2</sup>). It doesn't take more than n<sup>2</sup> steps (O(n<sup>2</sup>)) and it takes at least n<sup>2</sup> steps, since there's no way to avoid comparing everything (Ω(n<sup>2</sup>)).

Basically, theta notation works only for large inputs and gives us the exact growth rate. Big-O overestimates, and Omega underestimates. Theta is precise. Again, it doesn't work on small inputs, since sorting an array with three numbers might take only a constant amount of time even for an algorithm with Θ(n<sup>2</sup>) runtime.

Still, we normally use big-O.

## How to determine and differentiate complexities

**Best case analysis**: finding the lower bound of an algorithm's runtime, i.e., the minimum amount of operations an algorithm can do. For example for a linear search the best case would be O(1) since you might find what you're looking for at the very start of the list.

**Worst case analysis**: finding the upper bound of an algorithm's runtime, i.e., the maximum amount of operations. For example, a linear search has a worst case of O(n), since we might have to go through the entire array just to find the element we want.

### Technique to calculate different complexities

**Step 0**: Don't mind any constants or non-dominant variables in your program. Constants don't matter for extremely large inputs. For example, if you have five for loops that aren't nested, you wouldn't write O(5n). You would simply write O(n).

**Step 1**: Break the functions in your program down into individual operations. So split it into seperate for loops, while loops, operations, etc.

**Step 2**: Calculate the Big O of each operation.

**Step 3**: Add all the Big O's up and calculate the end result. By calculate I mean find the one with highest degree, aka if the input is big enough the other don't matter. If we have a triply-nested for loop and ten doubly-nested for loops, as the input tends towards infinity the triply-nested for loop would outgrow the ten doubly-nested for loops extremely fast, so we would only consider the triply-nested for loop.

### Tip:

When loops are nested, multiply the complexity of the outer loop by the complexity of the inner loop. If there are C number of nested for loops, the time complexity would be O(n<sup>C</sup>).

### Rule of thumb:

For sequential statements (comparisons, assignments, etc), the complexity is constant: O(1).

For constant time loops (ex. for i in range(20)), the complexity is constant: O(1).

For nested loops, the complexity depends on the number of loops.

For logarithmic time loops, the complexity is O(log n).

For recursive functions, the complexity (worst case) is O(2<sup>n</sup>).

## Big O complexity chart of common data structure operations

<img width="506" alt="data complexity chart" src="https://github.com/user-attachments/assets/71c3e027-5c2c-4d1e-9a16-797fbfd926f1">

# Credits
Article I read: https://medium.com/coders-mojo/day-4-of-30-days-of-data-structures-and-algorithms-and-system-design-simplified-83d4c90d9115

Author: Naina Chaturvedi

This article: Written by me, Barca Koseoglu

Coding examples: Written and thought of by me, inspiration through Leetcode problem's I've done in the past

Images: Taken from the article I read
