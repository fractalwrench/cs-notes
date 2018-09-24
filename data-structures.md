# Data Structures

A data structure is an organisation of values in a manner where they can be efficiently retrieved and transformed into other values.

Different data structures are suited to solving different problems.

- [Array](#Array)
- [ArrayList](#ArrayList)
- [LinkedList](#LinkedList)
- [Stack](#Stack)
- [Queue](#Queue)
- [HashTable](#HashTable)
- [Tree](#Tree)
- [Trie](#Trie)
- [Graph](#Graph)
- [Heap](#Heap)

<!-- TODO sample implementation of each type of structure, and explanation of their use -->

## Array

An array is a fixed-length data structure whose elements are next to each other in memory. Arrays are a very important concept, and are used to implement many other data structures, such as ArrayLists and HashTables. An array of integers in Java looks like this:

```
int[] numbers = {2, 13, 8, 293, -8, 0};
System.out.println(numbers[0]); // prints the zeroth element, 2
System.out.println(numbers[3]); // prints the 3rd element, 293
System.out.println(numbers.length); // prints the array length, 6
```

Each element within the array can be accessed, and altered, via an index. In Java the index starts at 0. In the example below, we mutate the value at the 3rd index:

```
numbers[3] = 999;
System.out.println(numbers[3]); // prints the 3rd element, 999
```

A common use-case for arrays is to sort their elements so that they are arranged in a particular order. For example, a dictionary may wish to order words alphabetically:

```
String[] words = {"abacus", "zeitgeist", "duck"};
Arrays.sort(words); // sorts the array in place
// {"abacus", "duck", "zeitgeist"};
```

Arrays can hold references to any type in Java - it's even possible to create arrays of arrays! Multidimensional arrays can be useful for modelling graphs, or mathematical matrices:

```
int[][] matrix = {
    {3, 67, 2},
    {-9, 5, 330}
};
matrix[1, 2]; // access 330
```

### Complexity

| Access | Insertion Deletion | Search | Space |
|:------:|:------------------:|:------:|:-----:|
| `O(1)` | `O(n)`             | `O(n)` | `O(n)`|

Because arrays are of a fixed size, it is necessary to copy all the elements to a new array when inserting or deleting values.

If the data can be ordered, it may be possible to improve search from `O(n)` to `O(log n)` by using a binary search.

## ArrayList

## LinkedList

## Stack

## Queue

## HashTable

## Tree

## Trie

## Graph

## Heap