# Data Structures

A data structure is an organisation of values in a manner where they can be efficiently retrieved and transformed into other values.

Different data structures are suited to solving different problems.

- [Array](#array)
- [ArrayList](#arraylist)
- [LinkedList](#linkedlist)
- [Stack](#stack)
- [Queue](#queue)
- [HashTable](#hashtable)
- [Tree](#tree)
- [Trie](#trie)
- [Graph](#graph)
- [Heap](#heap)
- [Set](#set)

<!-- TODO sample implementation of each type of structure, and explanation of their use -->

## Array

An array is a fixed-length data structure whose elements are next to each other in memory. Arrays are a very important concept, and are used to implement many other data structures, such as ArrayLists and HashTables. An array of integers in Java looks like this:z

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

An ArrayList is similar to an Array, but is capable of dynamically resizing itself to accommodate additional elements after initialisation.

```
List<String> words = new ArrayList<String>();
words.add("London");
words.add("Bath");

System.out.println(words.get(1)); // prints "Bath"
System.out.println(words.size()); // prints 2
```

This is possible because it is backed internally by an array, which has a default capacity of N elements. When there is not enough space to add an element, a new larger array is initialised and the existing values are copied over. This behaviour is encapsulated so that client code is unaware of when the backing array is changed:

```
// initial capacity of 2 elements
List<String> words = new ArrayList<String>(2); // {null, null}
numbers.add("cat"); // {"cat", null}
numbers.add("dog"); // {"cat", "dog"}

// values copied to new array that is twice the size
numbers.add("chimp"); // {"cat", "dog", "chimp", null}
```

Typically, the new array is double the size of the previous one, although it's perfectly valid to use a different resizing factor.

When an array does needs to be copied, this takes O(n) time as each element must be moved across. However, because this happens so rarely, the insertion time is amortised to O(1) on average.

It is also worth noting that some implementations may copy values to a smaller array when elements are removed. This can allow additional memory to be reclaimed by the garbage collector.

### Complexity

| Access | Insertion Deletion | Search | Space |
|:------:|:------------------:|:------:|:-----:|
| `O(1)` | `O(1)`             | `O(n)` | `O(n)`|

It is important to note that for insertion/deletion, the O(1) case is amortised.

## LinkedList

## Stack

## Queue

## HashTable

## Tree

## Trie

## Graph

## Heap

## Set