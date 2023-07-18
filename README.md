# Cheatsheets any issue more clearity  [click me](https://leetcode.com/explore/interview/card/cheatsheets/720/resources/4725/)

This repository contains a collection of cheat sheets that you can use as you solve problems and prepare for interviews. You will find:

🕰️ Time complexity (Big O) cheat sheet
📊 General DS/A flowchart (when to use each DS/A)
🎓 Stages of an interview cheat sheet

## 🕰️ Time complexity (Big O) cheat sheet

First, let's talk about the time complexity of common operations, split by data structure/algorithm. Then, we'll talk about reasonable complexities given input sizes.

### Arrays (dynamic array/list)

Given n = arr.length,

Add or remove element at the end: O(1) amortized
Add or remove element from arbitrary index: O(n)
Access or modify element at arbitrary index: O(1)
Check if element exists: O(n)
Two pointers: O(n⋅k), where k is the work done at each iteration, includes sliding window
Building a prefix sum: O(n)
Finding the sum of a subarray given a prefix sum: O(1)

### Strings (immutable)

Given n = s.length,

Add or remove character: O(n)
Access element at arbitrary index: O(1)
Concatenation between two strings: O(n+m), where m is the length of the other string
Create substring: O(m), where m is the length of the substring
Two pointers: O(n⋅k), where k is the work done at each iteration, includes sliding window
Building a string from joining an array, stringbuilder, etc.: O(n)

# Linked Lists

This repository contains an implementation of a singly linked list in Java. You will find:

📝 Time complexity cheat sheet
📊 General DS/A flowchart (when to use each DS/A)
📚 Stages of an interview cheat sheet

## 📝 Time complexity cheat sheet

Given n as the number of nodes in the linked list,

Add or remove element given pointer before add/removal location: O(1)
Add or remove element given pointer at add/removal location: O(1) if doubly linked
Add or remove element at arbitrary position without pointer: O(n)
Access element at arbitrary position without pointer: O(n)
Check if element exists: O(n)
Reverse between position i and j: O(j−i)
Detect a cycle: O(n) using fast-slow pointers or hash map


## Hash table/dictionary

- Given n = dic.length,

Add or remove key-value pair: O(1)
Check if key exists: O(1)
Check if value exists: O(n)
Access or modify value associated with key: O(1)
Iterate over all keys, values, or both: O(n)
Note: the O(1) operations are constant relative to n. In reality, the hashing algorithm might be expensive. For example, if your keys are strings, then it will cost O(m) where 

m is the length of the string. The operations only take constant time relative to the size of the hash map.

## Set

Given n = set.length,

Add or remove element: O(1)
Check if element exists: O(1)
The above note applies here as well.

## Stack

Stack operations are dependent on their implementation. A stack is only required to support pop and push. If implemented with a dynamic array:

Given n = stack.length,

Push element: O(1)
Pop element: O(1)
Peek (see element at top of stack): O(1)
Access or modify element at arbitrary index: O(1)
Check if element exists: O(n)

## Queue

Queue operations are dependent on their implementation. A queue is only required to support dequeue and enqueue. If implemented with a doubly linked list:

Given n = queue.length,
O(1)
Dequeue element: O(1)
Peek (see element at front of queue): O(1)
Access or modify element at arbitrary index: O(n)
Check if element exists: O(n)
Note: most programming languages implement queues in a more sophisticated manner than a simple doubly linked list. Depending on implementation, accessing elements by index may be faster than 
O(n), or 

O(n) but with a significant constant divisor.

## Binary tree problems (DFS/BFS)

Given 

n as the number of nodes in the tree,

Most algorithms will run in O(n⋅k) time, where 
�
k is the work done at each node, usually O(1). This is just a general rule and not always the case. We are assuming here that BFS is implemented with an efficient queue.

## Binary search tree

Given 

n as the number of nodes in the tree,

Add or remove element: O(n) worst case, 
log
⁡
O(logn) average case
Check if element exists: O(n) worst case, log
⁡

