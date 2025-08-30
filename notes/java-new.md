# Java

---

## Java Basics
### History of Java, JDK vs JRE vs JVM
### Features of Java
### Data Types (primitive & wrapper classes)
### Variables (local, instance, static)
### Operators (arithmetic, logical, relational, bitwise, ternary)
### Control Flow (if-else, switch, loops – for, while, do-while)
### Type Casting (widening, narrowing, autoboxing/unboxing)

---

## Object-Oriented Programming (OOP)
### Class & Objects
### Constructors (default, parameterized, constructor chaining)
### Inheritance (single, multilevel, hierarchical, multiple via interfaces)
### Polymorphism (method overloading, overriding, dynamic dispatch)
### Abstraction (abstract class vs interface)
### Encapsulation (getters & setters, access modifiers)

---

## Order of Elements in Java Class
- Package Statement
- Import Statements
- Class Declaration
- Constants (static final) # public static final int MAX_USERS = 1000;
- Static variables (static) # private static int totalUsers;
- Instance Variables (private first, then protected, then public)
- Primitives (boolean, byte, short, int, long, float, double)
- Immutable objects (`String`, `UUID`)
- Collections (List, Set, Map)
- Custom objects (Person, Address)
- Constructors (Default, Parameterized, Static Factory, Copy Constructor, Builder Pattern)
- Static Methods (Public, Private)
- Instance Methods (Public, Protected, Private)
- Override methods toString(), equals(), hashCode()
- Private helper methods last
- Inner Classes

---

## Access Modifiers
### public, private, protected, default
### Where to apply (class, methods, variables, constructors)
### Difference between package-level and external access

---

## Strings
### String Methods (`length()`, `charAt()`, `substring()`, etc.)
### Immutability of String
### String Pool
### String vs StringBuilder vs StringBuffer

---

## StringBuilder
### append(), insert(), replace(), delete(), reverse()
### Capacity & ensureCapacity()
### Difference with StringBuffer

---

## Enums
### Defining enums
### Enum methods (`values()`, `valueOf()`, `ordinal()`)
### Enum with fields & methods
### Enum in switch-case

---

## Exceptions
### Types of Exceptions (checked, unchecked, errors)
### try-catch-finally
### throw vs throws
### Custom exceptions
### Multi-catch block
### try-with-resources

---

## Inner Classes & Annotations
### Inner Classes (member, static, local, anonymous)
### Built-in Annotations (`@Override`, `@Deprecated`, `@SuppressWarnings`)
### Meta-annotations (`@Target`, `@Retention`)
### Custom annotations

---

## Collections Framework

### List : ArrayList, LinkedList, Vector, Stack
`add(E e)` : Adds an element to the end of the list.
`add(int index, E element)` : Inserts an element at the specified index.
`get(int index)` : Retrieves an element at the specified index.
`remove(int index)` : Removes the element at the specified index.
`remove(Object o)` : Removes the first occurrence of the specified object.
`set(int index, E element)` : Replaces the element at the specified index.
`contains(Object o)` : Returns true if found.
`indexOf(Object o)` : Returns the index of the first occurrence of the specified element.
`lastIndexOf(Object o)` : Returns the index of the last occurrence of the specified element. If not found returns -1.
`addAll(Collection<? extends E> c)` : Adds all elements from the collection to the list.
`addAll(int index, Collection<? extends E> c)` : Inserts all elements at the specified index.
`removeAll(Collection<?> c)` : Removes all elements that are contained in the specified collection.
`retainAll(Collection<?> c)` : Retains only elements that are contained in the specified collection.
`subList(int fromIndex, int toIndex)` : Returns a view of the portion of the list between the specified indexes.
`toArray()` : Returns an array containing all elements in the list.
`toArray(T[] a)` : Returns an array containing all elements in the list with the specified type.
`iterator()` : Returns an iterator over the elements in the list.
`listIterator()` : Returns a list iterator over the elements in the list.
`listIterator(int index)` : Returns a list iterator starting at the specified position.

---

### Set : HashSet, LinkedHashSet, TreeSet
`add(E e)` : Adds an element to the set.
`remove(Object o)` : Removes the specified element from the set.
`contains(Object o)` : Checks if the set contains the specified element.
`toArray()` : Converts the set to an array.
`addAll(Collection<? extends E> c)` : Adds all elements from the collection to the set.
`removeAll(Collection<?> c)` : Removes all elements that are contained in the specified collection.
`retainAll(Collection<?> c)` : Retains only elements that are contained in the specified collection.
`containsAll(Collection<?> c)` : Returns true if the set contains all elements of the specified collection.
`iterator()` : Returns an iterator over the elements in the set.
`toArray(T[] a)` : Returns an array containing all elements in the set with the specified type.

---

### Queue : PriorityQueue, LinkedList, ArrayDeque
`offer(E e)` : Adds an element to the queue (returns false if full).
`poll()` : Removes and returns the front element (returns null if empty).
`peek()` : Retrieves the front element (returns null if empty).
`add(E e)` : Inserts the element into the queue (throws exception if full).
`remove()` : Retrieves and removes the head of the queue (throws exception if empty).
`element()` : Retrieves the head of the queue (throws exception if empty).
`iterator()` : Returns an iterator over the elements in the queue.
`toArray()` : Returns an array containing all elements in the queue.

---

### Deque : ArrayDeque, LinkedList
`offerFirst(E e)` : Adds an element at the front of the deque (returns false if full).
`offerLast(E e)` : Adds an element at the end of the deque (returns false if full).
`pollFirst()` : Removes and returns the front element (returns null if empty).
`pollLast()` : Removes and returns the last element (returns null if empty).
`peekFirst()` : Retrieves the front element (returns null if empty).
`peekLast()` : Retrieves the last element (returns null if empty).
`addFirst(E e)` : Inserts an element at the front (throws exception if full).
`addLast(E e)` : Inserts an element at the end (throws exception if full).
`removeFirst()` : Removes and returns the first element (throws exception if empty).
`removeLast()` : Removes and returns the last element (throws exception if empty).
`getFirst()` : Retrieves the first element (throws exception if empty).
`getLast()` : Retrieves the last element (throws exception if empty).
`removeFirstOccurrence(Object o)` : Removes the first occurrence of the specified element.
`removeLastOccurrence(Object o)` : Removes the last occurrence of the specified element.
`push(E e)` : Pushes an element onto the stack (front of deque).
`pop()` : Pops an element from the stack (front of deque).

---

### Map : HashMap, LinkedHashMap, TreeMap, Hashtable
`put(K key, V value)` : Adds or updates a key-value pair in the map.
`putIfAbsent(K key, V value)` : Adds key-value only if key is absent.
`get(Object key)` : Retrieves the value associated with the key.
`getOrDefault(Object key, V defaultValue)` : Returns the value for the key, or default value if key is not found.
`remove(Object key)` : Removes the key-value pair for the specified key.
`remove(Object key, Object value)` : Removes the entry only if key is mapped to the specified value.
`replace(K key, V value)` : Replaces the entry for the specified key only if it's currently mapped.
`replace(K key, V oldValue, V newValue)` : Replaces the entry only if currently mapped to the specified value.
`containsKey(Object key)` : Checks if the map contains the specified key.
`containsValue(Object value)` : Checks if the map contains the specified value.
`keySet()` : Returns a set of all keys in the map.
`values()` : Returns a collection of all values in the map.
`entrySet()` : Returns a set of all key-value pairs in the map.
`putAll(Map<? extends K, ? extends V> m)` : Copies all mappings from the specified map.
`compute(K key, BiFunction<? super K, ? super V, ? extends V> remappingFunction)` : Computes a mapping for the specified key.
`computeIfAbsent(K key, Function<? super K, ? extends V> mappingFunction)` : Computes value if key is absent.
`computeIfPresent(K key, BiFunction<? super K, ? super V, ? extends V> remappingFunction)` : Computes value if key is present.
`merge(K key, V value, BiFunction<? super V, ? super V, ? extends V> remappingFunction)` : Merges the specified value with existing value.
`forEach(BiConsumer<? super K, ? super V> action)` : Performs the given action for each entry.
`replaceAll(BiFunction<? super K, ? super V, ? extends V> function)` : Replaces each entry's value with the result of the function.

---

### Common Methods
`size()` : Returns the number of entries.
`clear()` : Removes all entries.
`isEmpty()` : Returns true if no entries present.
`equals(Object o)` : Compares the specified object with this collection for equality.
`hashCode()` : Returns the hash code value for this collection.
`containsAll(Collection<?> c)` : Returns true if this collection contains all elements in the specified collection.
`stream()` : Returns a sequential stream with this collection as its source.
`parallelStream()` : Returns a parallel stream with this collection as its source.
`spliterator()` : Creates a Spliterator over the elements in this collection.
`removeIf(Predicate<? super E> filter)` : Removes all elements that satisfy the given predicate.
`forEach(Consumer<? super E> action)` : Performs the given action for each element.

---

### TreeSet / TreeMap / SortedSet / SortedMap
`first()` : Returns the first (lowest) element.
`last()` : Returns the last (highest) element.
`headSet(E toElement)` : Returns elements strictly less than toElement.
`tailSet(E fromElement)` : Returns elements greater than or equal to fromElement.
`subSet(E fromElement, E toElement)` : Returns elements from fromElement (inclusive) to toElement (exclusive).
`comparator()` : Returns the comparator used to order elements.
`firstKey()` : Returns the first (lowest) key (Map only).
`lastKey()` : Returns the last (highest) key (Map only).
`headMap(K toKey)` : Returns keys strictly less than toKey (Map only).
`tailMap(K fromKey)` : Returns keys greater than or equal to fromKey (Map only).
`subMap(K fromKey, K toKey)` : Returns keys from fromKey (inclusive) to toKey (exclusive) (Map only).

