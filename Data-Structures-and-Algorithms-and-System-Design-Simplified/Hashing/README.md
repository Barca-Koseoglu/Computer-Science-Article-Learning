# Hashing

## What is a hash table?

Hash tables are on of my favorite data structures and also one of the most useful. Whenever I try to solve a problem, I always try to use a hash map because of how convenient and efficient they are.

<img width="295" alt="hash map" src="https://github.com/user-attachments/assets/2ed50522-90e4-4c43-afbd-506884a27f61">


A hash table is a data structure that uses an associative method to store data in the form of **key-value** pairs. Keys are unique and ar mapped to values. 

Key-value pairing makes the data organization and access extremely efficient (hence why I like it so much), since in order to access the data you just need a key, which makes the time complexity O(1). Compare this to a list: to access a single random value in the list, the average time complexity is O(n).

Basically, hash tables are **very efficient and fast**.

## How does a hash table work?

A hash table takes an element you want to add or find (called the key) and runs it through a **hash function**, which is somehwat like a math equation, and the answer to that equation produces the index in the table that the **value** is stored in. Think of it this way: in a list, if you want to access an specfic index inside the list, you would simply write list[index] and get the **value** you want in O(1) time. 

**Hashing** is a technique that takes keys and converts them to indexes, and those indexes are mapped to values. Unique indexes are commonly generated using a **modulus** operator, which divides a number and returns the remainder, kind of like what we used to do in elementary school.

## Some extra information

The article I'm reading doesn't exactly cover how hashing really works and deals with overlaps of hash functions, so I'll talk about it myself.

### Hash sets

Hash sets, simply called sets, are hash maps (also called hash tables) but instead of key-value pairs, there are just keys. There can be no duplicates and it's unsorted, but it's as efficient as a hash map. They're really useful in many different types of problems.

### Buckets

Buckets are the places where the key-value pairs are stored. Each bucket corresponds to a hash value. What data structure are they, exactly? Most times, a list, and each index is a bucket. In a simple implementation of a hash map or set, an array of a fixed size will be used. In python, though, the array size is a power of 2 and is based on the number of elements in the array. I will explain further why this is.

### What exactly is a hash functon?

A hash function is just a calculation that spits out an index to access a values in a list. What is this calculation exacty, though? Simply, it's a mathematical operation of your choice, modulo the size of your list (by your choice, I mean it really doesn't matter). The modulus operator gives the remainder of a division operation. So if your random number is 125 and the size of your array is 10, you can do the calculation 125 % 10 and get 5. Then, you will store the key value pair in index 5.

In Python, hash function don't use the modulus operator to create values. Instead, they use bitwise masking, which is a technique to manipulate the bits of a binary number. Specificallu, Python uses the **AND** operator to take the remainder instead of dividing, which doesn't really make a difference unless you're performing millions of operations. They also make the size of their array powers of two to allow this method of hashing to work.

Why it works is a little hard to explain, but basically they do "hash(key) & (len(array)-1)*. hash(key) is the hashed key, the & operator is AND, and len(array)-1 in binary would be n ones if n 2<sup>n</sup> == len(array). len(array)-1 in binary is called the **bitmask**. Remember, this only works when the length of the array is a power of two, since binary counts up that way. When you subtract one, you're left with all ones, and you could get a value anywhere from 0 to len(array)-1, which are also the indices of the array. When it's like this, using the & operator gives us only the first n binary digits of the binary representation of the hash. It's exactly like modulus. Also, why should the bitwise all be ones, or why can't we have any length for the array? Because when you subtract one from an array whose length is not a power of 2, you won't be able to get the remainder. The ones are there because if the corresponding number of the hash is 1, then we will have 1. I the corresponding number is 0, then we will have 0. But if the number of the hash is 1 and the bitmask number in the same location is 0, we will get 0; bascially, it doesn't return the last n binary digits of the hash. Also if you don't know what the AND operator does in binary, it compares each 0 and 1 at the same position of two binary numbers, and returns 1 if both are 1 and 0 otherwise. There's a mathematical proof for this, but honestly it's unnecessary if you understand the logic.

Here's an example:

```python
hash_table = [0,0,0,0,0,0,0,0]

hash_val = 20 # in binary, 0b10100

bitmask = len(hash_table)-1 # in binary, 0b111

print(hash_val & bitmask) #output will be 0b100, or 4
```

### Collisions

What would you do if two different keys had the same hash value? One possible answer it to use a seperate data structure, like a linked list, to store them. If you get the same hash value, just traverse the list until you find the value you're seeking.

The way python does it is called quadratic probing. If a bucket already has a key, go to the indice next to it. If that one is full, go to the 2<sup>2</sup>th after it. If that one is also full, go to the 2<sup>3</sup>th after it. Progress like this quadratically until you find an empty space. Linear probing also works, but because values could end up in clusters and inserting/finding new values would be difficult.

### My implementation

This is my implementation of a simple hash set and hash map on Leetcode

[Hash set](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/705-Design-HashSet)

[Hash map](https://github.com/Barca-Koseoglu/My-Leetcode-Solutions/tree/main/706-Design-HashMap)

## Important patterns and techniques utilizing hash tables

1. Finding duplicates in an array
2. Finding a unique target sum
3. Accessing the index by keys
4. Some binary tree questions

## Some questions:

