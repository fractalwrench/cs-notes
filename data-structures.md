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

A LinkedList is formed of nodes which contain a data value, and a pointer to other nodes. For a singly linked list, each node points to the next node in the Collection.

```
[59] -> [9044] -> [-22] -> [3]
```

A doubly-linked-list contains pointers to the next *and* previous node.

One of the main benefits of a LinkedList is that it is possible to insert or delete elements at the head or tail in constant time. A trade-off is that the time taken to access individual elements is O(n), unlike the O(1) of an Array.

A node within a LinkedList is very simple to implement in Java:

```
class Node {
    String data;
    Node next; // points to the next node in the list
}

// create a simple linkedlist with 2 elements
Node head = new Node();
head.data = "first node";

Node another = new Node();
another.data = "second node";
head.next = another; // forms a linked list
```

When working with LinkedLists, be very careful to account for the head/tail nodes. Some common mistakes include:

- Forgetting that the next value for head/tail nodes can be null
- Neglecting to remove references when removing nodes

### Common Tricks

#### Runner technique

In the runner technique, two iterators 'run' through the LinkedList simultaneously. One runner is faster than the other, usually by a factor of two. This has the useful property that the pointers will simultaneously reach the midpoint and end of the list.

#### Recursion

LinkedList problems can commonly be solved with recursion.

### Complexity

| Access | Insertion Deletion | Search | Space |
|:------:|:------------------:|:------:|:-----:|
| `O(n)` | `O(1)`             | `O(n)` | `O(n)`|

## Stack

## Queue

## HashTable

## Tree

## Trie

## Graph

## Heap

## Se