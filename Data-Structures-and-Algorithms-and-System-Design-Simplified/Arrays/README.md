# Arrays

## What are arrays?

Arrays are one of the most basic and important data structures in all of computer science. It is a collection of contiguous memory locations which is **zero-indexed**, meaning the "boxes" of the array start counting from 0. The length of the array is total number of elements in it.

<img width="533" alt="array" src="https://github.com/user-attachments/assets/02be1750-fd34-423a-85b8-4aae107e462a">

In python, the language I use, an array is just a list that stores elements of different types of data. the list's index starts from 0 and its last element can be access going backwards by -1 (arr[-1]).

<img width="560" alt="array2" src="https://github.com/user-attachments/assets/bff8da61-c9a5-48f3-a653-4a458fc2b36a">

## How do arrays work?

Arrays allocate blocks of memory to hold elements. Each element is assigned a unique index (sometimes called a subscript) that can be used to access and change the element. They are stored in contiguous (meaning side-by-side) memory locations. Arrays are collections of objects which can be either the same or different data types. Allocating the elements to contiguous memory locations allows one to insert, delete, update, and add to the array.

Arrays in python, as said, are known as lists. They have a bunch of different operations that allow us to manipulate them to solve problems.

## Important patterns and techniques to solve problems

Manipulating arrays in specific and clever ways allows us to solve many problems. There are some very common patterns used to solve different problems.

**Two pointers**: One of my favorite techniques. It uses two variables as indicies to traverse arrays and find specific elements or patterns. It's commonly used in problems involving sorting, searching,a dn removing duplicates.

**Sliding window**: This technique keeps track of a "window" of elements in an array, like a specific portion. This technique is often utilied to find the maximum or minimum value in a **subarray** (an array withing the original array).

**Dynamic programming**. A more advanced technique used to solve problems by breaking them down into smaller parts. It can be used for a lot of different, more complex problems that may not seem so straightforward, even by brute forcing a solution.

**Sorting**: Sorting is a fundamental operation used in many problems and real life. Arrays let us sort elements using different techniques, like Merge Sort.

### Some problems utilizing arrays (linked to my solutions):

[Find subarrays with equal sum](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/2395-Find-Subarrays-With-Equal-Sum)

[Jump game](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/55-Jump-Game)

[Gas Stations](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/134-Gas-Station)

[2sum](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/1-Two-Sum) (Brute force solution would be better for this article but I used a dictionary for efficiency. It still utilizes access values with indices, though)

[Search in rotated sorted array](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/33-Search-In-Rotated-Sorted-Array)

[Merge two arrays](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/merge-sorted-array)

## Complexity Analysis

Read my article on [complexity analysis](https://github.com/Barca-Koseoglu/Computer-Science-Article-Learning/tree/main/Data-Structures-and-Algorithms-and-System-Design-Simplified/Complexity-Analysis) if you don't know what it is already.

To create an array: Time O(1), Space O(n)

Insertion and deletion at the beginning of the array (index 0): O(n) time if the array is not full

Insertion and deletion at the end of the array (index -1): O(1)

Insertion and deletion somewhere in the middle: O(n)

Using the index to access something in the array: O(1)

Searching for an item in the array: O(n)

## Tips and techniques to solve array questions

1. Before thinking about a solution, check to see if the array is sorted or not. If it is, the most optimal solution is most likely found using binary search
2. Know and implement important list methods (you could always use google if you forget)
3. Know how to implement recursion, although things could get tricky
4. Know how to manipulate indexes and retrieve values
5. Know how to reverse, sort, and slice (split up parts of) arrays

# Credits

Article I read: https://medium.com/coders-mojo/day-11-of-30-days-of-data-structures-and-algorithms-and-system-design-simplified-arrays-bf7045a3c98b

Author: Naina Chaturvedi

This article: Written by me, Barca Koseoglu

Problem solutions: Made by me, in my [Leetcode solutions page](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions)

Images: Taken from the article I read
