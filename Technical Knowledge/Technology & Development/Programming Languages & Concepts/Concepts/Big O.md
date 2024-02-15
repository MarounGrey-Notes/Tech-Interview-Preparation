# Big O notation and Time Complexity
Big O notation provides a formal way to classify algorithms by their worst-case time or space complexity as inputs grow towards infinity. For example, O(1) describes constant time, O(N) linear time, and O(log N) logarithmic time complexity classes. Big O abstracts away language and hardware specifics allowing technology-agnostic comparisons between approaches. This guide explains Big O analysis through examples for common data structure operations and code blocks. Understanding time and space complexity tradeoffs helps pick optimal data structures and write efficient algorithms ready for scale. We will build intuition around evaluating efficiency for constant, logarithmic, linear and exponential time algorithms in Big O terms.

![Big O Complexity Chart](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fpaper-attachments.dropbox.com%2Fs_2D428973624E7FC84C7D69D11421DE762BEA6B6F3361231FCDCAE0425D14526F_1664885448372_Untitled.drawio%2B17.png&f=1&nofb=1&ipt=a2ee11d26a5471e4c70928836d3a7b33785f35d951f2f00dc509a86d3442e2b0&ipo=images)

CheatSheet: https://zerotomastery.io/cheatsheets/big-o-cheat-sheet/?utm_source=udemy&utm_medium=coursecontent


## Time Complexity Analysis
Time that it takes to run the function depends on CPU, what other programs are curently running on the computer, programming languge and many other things.

*Interview Question: Describe the time and space complexity analysis of algorithms. Explain Big O notation.*
##### Simple Answer
Time complexity measures how fast an algorithm runs as input size grows. Space complexity measures memory usage. Big O notation describes complexity - O(n) means linear growth in time. This helps compare algorithms.
##### Book Answer
The time complexity of an algorithm expresses how the runtime scales with input size n. Space complexity measures how much additional memory is allocated. Big O notation formally describes the upper bound complexity e.g. O(n) for linear time algorithms. Analyzing time and space complexity allows comparing algorithms and picking optimal approaches.

## Data Structure Operations Complexity
*Interview Question: Explain the runtime complexity of common operations (search, insert, delete, etc) on basic data structures like arrays, linked lists, stacks, queues, trees, and hash tables.*

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

## Big O examples
Code examples of JavaScript functions with different algorithmic time complexities (Big O):

**O(1) - Constant time**
```js
function getFirstElement(arr) {
  return arr[0];
}
```
Accessing array first element takes constant time regardless of array size.

**O(log N) - Logarithmic time**
```js 
function binarySearch(sortedArray, key) {
  let start = 0;
  let end = sortedArray.length - 1;
  
  while (start <= end) {
    let mid = Math.floor((start + end) / 2);
    if (key === sortedArray[mid]) {
      return mid;
    }
    if (key < sortedArray[mid]) { 
      end = mid - 1; 
    } else {
      start = mid + 1;
    }
  }

  return -1; 
}
```
Binary search eliminates half of elements after each iteration.

**O(N) - Linear time**
```js
function printAllElements(arr) {
  arr.forEach(element => console.log(element));  
}
``` 
Need to iterate through all N elements.

**O(N^2) - Quadratic time**  
```js
function printAllPossibleOrderedPairs(arr) {
  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < arr.length; j++) {
      console.log(arr[i], arr[j]); 
    }
  }
}
```
Nested iterations each running N times.

# Space Complexity
When a program executes it has 2 ways to remember things:
- Heap: Sore variables
- Stack: Keep track of function calls

**O(1) Constant Space**
```js
function sum(arr) {
  let sum = 0;
  
  for(let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  
  return sum; 
}
```

This function iterates over the input array but only uses a single sum variable for computation. So additional space used does not depend on input size n. It is constant O(1) space.


**O(n) Linear Space**

```js
function createCopy(arr) {
  let copy = [];
  
  for(let i = 0; i < arr.length; i++) {
    copy.push(arr[i]);  
  }

  return copy; 
}
```

Here the copy array being created and returned has a size proportional to the input array. The larger the input array, more space needed. This makes it a O(n) linear space complexity.


