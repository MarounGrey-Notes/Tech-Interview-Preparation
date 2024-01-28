## Compare and contrast arrays and linked lists - strengths, weaknesses, when to use which.

Arrays allow fast access/lookup by index but insertion/deletion is costly. Linked list insertion/deletion just updates the links, so it's faster, but lookup requires traversal.

## Implement a stack using an array. Write push and pop methods.
```
class Stack {
  constructor() {
    this.items = [];
  }

  push(item) {
    this.items.push(item);
  }

  pop() {
    return this.items.pop();
  }
}
```
