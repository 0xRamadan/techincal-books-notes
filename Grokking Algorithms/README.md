# Grokking Algorithms Notes

## Content:

- Ch01 - Introduction to algorithms
- Ch02 - Selection sort
- Ch03 - Recursion
- Ch04 - Quicksort
- Ch05 - Hash tables
- Ch06 - Breadth-first search
- Ch07 - Dijkstra’s algorithm
- Ch08 - Greedy algorithm
- Ch09 - Dynamic programming
- Ch10 - K-nearest neighbors
- Ch11 - Where to go next

## Chapter 01: Introduction to algorithms

Some common Big O run times sorted from fastest to slowest:

- O(log n), also known as log time. Example: Binary search.
- O(n), also known as linear time. Example: Simple search.
- O(n \* log n). Example: A fast sorting algorithm, like quicksort.
- O(n2). Example: A slow sorting algorithm, like selection sort.
- O(n!). Example: A really slow algorithm, like the traveling Salesperson.

**Recap**

- Binary search is a lot faster than simple search.
- O(log n) is faster than O(n), but it gets a lot faster once the list of items you’re searching through grows.
- Algorithm speed isn’t measured in seconds.
- Algorithm times are measured in terms of growth of an algorithm.
- Algorithm times are written in Big O notation.

## Chapter 02: Selection Sort

- Linked lists are great if you’re going to read all the items one at a time.
- Arrays are great if you want to read random elements.
- Lists are better if you want to insert elements into the middle.
- A lot of use cases require random access, so arrays are used a lot. Arrays and lists are used to implement other data structures.
- Selection sort is a neat algorithm, but it’s not very fast. Quicksort is a faster sorting algorithm that only takes O(n log n) time.

**Recap**

- When you want to store multiple elements, use an array or a list.
- With an array, all your elements are stored right next to each other.
- With a list, elements are strewn all over, and one element stores the address of the next one.
- Arrays allow fast reads.
- Linked lists allow fast inserts and deletes.
- All elements in the array should be the same type (all ints, all doubles, and so on).

```python
# A simple Selection sort Algorithm
def findSmallest(arr):
    smallest = arr[0]
    smallest_index = 0
    for i in range(1, len(arr)):
        if arr[i] < smallest:
            smallest =arr[i]
            smallest_index = i
    return smallest_index

def selectionSort(arr):
    new_arr = []
    for i in range(len(arr)):
        smallest = findSmallest(arr)
        new_arr.append(arr.pop(smallest))
    return new_arr

if __name__ == '__main__':
    arr = list(map(int, input().split()))
    print(selectionSort(arr))
```

## Chapter 03: Recursion

- Pseudo code is a high-level description of the problem you’re trying to solve, in code. It’s written like code, but it’s meant to be closer to human speech.
- Recursion is where a function calls itself.
- Quote by Leigh Caldwell on Stack Overflow:

  "Loops may achieve a performance gain for your program. Recursion may achieve a performance gain for your programmer. Choose which is more important in your situation!"

- every recursive function has two parts: the base case, and the recursive case.

[image]

- Using the stack is convenient because you don’t have to keep track of a pile of boxes yourself—the stack does it for you. but there’s a cost: saving all that info can take up a lot of memory.

**Recap**

- Recursion is when a function calls itself.
- Every recursive function has two cases: the base case and the recursive case.
- A stack has two operations: push and pop.
- All function calls go onto the call stack.
- The call stack can get very large, which takes up a lot of memory.

## Chapter 04: Quicksort

- Quicksort is a sorting algorithm, and a much faster one than selection sort.
- To solve a problem using D&C, there are two steps:
  1. Figure out the base case. This should be the simplest possible case.
  2. Divide or decrease your problem until it becomes the base case.
- Remember, recursion keeps track of the state.
- When you’re writing a recursive function involving an array, the base case is often an empty array or an array with one element. If you’re stuck, try that first.

**Recap**

- D&C works by breaking a problem down into smaller and smaller pieces. If you’re using D&C on a list, the base case is probably an empty array or an array with one element.
- If you’re implementing quicksort, choose a random element as the pivot. The average runtime of quicksort is O(n log n)!
- The constant in Big O notation can matter sometimes. That’s why quicksort is faster than merge sort.
- The constant almost never matters for simple search versus binary search, because O(log n) is so much faster than O(n) when your list gets big.

## Chapter 05: Hash Tables

- Using hash tables for lookups
  Hash tables are great when you want to
  - Create a mapping from one thing to another thing
  - Look something up
- Preventing duplicate entries.

**Recap**

You’ll almost never have to implement a hash table yourself. The programming language you use should provide an implementation for you. You can use Python’s hash tables and assume that you’ll get the average case performance: constant time.
Hash tables are a powerful data structure because they’re so fast and they let you model data in a different way. You might soon find that you’re using them all the time:

- You can make a hash table by combining a hash function with an array.
- Collisions are bad. You need a hash function that minimizes collisions.
- Hash tables have really fast search, insert, and delete.
- Hash tables are good for modeling relationships from one item to another item.
- Once your load factor is greater than .07, it’s time to resize your hash table.
- Hash tables are used for caching data (for example, with a web server).
- Hash tables are great for catching duplicates.
