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

[2um](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/1-Two-Sum) (Brute force solution would be better for this article but I used a dictionary for efficiency. It still utilizes access values with indices, though)

[Search in rotated sorted array](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/33-Search-In-Rotated-Sorted-Array)

Merge two arrays - later

tbc
