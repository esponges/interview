# Data Structures

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