O(logn) average case
The average case is when the tree is well balanced - each depth is close to full. The worst case is when the tree is just a straight line.

## Heap/Priority Queue

Given n = heap.length and talking about min heaps,

Add an element: log
⁡
O(logn)
Delete the minimum element:log
⁡
O(logn)
Find the minimum element: O(1)
Check if element exists: 

O(n)
Binary search

Binary search runs in log
⁡
O(logn) in the worst case, where 
�
n is the size of your initial search space.

- Miscellaneous

## Sorting: log
⁡

O(n⋅logn), where 

n is the size of the data being sorted
DFS and BFS on a graph: O(n⋅k+e), where 

n is the number of nodes, 

e is the number of edges, if each node is handled in 

O(1) other than iterating over edges
DFS and BFS space complexity: typically 

O(n), but if it's in a graph, might be 

O(n+e) to store the graph
Dynamic programming time complexity: 

O(n⋅k), where 

n is the number of states and 

k is the work done at each state
Dynamic programming space complexity: 


O(n), where 

n is the number of states
Input sizes vs time complexity
The constraints of a problem can be considered as hints because they indicate an upper bound on what your solution's time complexity should be. Being able to figure out the expected time complexity of a solution given the input size is a valuable skill to have. In all LeetCode problems and most online assessments (OA), you will be given the problem's constraints. Unfortunately, you will usually not be explicitly told the constraints of a problem in an interview, but it's still good for practicing on LeetCode and completing OAs. Still, in an interview, it usually doesn't hurt to ask about the expected input sizes.

n <= 10

The expected time complexity likely has a factorial or an exponential with a base larger than 2 - 

O(n 
2
 ⋅n!) or 

4

O(4 
n
 ) for example.

You should think about backtracking or any brute-force-esque recursive algorithm. n <= 10 is extremely small and usually any algorithm that correctly finds the answer will be fast enough.

10 < n <= 20

The expected time complexity likely involves 

2

O(2 
n
 ). Any higher base or a factorial will be too slow (
3
20
3 
20
  = ~3.5 billion, and 
20
!
20! is much larger). A 
2

2 
n
  usually implies that given a collection of elements, you are considering all subsets/subsequences - for each element, there are two choices: take it or don't take it.

Again, this bound is very small, so most algorithms that are correct will probably be fast enough. Consider backtracking and recursion.

20 < n <= 100

At this point, exponentials will be too slow. The upper bound will likely involve 

O(n 

Problems marked as "easy" on LeetCode usually have this bound, which can be deceiving. There may be solutions that run in 

O(n), but the small bound allows brute force solutions to pass (finding the linear time solution might not be considered as "easy").

Consider brute force solutions that involve nested loops. If you come up with a brute force solution, try analyzing the algorithm to find what steps are "slow", and try to improve on those steps using tools like hash maps or heaps.

100 < n <= 1,000

In this range, a quadratic time complexity 

2
O(n 
2
 ) should be sufficient, as long as the constant factor isn't too large.

Similar to the previous range, you should consider nested loops. The difference between this range and the previous one is that 

2

O(n 
2
 ) is usually the expected/optimal time complexity in this range, and it might not be possible to improve.

1,000 < n < 100,000


1
0
5
n<=10 
5
  is the most common constraint you will see on LeetCode. In this range, the slowest acceptable common time complexity is 


log
⁡

O(n⋅logn), although a linear time approach 

O(n) is commonly the goal.

In this range, ask yourself if sorting the input or using a heap can be helpful. If not, then aim for an 

O(n) algorithm. Nested loops that run in 

2

O(n 
2
 ) are unacceptable - you will probably need to make use of a technique learned in this course to simulate a nested loop's behavior in 

1

O(1) or 

log
⁡


O(logn):

## Hash map
A two pointers implementation like sliding window
Monotonic stack

## Sorting algorithms
All major programming languages have a built-in method for sorting. It is usually correct to assume and say sorting costs 
