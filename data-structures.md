# Data Structures

## Space and Time Complexity
- What are the principal time complexities?
1. Constant time (O(1)): The algorithm takes the same amount of time to run, regardless of the size of the input. For example, an algorithm to return the length of a list always takes a constant amount of time, regardless of the number of elements in the list.
2. Linear time (O(n)): The algorithm takes time proportional to the size of the input. For example, an algorithm to **search** for an element in a list takes linear time, because it has to examine each element in the list.
3. Quadratic time (O(n^2)): The algorithm takes time proportional to the square of the size of the input. For example, an algorithm to **sort** a list of numbers takes quadratic time, because it has to compare each element in the list with every other element.
4. Exponential time (O(2^n)): The algorithm takes time proportional to the power of 2 of the size of the input. For example, an algorithm to find the longest common subsequence of two strings takes exponential time, because it has to _consider all possible combinations_ of the two strings.

- And the principal space complexities?
1. Constant space (O(1)): The algorithm uses a **fixed amount of memory**, regardless of the size of the input. For example, an algorithm to return the length of a list always uses a constant amount of memory, because it only needs to store a few variables.
2. Linear space (O(n)): The algorithm uses **memory proportional to the size of the input**. For example, an algorithm to **sort** a list of numbers uses linear space, because it needs to store a copy of the list.
3. Quadratic space (O(n^2)): The algorithm uses **memory proportional to the square of the size of the input**. For example, an algorithm to find the longest common subsequence of two strings uses quadratic space, because it needs to store a table of **all possible combinations** of the two strings.

## Arrays
Arrays are a collection of elements of the same type. They are stored in contiguous memory locations. The elements of an array can be accessed using an index. The index of the first element is 0 and the index of the last element is the length of the array minus 1.

When we know the size of the array in advance they are a good option. They are also a good option when we need to access the elements of the array in a random order. The time complexity of accessing an element in an array is O(1).

If an element from the array is removed or added, the elements after it have to be shifted. This is an expensive operation. The time complexity of accessing an element in an array is O(1). The time complexity of adding or removing an element from an array is O(n). Also, the space in memory allocated for that element is not freed inmediately and but has to be garbage collected later.

```javascript
const arr = [1, 2, 3, 4, 5];

// Remove the second element from the array.
arr.splice(1, 1);

// The array now contains [1, 3, 4, 5].
console.log(arr);

// The space in memory that was occupied by the removed element is still allocated,
// but it is marked as "free" and can be reused by other objects in the program.

// If no other objects are using that space, it will eventually be reclaimed by the garbage collector.
```

## Linked Lists
Linked lists are a collection of elements of the same type. They are stored in non-contiguous memory locations. Each element of the linked list is called a node. Each node contains the value of the element and a pointer to the next node in the list. The last node of the list points to null.

When we don't know the size of the list in advance they are a good option. They are also a good option when we need to access the elements of the list in a sequential order. The time complexity of accessing an element in a linked list is O(n). However, if we want to access a random element in the list, LLs are not a good option since we have to traverse the list from the beginning to the element we want to access.

- Node

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
  }
}
```

- Traverse lists

```javascript
function traverseList(head) {
  // where head is the first node of the list
  // current is a pointer to the current node
  // if we want to access to a node we must "move" the pointer to that node and change its value
  let current = head;
  while (current !== null) {
    console.log(current.value);
    current = current.next;
  }
}
```

### Stack
A stack is a data structure that stores elements in a LIFO (Last In First Out) order. The last element added to the stack is the first one to be removed. The operations of adding and removing elements from a stack are called push and pop respectively.

Stacks are used in many algorithms. For example, they are used in the implementation of the call stack in programming languages. They are also used in the implementation of undo/redo functionality in text editors. 

They are also useful in the implementation of backtracking (recursion) algorithms because they can be used to keep track of the current state of the algorithm. When the algorithm needs to backtrack, it can simply pop the current state off the stack and return to the previous state.

Disadvantages of stacks:
- They are not random access. We can only access the top element of the stack.
- They are not dynamic. We have to specify the maximum number of elements that the stack can hold when we create it.

```javascript
class Stack {
  constructor() {
    this.items = [];
  }

  push(element) {
    this.items.push(element);
  }

  pop() {
    if (this.items.length === 0) {
      return "Underflow";
    }
    return this.items.pop();
  }

  peek() {
    return this.items[this.items.length - 1];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  printStack() {
    let str = "";
    for (let i = 0; i < this.items.length; i++) {
      str += this.items[i] + " ";
    }
    return str;
  }
}
```

## Queue
A queue is a data structure that stores elements in a FIFO (First In First Out) order. The first element added to the queue is the first one to be removed. The operations of adding and removing elements from a queue are called enqueue and dequeue respectively.

Queues are used in many algorithms. For example, they are used in the implementation of breadth-first search (BFS) algorithm. They are also used in the implementation of the message queue in operating systems.

Disadvantages of queues:
- They are not random access. We can only access the first element of the queue.
- They are not dynamic. We have to specify the maximum number of elements that the queue can hold when we create it.

```javascript
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(element) {
    this.items.push(element);
  }

  dequeue() {
    if (this.items.length === 0) {
      return "Underflow";
    }
    return this.items.shift();
  }

  front() {
    if (this.items.length === 0) {
      return "No elements in Queue";
    }
    return this.items[0];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  printQueue() {
    let str = "";
    for (let i = 0; i < this.items.length; i++) {
      str += this.items[i] + " ";
    }
    return str;
  }
}
```

## Hash Tables
In Javascript, objects are hash tables. A hash table is a data structure that maps keys to values. It uses a hash function to compute an index into an array of buckets or slots, from which the desired value can be found.

Hash tables are used in many algorithms. For example, they are used in the implementation of associative arrays, database indexing, caches, etc.

Disadvantages of hash tables:
- They are not ordered. The order of the elements is not guaranteed.
- They are not dynamic. We have to specify the maximum number of elements that the hash table can hold when we create it.

## Trees
A tree is a data structure that stores elements in a hierarchical way. Each element in the tree is called a node. The top node of the tree is called the root node. The nodes that are directly under a node are called its children. The node that is directly above a node is called its parent. The nodes that have no children are called leaf nodes.

Trees are used in many algorithms. For example, they are used in the implementation of binary search trees, heaps, etc.

Some examples of how binary trees are used in real-world applications:

- File systems use binary trees to store files and directories.
- Databases use binary trees to index data.
- Search engines use binary trees to index web pages.
- Compilers use binary trees to parse code.
- Computer graphics use binary trees to represent 3D models

Disadvantages of trees:
- They are not random access. We can only access the root node of the tree.

### Binary Search Tree
A binary search tree is a binary tree in which the value of each node is greater than or equal to the values in the nodes of its left subtree and less than or equal to the values in the nodes of its right subtree.

Binary search trees are used in many algorithms. For example, they are used in the implementation of associative arrays, database indexing, caches, etc.

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

// creating a BST
const values = [15, 25, 10, 7, 22, 17, 13, 5, 9, 27];
const root = new Node(values[0]);

for (let i = 1; i < values.length; i++) {
  // always start at the root
  let current = root;
  while (true) {
    // find the side where the new node should be inserted
    // smaller values go to the left
    if (values[i] < current.value) {
      if (current.left === null) {
        current.left = new Node(values[i]);
        break;
      } else {
        current = current.left;
      }
    // larger values go to the right
    } else if (values[i] > current.value) {
      if (current.right === null) {
        current.right = new Node(values[i]);
        break;
      } else {
        current = current.right;
      }
    } else {
      break;
    }
  }
}
```
