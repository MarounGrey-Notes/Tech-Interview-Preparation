# Big O notation and Time Complexity
![Big O Complexity Chart](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fpaper-attachments.dropbox.com%2Fs_2D428973624E7FC84C7D69D11421DE762BEA6B6F3361231FCDCAE0425D14526F_1664885448372_Untitled.drawio%2B17.png&f=1&nofb=1&ipt=a2ee11d26a5471e4c70928836d3a7b33785f35d951f2f00dc509a86d3442e2b0&ipo=images)

CheatSheet: https://zerotomastery.io/cheatsheets/big-o-cheat-sheet/?utm_source=udemy&utm_medium=coursecontent


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
