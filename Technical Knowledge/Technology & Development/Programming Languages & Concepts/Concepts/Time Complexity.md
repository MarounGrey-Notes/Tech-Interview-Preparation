## Describe the time and space complexity analysis of algorithms. Explain Big O notation.
##### Simple Answer
Time complexity measures how fast an algorithm runs as input size grows. Space complexity measures memory usage. Big O notation describes complexity - O(n) means linear growth in time. This helps compare algorithms.
##### Book Answer
The time complexity of an algorithm expresses how the runtime scales with input size n. Space complexity measures how much additional memory is allocated. Big O notation formally describes the upper bound complexity e.g. O(n) for linear time algorithms. Analyzing time and space complexity allows comparing algorithms and picking optimal approaches.

## Explain the runtime complexity of common operations (search, insert, delete, etc) on basic data structures like arrays, linked lists, stacks, queues, trees, and hash tables.

| Data Structure | Access | Search | Insertion | Deletion |
| -------------- | ------ | ------ | --------- | -------- |
| **Array** | O(1) | O(n) | O(n) | O(n) |
| **Linked List** | O(n) | O(n) | O(1) | O(1) |  
| **Stack** | O(n) | O(n) | O(1) | O(1) |
| **Queue** | O(n) | O(n) | O(1) | O(1) |
| **Binary Search Tree** | O(log n) | O(log n) | O(log n) | O(log n) |
| **Balanced Binary Tree** | O(log n) | O(log n) | O(log n) | O(log n) |
| **Hash Table** | N/A | O(1) average | O(1) average | O(1) average |

* Arrays allow fast access by index in O(1) time, but searches, insertions and deletions require O(n) time since whole array needs traversing in worst case.
* Linked lists allow faster O(1) insertion and deletion by just updating the links. But searches take O(n) time due to linear traversal.
* Stacks and queues provide O(1) insertion and deletion from ends but O(n) search time.  
* Search trees like BST have O(log n) operations with balanced trees.  
* Hash tables provide average O(1) time for searches, inserts and deletes.
