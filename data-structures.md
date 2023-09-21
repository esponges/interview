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