---

### NavigableSet / NavigableMap / TreeSet / TreeMap
`lower(E e)` : Returns the greatest element strictly less than the given element.
`floor(E e)` : Returns the greatest element less than or equal to the given element.
`ceiling(E e)` : Returns the smallest element greater than or equal to the given element.
`higher(E e)` : Returns the smallest element strictly greater than the given element.
`pollFirst()` : Retrieves and removes the first element.
`pollLast()` : Retrieves and removes the last element.
`descendingSet()` : Returns a reverse order view of the elements.
`descendingIterator()` : Returns an iterator over elements in descending order.
`lowerKey(K key)` : Returns the greatest key strictly less than the given key (Map only).
`floorKey(K key)` : Returns the greatest key less than or equal to the given key (Map only).
`ceilingKey(K key)` : Returns the smallest key greater than or equal to the given key (Map only).
`higherKey(K key)` : Returns the smallest key strictly greater than the given key (Map only).
`firstEntry()` : Returns the first key-value mapping (Map only).
`lastEntry()` : Returns the last key-value mapping (Map only).
`pollFirstEntry()` : Removes and returns the first key-value mapping (Map only).
`pollLastEntry()` : Removes and returns the last key-value mapping (Map only).
`descendingMap()` : Returns a reverse order view of the mappings (Map only).
`navigableKeySet()` : Returns a navigable set view of the keys (Map only).
`descendingKeySet()` : Returns a reverse order navigable set view of the keys (Map only).

---

## Iterators
### Iterator (`hasNext()`, `next()`, `remove()`)
### ListIterator (`hasPrevious()`, `previous()`)
### Fail-fast vs Fail-safe iterators
### forEach() and Iterable

---

## Custom Sorting
### Comparable (`compareTo`)
### Comparator (`compare`)
### Collections.sort() & List.sort()
### Sorting with Lambda & Streams

---

## Generics
### Generic classes & methods
### Bounded types (`extends`, `super`)
### Wildcards (`?`, `? extends`, `? super`)
### Type erasure

---

## I/O & Serialization
### File Handling (`FileReader`, `FileWriter`, `BufferedReader`, etc.)
### Byte Streams (`InputStream`, `OutputStream`)
### Character Streams (`Reader`, `Writer`)
### NIO & NIO.2 (`Path`, `Files`, `Channels`)
### Serialization & Deserialization (`ObjectOutputStream`, `ObjectInputStream`)

---

## Multithreading & Concurrency
### Creating threads (Thread class, Runnable interface)
### Thread lifecycle & states
### Synchronization (methods, blocks, static synchronization)
### Locks & ReentrantLock
### Inter-thread communication (`wait()`, `notify()`, `notifyAll()`)
### Executor framework (`ExecutorService`, `ThreadPoolExecutor`)
### Concurrency utilities (`CountDownLatch`, `CyclicBarrier`, `Semaphore`, `ConcurrentHashMap`)
### Volatile & Atomic variables

---

## Java 8+ (Modern Java)

### Lambda Expressions
- Syntax & functional interfaces
- Built-in functional interfaces (`Predicate`, `Consumer`, `Supplier`, `Function`)
- Method references & constructor references

### Streams API
- Stream creation (`stream()`, `of()`)
- Intermediate operations (`filter`, `map`, `sorted`, `distinct`)
- Terminal operations (`collect`, `forEach`, `reduce`)
- Parallel streams

---

## JDBC Basics
### JDBC drivers
### Steps to connect Java with DB
### Statement, PreparedStatement, CallableStatement
### ResultSet
### Batch processing
### Transactions

---

## JVM Internals
### JVM architecture (ClassLoader, Memory Areas, Execution Engine, JIT)
### Class loading process (loading, linking, initialization)
### Garbage Collection (generational GC, G1 GC, ZGC, Shenandoah)
### Strong, Weak, Soft, Phantom references

---

## Java LTS Versions & Features
### Java 8 → Lambdas, Streams, Date/Time API, Optional
### Java 11 → HTTP Client API, String methods, var in lambdas
### Java 17 → Sealed classes, pattern matching, switch expressions
### Java 21 → Virtual threads, string templates, record patterns

---

## Best Practices
### Immutability & defensive copying
### equals() & hashCode() contract
### Coding standards & design patterns (Singleton, Factory, Builder, etc.)
