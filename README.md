# Understanding Java Collections, Collection and Collections Framework

![java collections](https://github.com/user-attachments/assets/f2eb1c76-df97-4e8f-aa42-d74a20aab6c6)

Java provides a rich and powerful API for working with collections of objects. This is facilitated through the Collections Framework, which is a unified architecture for representing and manipulating collections. In this blog, we will delve into the key components of the `Collection`, `Collections` & `Collections Framework` with the various interfaces and classes that implement these concepts.

Let's first understand the terms :
- Collection - It is a interface.
- Collections - It is a utility class which provides various methods.
- Collections framework - It is a topic/concept or a unified architecture.

## Table of Contents
1. [Introduction to Collections Framework](#1introduction-to-collections-framework)
2. [Iterable Interface](#2iterable-interface)
3. [Collection Interface](#3collection-interface)
4. [Core Interfaces in the Collections Framework](#4core-interfaces-in-the-collections-framework)
5. [Key Classes in the Collections Framework](#6key-classes-in-the-collections-framework)
6. [Collections Utility Class](#5collections-utility-class)
7. [Conclusion](#8conclusion)

## 1.Introduction to Collections Framework

The Collections framework is a part of the `java.util` package and provides a well-designed set of interfaces and classes that make it easy to work with groups of objects.

### Hierarchy of Java Collections Framework

- `Iterable`Interface.
- `Collection` Interface (root interface).    
- Major interfaces derived from Collection :
  - List 
  - Set
  - Queue
  - Map (though it doesn’t extend Collection, it is a part of JCF).

### Benefits of Collections Framework
- **Reduces Programming Effort:** Provides useful data structures and algorithms out of the box.
- **Increases Performance:** High-performance implementations of data structures.
- **Promotes Software Reuse:** With well-defined interfaces, it is easy to reuse and extend.

## 2.Iterable Interface

It is designed to represent a collection of elements that can be iterated over. 

### Key Methods of Iterbale Interface 
- `iterator()` - method to travel element by element.
- `next()` - Checks if there are more elements to iterate over.
- `hasNext()` - Returns the next element in the iteration.

```java
Iterator it = obj.iterator();
while (it.hasNext()) {
System.out.print(it.next() + ", ");
}
```

## 3.Collection Interface

The interface is extended by other interfaces like `Set`, `List`, and `Queue`.

### Key Methods of Collection Interface 
- `boolean add(ele)` -  Adds an element to the collection.
- `boolean remove(Object)` - Adds all elements from the specified collection to the collection.
- `boolean contains(ele)` - Checks if the collection contains the specified element.
- `int size()` -  Returns the number of elements in the collection.
- `void clear()` - Removes all elements from the collection.
- `boolean isEmpty()` - Checks if the collection is empty.

```java

// Create a collection (ArrayList)
        Collection<String> collection = new ArrayList<>();
        
        // add(element) - Adds an element to the collection.
        collection.add("Apple");
        collection.add("Banana");
        collection.add("Cherry");
        System.out.println("After adding elements: " + collection);
        // Output: After adding elements: [Apple, Banana, Cherry]

        // remove(Object) - Removes the specified element from the collection.
        collection.remove("Banana");
        System.out.println("After removing 'Banana': " + collection);
        // Output: After removing 'Banana': [Apple, Cherry]

        // contains(element) - Checks if the collection contains the specified element.
        boolean containsApple = collection.contains("Apple");
        System.out.println("Collection contains 'Apple': " + containsApple);
        // Output: Collection contains 'Apple': true

        // size() - Returns the number of elements in the collection.
        int size = collection.size();
        System.out.println("Size of collection: " + size);
        // Output: Size of collection: 2

        // clear() - Removes all elements from the collection.
        collection.clear();
        System.out.println("After clearing the collection: " + collection);
        // Output: After clearing the collection: []

        // isEmpty() - Checks if the collection is empty.
        boolean isEmpty = collection.isEmpty();
        System.out.println("Collection is empty: " + isEmpty);
        // Output: Collection is empty: true
```

## 4.Core Interfaces in the Collections Framework

### List
- An ordered collection (also known as a sequence).
- Examples: ArrayList, LinkedList.

### Set
- Does not allow duplicate elements.
- Examples: HashSet, LinkedHashSet, TreeSet.

### Queue
- Designed for processing elements according to priority.
- Typically orders elements in a FIFO (first-in, first-out) manner.
- Examples: PriorityQueue, LinkedList.

### Map ( Does not extends Collection)
- An object that maps keys to values, with no duplicate keys allowed.
- Each key can map to at most one value.
- Examples: HashMap, TreeMap, LinkedHashMap.

## 6.Key Classes in the Collections Framework

The classes which implements interfaces like `List`, `Queue` and `Set`.

### List Interface classes -

- ArrayList
  - Resizable array.
  - Preferred for searching.

- LinkedList
  - Doubly-linked list implementation of the List and Deque interfaces.
  - Preferred for adding & deleting.

- Stack

  - `empty()` - Returns true if empty.
  - `push()` - Return ele in stack.
  - `pop()` - Return ele at top & then remove
  - `peek()` - Return ele at top
  - `search()` - Return index if ele is present, else return -1

### Queue Interface Classes

- PriorityQueue (Queue Interface)

  - `offer(ele)` - Inserts the specified element into the queue.
  - `poll()` - Retrieves and removes the head of the queue, or returns null if the queue is empty.
  - `remove()` - Retrieves and removes the head of the queue.
  - `peek()` - Retrieves, but does not remove, the head of the queue, or returns null if the queue is empty.
  - `element()` - Retrieves, but does not remove, the head of the queue.

- ArrayDeque (Dequeue Interface)

  - `offerFirst(ele)`, `pollFirst()`, `peekFirst(ele)`
  - `offerLast(ele)`, `pollLast()`, `peekLats()`

- ArrayBlockingQueue (BlockingQueue Interface)

  - size is fixed
  - powered by array
  
- LinkedBlockingQueue (BlockingQueue Interface)

  - bounded if size is given else unbounded
  - powered by linkedlist

### Set Interface Classes 

- HashSet (Set Interface)

  - powered by hashtable
  - ordering of ele is not define
  
- LinkedHashSet (Set Interface)

  - powered with doubly linkedlist & hashset
  - maintains the order

- TreeSet (SortedSet)

  - powered by tree data structure (self-balanced BST)
  - maintains sorted order of ele
 
### Map Interface

- HashMap (Map Interface)
  
> - contains key : value pair
> - powered by hashtable
> - insertion order not fix
> - not contain duplicate keys but can contain duplicate value
> - null key allowed once but null value allowed multiple

   - `put(key, value)` - Associates the specified value with the specified key in the map. If the map previously contained a mapping for the key, the old value is replaced.
   - `get(key)` - Returns the value to which the specified key is mapped, or null if the map contains no mapping for the key.
   - `remove()` - Removes the mapping for a key from this map if it is present.
   - `containsKey(key)` - Returns true if this map contains a mapping for the specified key.
   - `containsValue(value)` - Returns true if this map maps one or more keys to the specified value.
   - `isEmpty()` - Returns true if this map contains no key-value mappings.
   - `size()` - Returns the number of key-value mappings in this map.
   - `clear()` - Removes all of the mappings from this map. The map will be empty after this call returns.
 
```java
HashMap<String, Integer> map = new HashMap<>();
map.put("Apple", 10);
map.put("Banana", 20);
Integer value = map.get("Apple"); // Returns 10
map.remove("Banana"); // Removes the key "Banana" and its associated value
boolean hasApple = map.containsKey("Apple"); // Returns true
boolean hasValue10 = map.containsValue(10); // Returns true
boolean isEmpty = map.isEmpty(); // Returns false
int size = map.size(); // Returns 1
map.clear(); // Clears all mappings

   // Traversing using for-each loop (entrySet)
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
        }
        // Output:
        // Key: Apple, Value: 10
        // Key: Banana, Value: 20
        // Key: Cherry, Value: 30
```

- LinkedHashMap (Map Interface)
  - insertion order is maintain
 
- TreeMap (SortedMap)
  - insertion in specific order (ascending by default)

## 5.Collections Utility Class

The Collections class consists exclusively of static methods that operate on or return collections. It contains polymorphic algorithms that operate on collections, "wrappers", which return a new collection backed by a specified collection, and a few other odds and ends.

### Commonly Used Methods
- `sort()`
- `reverse()`
- `binarySearch()`
- `max()`
- `min()`

```java
 List = [5, 2, 9, 1, 7]
        Collections.sort(list);
        System.out.println("After sorting: " + list);
        // Output: After sorting: [1, 2, 5, 7, 9]
        
        Collections.reverse(list);
        System.out.println("After reversing: " + list);
        // Output: After reversing: [9, 7, 5, 2, 1]

        Collections.sort(list); // List must be sorted before binary search
        int index = Collections.binarySearch(list, 5);
        System.out.println("Index of element '5' after binary search: " + index);
        // Output: Index of element '5' after binary search: 2
        
        int maxElement = Collections.max(list);
        System.out.println("Maximum element: " + maxElement);
        // Output: Maximum element: 9
        
        int minElement = Collections.min(list);
        System.out.println("Minimum element: " + minElement);
        // Output: Minimum element: 1
```


## 8.Conclusion

The Java Collections Framework is a powerful and flexible tool for managing collections of objects. By understanding the Collection interface, the Collections utility class, and the various core interfaces and classes, you can effectively utilize these tools in your Java programs. This framework not only simplifies the task of managing collections but also enhances code readability and maintainability.
Feel free to experiment with the examples provided and explore the extensive capabilities of the Java Collections Framework!

