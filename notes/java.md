# Java

---

## History of Java
- Developed by **James Gosling** at Sun Microsystems (1995)  
- Initially called **Oak**, later renamed **Java**  
- Key principle: **WORA → Write Once, Run Anywhere**  
- Acquired by **Oracle** in 2010  

---

## JDK vs JRE vs JVM
- **JVM (Java Virtual Machine):** Executes bytecode, provides platform independence  
- **JRE (Java Runtime Environment):** JVM + libraries to run Java apps (no compilers)  
- **JDK (Java Development Kit):** JRE + development tools (compiler, debugger, etc.)  
- **Flow** : `.java` → (javac) → `.class` (bytecode) → JVM executes  

---

## Features of Java
- Simple and Secure  
- Object Oriented  
- Platform Independent (via JVM)  
- Robust (exception handling, GC)  
- Multithreaded
- High Performance (JIT compiler)  
- Distributed (network support)  

---

## Data Types
### Primitive Types
- byte (1B), short (2B), int (4B), long (8B)  
- float (4B), double (8B)  
- char (2B, Unicode)  
- boolean (1 bit, true/false)  

### Wrapper Classes
- byte → `Byte`  
- short → `Short`  
- int → `Integer`  
- long → `Long`  
- float → `Float`  
- double → `Double`  
- char → `Character`  
- boolean → `Boolean`  

---

## Variables
- **Local Variable:** Declared inside methods with block scope
- **Instance Variable:** Inside class but outside methods per object  
- **Static Variable:** Belongs to class shared across all objects  

---

## Operators
- **Arithmetic:** `+ - * / % ++ --`  
- **Relational:** `< > <= >= == !=`  
- **Logical:** `&& || !`  
- **Bitwise:** `& | ^ ~ << >> >>>`  
- **Ternary:** `condition ? expr1 : expr2`  

---

## Control Flow
- **if-else** (conditional branching)  
- **switch-case** (multi-condition)  
- **Loops:**  
  - `for(init; condition; update)`  
  - `while(condition)`  
  - `do { } while(condition);`  

---

## 8. Type Casting
- **Widening (Implicit):** smaller → larger  


## Order of Elements in Java Class :
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

## Java Collections :


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

## Key Points :

- Extends must come before implements.
- Only one class can be extended, but multiple interfaces can be implemented.
- Final classes cannot be extended.
- Final methods cannot be overridden.
- Interface methods are implicitly public abstract.
- Interface variables are implicitly public static final.
- lambdas and inner classes can only capture variables that are effectively final.

---

## Iterators :

```java
// List
for (int i = 0; i < fruits.size(); i++) System.out.println(fruits.get(i));
for (String fruit : fruits) System.out.println(fruit);
// Set
for (String city : cities) System.out.println(city);
// Queue
while (!queue.isEmpty()) System.out.println(queue.poll());
for (String item : queue) System.out.println(item);
// Map
for (Map.Entry<Integer, String> entry : map.entrySet()) System.out.println(entry.getKey() + " : " + entry.getValue());
```

## Exceptions :
```java
class CustomException extends Exception{
    public CustomException(String message) {
        super(message);
    }
}

class Main {
    public void getException() throws CustomException{
        throw new CustomException("Divide by zero");
    }
    
    public static void main(String[] args) {
        Main m = new Main();
        
        try {
            int x = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Exception Occured : " + e.getMessage());
        } 
        
        try {
            m.getException();
        } catch (CustomException e) {
            System.out.println("Custom Exception Occured : " + e.getMessage());
        } finally {
            System.out.println("Finally will execute anyway");
        }
    }
}

```

---

## String Methods :
`length()` : Returns the length of the string.  
`charAt(int index)` : Returns the character at the specified index.  
`substring(int beginIndex)` : Returns a substring from the specified start index.  
`substring(int beginIndex, int endIndex)` : Returns a substring from the start index to the end index.  
`contains(CharSequence sequence)` : Returns true if the string contains the specified sequence.  
`equals(Object anObject)` : Compares the string to the specified object for equality.  
`equalsIgnoreCase(String anotherString)` : Compares the string to the specified string, ignoring case.  
`compareTo(String anotherString)` : Compares the string to the specified string lexicographically.  
`compareToIgnoreCase(String str)` : Compares the string to the specified string, ignoring case, lexicographically.  
`startsWith(String prefix)` : Returns true if the string starts with the specified prefix.  
`endsWith(String suffix)` : Returns true if the string ends with the specified suffix.  
`indexOf(int ch)` : Returns the index of the first occurrence of the specified character.  
`indexOf(String str)` : Returns the index of the first occurrence of the specified substring.  
`lastIndexOf(int ch)` : Returns the index of the last occurrence of the specified character.  
`lastIndexOf(String str)` : Returns the index of the last occurrence of the specified substring.  
`replace(char oldChar, char newChar)` : Returns a new string with all occurrences of oldChar replaced by newChar.  
`replace(CharSequence target, CharSequence replacement)` : Replaces each substring matching target with the replacement.  
`replaceAll(String regex, String replacement)` : Replaces each substring matching the regex.  
`replaceFirst(String regex, String replacement)` : Replaces the first substring matching the regex.  
`toLowerCase()` : Converts all characters to lowercase.  
`toUpperCase()` : Converts all characters to uppercase.  
`trim()` : Removes leading and trailing whitespace.  
`split(String regex)` : Splits the string around matches of the regex.  
`split(String regex, int limit)` : Splits with a limit on number of splits.  
`concat(String str)` : Concatenates the specified string.  
`join(CharSequence delimiter, CharSequence... elements)` : Joins elements with the delimiter.  
`valueOf(int i)` : Returns the string representation of the integer.  
`toCharArray()` : Converts the string into a character array.  
`isEmpty()` : Returns true if the string is empty.  
`matches(String regex)` : Returns true if the string matches the regex.  
`regionMatches(int toffset, String other, int ooffset, int len)` : Compares regions of two strings.  
`regionMatches(boolean ignoreCase, int toffset, String other, int ooffset, int len)` : Same as above, with case control.  
`format(String format, Object... args)` : Returns a formatted string.  
`getBytes()` : Encodes the string into bytes using default charset.  
`getBytes(Charset charset)` : Encodes into bytes using specified charset.  
`toString()` : Returns the string itself.  
`contentEquals(StringBuffer sb)` : Compares the string to a StringBuffer.  
`StringBuilder sb = new StringBuilder("Hello")` : Creates a mutable string.  
`String.format("Value: %d", 42)` : Formats a string.  
`StringBuffer sb = new StringBuffer("Hello")` : Creates a synchronized mutable string.  
`str1.equals(str2), str1.equalsIgnoreCase(str2)` : String comparisons.  

---

## StringBuilder Methods :
`StringBuilder()` : Creates empty StringBuilder (capacity=16).  
`StringBuilder(int capacity)` : Creates empty StringBuilder with given capacity.  
`StringBuilder(String str)` : Creates StringBuilder initialized with str.  
`append(x)` : Appends x (any type).  
`insert(int offset, x)` : Inserts x at the given offset.  
`delete(int start, int end)` : Removes chars from start to end-1.  
`deleteCharAt(int index)` : Removes char at the given index.  
`replace(int start, int end, String str)` : Replaces substring with str.  
`reverse()` : Reverses the character sequence.  
`setCharAt(int index, char ch)` : Sets a char at given index.  
`substring(int start)` : Returns substring from start to end.  
`substring(int start, int end)` : Returns substring from start to end-1.  
`length()` : Returns current length.  
`capacity()` : Returns current capacity.  
`ensureCapacity(int min)` : Ensures minimum capacity.  
`trimToSize()` : Reduces capacity to match length.  
`toString()` : Converts to String.  
`chars()` : Returns IntStream of characters.  
`sb.setLength(0)` : Resets to "" but keeps capacity.  
`sb = new StringBuilder()` : Creates fresh empty instance.  

---

### Access Modifiers (Control Visibility)
`public` : Accessible from anywhere.  
`protected` : Accessible within same package + subclasses.  
`private` : Accessible only within the class.  
`(default / package-private)` : Accessible only within the same package.

---
### Non Access Modifiers (Modify Behavior)
`static` : Belongs to the class, not instance.  
`final` : Used for constants, prevents inheritance or overriding.  
`abstract` : Used for abstract classes/methods (no body).  
`synchronized` : Ensures only one thread accesses at a time.  
`volatile` : Ensures visibility of shared variables across threads.  
`transient` : Excludes a variable from serialization.  
`strictfp` : Enforces IEEE precise floating-point calculations.  
`native` : Used to call platform-specific (C/C++) code.  

---

## Multithreading :

### Extend Thread Class
```java
class Main{
    public static void main(String[] args) {
        MyThread t = new MyThread();
        t.start();
    }
}

public class MyThread extends Thread {
    public void run(){
        System.out.println("thread");
    }
}
```

### Implements Runnable Interface
```java
class Main{
    public static void main(String[] args) {
        Thread t = new Thread(new MyRunnable());
        t.start();
    }
}

public class MyRunnable implements Runnable {
    public void run(){
        System.out.println("thread");
    }
}
```

### Synchronized Method
```java
public synchronized void increment() {
    count++;
}
```
### Synchronized Block
```java
private final Object lock = new Object();

public void increment() {
    synchronized (lock) {
        count++;
    }
}
```

### Wait Notify 
```java
class SharedBuffer {
    private Queue<Integer> queue = new LinkedList<>();
    private final int CAPACITY = 5;

    public synchronized void produce(int item) throws InterruptedException {
        while (queue.size() == CAPACITY) {
            wait();
        }
        queue.add(item);
        notify();
    }

    public synchronized int consume() throws InterruptedException {
        while (queue.isEmpty()) {
            wait();
        }
        int item = queue.poll();
        notify();
        return item;
    }
}
```

---

## Custom Sorting :

```java
Arrays.sort(arr);

Arrays.sort(arr, (a, b) -> b - a); // Must be Integer[], not int[]

List<Integer> numbers = new ArrayList<>();
numbers.sort((a, b) -> b - a);

class Person {
    String name;
    int age;
}
List<Person> people = new ArrayList<>();
people.sort((p1, p2) -> p1.age - p2.age);

Set<Integer> set = new TreeSet<>((a, b) -> b - a);

PriorityQueue<Integer> maxHeap = new PriorityQueue<>((a, b) -> b - a);
PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> a[1] - b[1]);

List<int[]> list = new ArrayList<>();
list.sort((a, b) -> {
    if (a[0] != b[0]) {
        return a[0] - b[0];
    } else {
        return b[1] - a[1];
    }
});
```

---
## Enum :

### Enum Syntax 

```java
public enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}

Day today = Day.MONDAY;
System.out.println(today); // Output: MONDAY

switch (today) {
    case MONDAY -> System.out.println("Week starts!");
    case FRIDAY -> System.out.println("Weekend is near!");
    default -> System.out.println("Midweek day.");
}
```

### Enum with Custom Values

```java
public enum Planet {
    MERCURY(3.303e+23, 2.4397e6),
    VENUS(4.869e+24, 6.0518e6),
    EARTH(5.976e+24, 6.37814e6);

    private final double mass;
    private final double radius;

    // Constructor (private by default)
    Planet(double mass, double radius) {
        this.mass = mass;
        this.radius = radius;
    }

    // Method to calculate surface gravity
    public double surfaceGravity() {
        return 6.67300E-11 * mass / (radius * radius);
    }
}

Planet earth = Planet.EARTH;
System.out.println(earth.surfaceGravity()); // Output: 9.8 (approx)
```

### Enum with Abstract Methods

```java
public enum Operation {
    ADD {
        public int apply(int a, int b) { return a + b; }
    },
    MULTIPLY {
        public int apply(int a, int b) { return a * b; }
    };

    public abstract int apply(int a, int b); // Abstract method
}

System.out.println(Operation.ADD.apply(5, 3)); // Output: 8
```

### Enum Implementing Interfaces

```java
public enum Task implements Runnable {
    TASK1 {
        @Override
        public void run() {
            System.out.println("Running Task 1");
        }
    },
    TASK2 {
        @Override
        public void run() {
            System.out.println("Running Task 2");
        }
    };
}
```

### Looping Through Enum Values

```java
for (Day day : Day.values()) {
    System.out.println(day);
}
```

| Method            | Description                              | Example                                  |
|-------------------|------------------------------------------|------------------------------------------|
| `values()`        | Returns all enum constants               | `Day[] days = Day.values();`             |
| `valueOf(String)` | Converts a string to enum                | `Day d = Day.valueOf("MONDAY");`         |
| `name()`          | Returns the enum constant's name         | `"MONDAY".equals(Day.MONDAY.name())`     |
| `ordinal()`       | Returns the position (index) of the enum | `Day.MONDAY.ordinal()` → `0`             |

---

## Lambda :

```Lambda Expression``` :
- A lambda expression is a short block of code that takes parameters, executes a block of code, returns a result.

```Use lambdas when``` :
- Working with functional interfaces (Runnable, Comparator, etc.)
- Using Java Streams API
- Writing event listeners (e.g., button clicks)
- Implementing simple single-method interfaces

```Avoid when``` :
- The logic is too complex (use a proper method instead)
- You need multiple methods (use a class)


### Before Lambdas: The Old Way (Anonymous Classes)

```java
// Old way - Anonymous class
Runnable runnable = new Runnable() {
    @Override
    public void run() {
        System.out.println("Running!");
    }
};
runnable.run();

//With Lambda (New Way)
Runnable runnable = () -> System.out.println("Running!");
runnable.run();
```

### Lambda with Parameters

```java
// Functional Interface
interface MathOperation {
    int operate(int a, int b);
}

public class Main {
    public static void main(String[] args) {
        MathOperation add = (a, b) -> a + b;
        System.out.println(add.operate(5, 3)); // Output: 8
    }
}
```

### Built-in Functional Interfaces

| Interface       | Method       | Example Lambda Usage             |
|-----------------|--------------|-----------------------------------|
| `Consumer<T>`   | `accept(T)`  | `(s) -> System.out.println(s)`    |
| `Supplier<T>`   | `get()`      | `() -> "Hello"`                   |
| `Function<T,R>` | `apply(T)`   | `(s) -> s.length()`              |
| `Predicate<T>`  | `test(T)`    | `(s) -> s.startsWith("A")`        |

### Method References (Shortcut for Lambdas)

| Type               | Syntax                 | Equivalent Lambda               |
|--------------------|------------------------|----------------------------------|
| Static Method      | `Math::max`            | `(a, b) -> Math.max(a, b)`       |
| Instance Method    | `System.out::println`  | `(s) -> System.out.println(s)`   |
| Constructor        | `ArrayList::new`       | `() -> new ArrayList<>()`        |

```java
names.forEach(name -> System.out.println(name)); // Lambda
names.forEach(System.out::println); // Method Reference
```

---
## Stream
- A Stream is a sequence of elements supporting Sequential or Parallel operations.
- Lazy evaluation (operations execute only when needed) and only when termial operation called.
- It is not possible to call two terminal operations on a single Java stream.
- No storage (does not modify the original collection).

```Key Characteristics``` :
- Not a data structure (unlike List, Set).
- Supports functional style operations (filter, map, reduce).
- Can be processed only once (like an iterator).


### Creating Streams

```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
Stream<String> stream = names.stream(); // sequential stream
Stream<String> parallelStream = names.parallelStream(); // parallel stream (uses multiple threads)

String[] languages = {"Java", "Python", "C++"};
Stream<String> stream = Arrays.stream(languages);

Stream<Integer> numbers = Stream.of(1, 2, 3, 4, 5);

// Generate random numbers infinitely
Stream<Double> randomNumbers = Stream.generate(Math::random);

// Stream of odd numbers: 1, 3, 5, ...
Stream<Integer> oddNumbers = Stream.iterate(1, n -> n + 2);
```

### Intermediate Operations

```java
filter(n -> n > 10)              // keeps elements that satisfy predicate
map(String::toUpperCase)         // transforms each element
mapToInt(String::length)         // specialized mapping to primitive streams
flatMap(List::stream)            // flattens nested streams
sorted()                         // natural order
sorted(Comparator.reverseOrder())// custom comparator
distinct()                       // removes duplicates
limit(5)                         // keeps first 5 elements
skip(3)                          // skips first 3 elements
peek(System.out::println)        // for debugging (intermediate side-effect)
```

### Terminal Operations

```java
forEach(System.out::println)     // performs action on each element
forEachOrdered(System.out::println) // preserves encounter order

collect(Collectors.toList())     // collect to List
collect(Collectors.toSet())      // collect to Set
collect(Collectors.joining(", "))// join strings

count()                          // returns long count
reduce((a, b) -> a + b)          // combines elements
reduce(0, Integer::sum)          // with identity

anyMatch(s -> s.startsWith("A")) // returns true if any matches
allMatch(n -> n > 0)             // returns true if all match
noneMatch(s -> s.isEmpty())      // returns true if none match

findFirst()                      // Optional of first element
findAny()                        // Optional of any element (parallel-friendly)
max(Comparator.naturalOrder())   // max element
min(Comparator.naturalOrder())   // min element
toArray()                        // collect into array
```

### Common Mistakes

```java 
Stream<Integer> stream = Stream.of(1, 2, 3);
stream.forEach(System.out::println);
stream.forEach(System.out::println); // Error: stream already closed

Optional<Integer> sum = Stream.of(1, 2).reduce((a, b) -> a + b);
System.out.println(sum.get()); // OK if stream is not empty
```

---

## Generics

`T` → **Type** (e.g., List<T>)
`E` → **Element** (e.g., ArrayList<E>)
`K` → **Key** (e.g., Map<K, V>)
`V` → **Value** (e.g., Map<K, V>)
`?` → **Wildcard** (unknown type)


### Generic Classes

```java
class Box<T> {  // 'T' is a type placeholder
    private T item;

    public void setItem(T item) {
        this.item = item;
    }

    public T getItem() {
        return item;
    }
}

Box<String> stringBox = new Box<>();
stringBox.setItem("Hello");
String value = stringBox.getItem(); // No casting needed!

Box<Integer> intBox = new Box<>();
intBox.setItem(100);
int num = intBox.getItem(); // Works with Integer too!

```

### Generic Methods

```java
public <T> void printArray(T[] array) {  // <T> before return type
    for (T item : array) {
        System.out.print(item + " ");
    }
}

String[] names = {"Alice", "Bob", "Charlie"};
printArray(names); // Works with String[]

Integer[] numbers = {1, 2, 3};
printArray(numbers); // Also works with Integer[]
```

### Bounded Generics (Restricting Types)

```java
class MathBox<T extends Number> {  // T must be Number or subclass (Integer, Double, etc.)
    private T number;

    public MathBox(T number) {
        this.number = number;
    }

    public double square() {
        return number.doubleValue() * number.doubleValue();
    }
}

MathBox<Integer> intBox = new MathBox<>(5);
System.out.println(intBox.square()); // 25.0

MathBox<Double> doubleBox = new MathBox<>(3.5);
System.out.println(doubleBox.square()); // 12.25

// MathBox<String> stringBox = new MathBox<>("Test"); // ERROR! String is not a Number
```

### Wildcards (?) for Flexibility

```java
public static void printNumbers(List<? extends Number> list) {
    for (Number num : list) {
        System.out.print(num + " ");
    }
}

List<Integer> ints = List.of(1, 2, 3);
List<Double> doubles = List.of(1.1, 2.2, 3.3);

printNumbers(ints);    // Works
printNumbers(doubles); // Also works
```

---

## Java 8 (2014) :

- **Lambda Expressions** → Write functions inline (simplifies anonymous classes).
- **Streams API** → Process collections in a functional style (map, filter, reduce).
- **Functional Interfaces** → Interfaces with a single abstract method (used with lambdas).
- **Default Methods** → Allow methods in interfaces with a default implementation.
- **Static Methods in Interfaces** → Define utility methods directly inside interfaces.
- **Method References** → Short-hand notation to call existing methods with `::`.
- **Optional Class** → Handle null values gracefully without NullPointerException.
- **New Date and Time API (java.time)** → Modern, immutable date/time handling.
- **Nashorn JavaScript Engine** → Execute JavaScript code within Java applications.
- **CompletableFuture** → Asynchronous programming support with futures.
- **Parallel Streams** → Run stream operations in parallel for performance.
- **Collectors Utility** → Collect results of stream processing (toList, toSet, groupingBy).
- **Base64 Encoding/Decoding** → Built-in support for encoding/decoding Base64 data.
- **Annotations on Java Types** → Apply annotations on types (e.g., generics, parameters).
- **Repeating Annotations** → Use the same annotation multiple times on a declaration.

---

## Java 11 (2018) :

- **Local-Variable Syntax for Lambda Parameters (`var`)** → Improves readability by using `var` in lambda expressions.  
- **New String Methods** → `isBlank()`, `lines()`, `strip()`, `repeat()` – commonly asked in interviews.  
- **Files API Enhancements** → `readString()` and `writeString()` simplify file handling.  
- **HTTP Client (Standardized)** → Built-in `HttpClient` for HTTP/2 and async requests (often asked).  
- **Flight Recorder** → Low-overhead monitoring/profiling tool inside the JVM.  
- **Z Garbage Collector (ZGC)** → Experimental low-latency GC (frequently discussed in interviews).  
- **Epsilon GC (No-Op GC)** → Allocates memory but does not reclaim (useful in testing scenarios).  
- **Nest-Based Access Control** → Inner classes can access each other’s private members without reflection.  
- **Removed Modules (Java EE & CORBA)** → Interviewers ask about removals/deprecations in Java 11.  

---

## Java 17 (2021) :

- **Sealed Classes** → Restrict which classes can extend or implement a class/interface.  
- **Pattern Matching for switch (Preview)** → Simplifies `switch` with type patterns and better readability.  
- **Text Blocks (Standard)** → Multi-line string literals using `"""`, easier JSON/SQL/XML handling.  
- **Records (Standard)** → Concise data-carrier classes with automatic getters, equals, hashCode, toString.  
- **New macOS Rendering Pipeline** → Uses Apple Metal API for better graphics performance.  
- **Foreign Function & Memory API (Incubator)** → Call native code & manage off-heap memory safely.  
- **Deprecations/Removals** → Removed RMI Activation, Applet API deprecated.  
- **Security Updates** → Strong encapsulation of JDK internals (access only via modules).  
- **Strongly Encapsulated JDK Internals** → Prevents direct access to internal APIs (like `sun.misc.Unsafe`).  

---

## Java 21 (2023) :

- **Virtual Threads (Project Loom)** → Lightweight threads managed by JVM, simplify concurrency and reduce resource usage.  
- **Pattern Matching for switch (Standard)** → Type-safe, concise `switch` with patterns and guards.  
- **Record Patterns (Standard)** → Deconstruct record values directly in pattern matching.  
- **Sequenced Collections** → New interfaces (`SequencedCollection`, `SequencedSet`, `SequencedMap`) to handle ordered collections easily.  
- **String Templates (Preview)** → Safer and more readable string interpolation (similar to templating in other languages).  
- **Scoped Values (Preview)** → Safer alternative to ThreadLocal for sharing data across threads.  
- **Foreign Function & Memory API (Standard)** → Replace JNI, interact with native libraries and memory safely.  
- **Key Security Enhancements** → TLS, cryptography updates for stronger security.  
- **Deprecations/Removals** → Final removal of `SecurityManager` and legacy APIs.  

---

## Imports 

- **DSA → `java.util.*`**  
  Collections framework (List, Set, Map, Queue, Stack, HashMap, ArrayList, etc.)

- **Functional Programming → `java.util.stream.*`  `java.util.function.*`**  
  Streams for functional style processing, functional interfaces (Predicate, Function, Consumer, Supplier).

- **I/O → `java.io.*`, `java.nio.*`**  
  File handling, input/output streams, readers/writers, and NIO for faster/buffered I/O.

- **Database → `java.sql.*`**  
  JDBC API for database connection, queries, ResultSet, PreparedStatement.

- **Date/Time → `java.time.*`**  
  Modern Date and Time API (LocalDate, LocalTime, LocalDateTime, ZonedDateTime, Duration, Period).

- **Concurrency → `java.util.concurrent.*`**  
  Multithreading utilities (ExecutorService, Future, CountDownLatch, ConcurrentHashMap, ThreadPoolExecutor).

- **Regex → `java.util.regex.*`**  
  Pattern matching using `Pattern` and `Matcher`.

---

## Regex 

- **`.`**  Matches any single character : `"a.c"` → matches `abc`, `axc`, `a9c`

- **`^`** Matches start of string : `"^abc"` → matches `abc123` (but not `1abc`)

- **`$`** Matches end of string : `"xyz$"` → matches `123xyz` (but not `xyz123`)

- **`*`** 0 or more occurrences : `"ab*"` → matches `a`, `ab`, `abb`, `abbbbb`

- **`+`** 1 or more occurrences : `"ab+"` → matches `ab`, `abb`, `abbbbb` (but not `a`)

- **`?`** 0 or 1 occurrence (optional) : `"colou?r"` → matches `color`, `colour`

- **`{n}`** Exactly `n` times : `"a{3}"` → matches `aaa`

- **`{n,}`** At least `n` times : `"a{2,}"` → matches `aa`, `aaa`, `aaaa...`

- **`{n,m}`** Between `n` and `m` times : `"a{2,4}"` → matches `aa`, `aaa`, `aaaa`

- **`[]`** Character set : `"[abc]"` → matches `a`, `b`, or `c`

- **`[^ ]`** Negated set : `"[^abc]"` → matches any char except `a`, `b`, `c`

- **`|`** OR : `"cat|dog"` → matches `cat` or `dog`

- **`(...)`** Group : `"(ab)+"` → matches `ab`, `abab`, `ababab`

- **`\d`** Digit `[0-9]` : `"\d+"` → matches `123`, `007`

- **`\D`** Non-digit : `"\D+"` → matches `abc`, `!@#`

- **`\w`** Word char `[a-zA-Z0-9_]` : `"\w+"` → matches `hello123`

- **`\W`** Non-word char : `"\W+"` → matches `!@#`, `--`

- **`\s`** Whitespace (space, tab, newline) : `"\s+"` → matches `"   "` (spaces), `\n`

- **`\S`** Non whitespace : `"\S+"` → matches `hello`, `123`

- **`(?i)`** Case insensitive flag : `"(?i)abc"` → matches `abc`, `ABC`, `AbC`

## Date and Time API

``` java
LocalDate.now(); // 2025-08-27 → Current system date
LocalTime.now(); // 21:15:30.123 → Current system time
LocalDateTime.now(); // 2025-08-27T21:15:30.123 → Current date and time
LocalDate.of(2023, 5, 10); // 2023-05-10 → Creates a specific date
LocalTime.of(10, 30); // 10:30 → Creates a specific time
LocalDate.parse("2023-08-15"); // 2023-08-15 → Parses string to date
LocalDate.now().format(DateTimeFormatter.ofPattern("dd/MM/yyyy")); // 27/08/2025 → Formats date
LocalDate.now().plusDays(5); // 2025-09-01 → Adds 5 days
LocalDate.now().minusMonths(2); // 2025-06-27 → Subtracts 2 months
LocalDate.of(2023,1,1).isBefore(LocalDate.of(2024,1,1)); // true → Checks if before
LocalDate.now().getDayOfWeek(); // WEDNESDAY → Day of the week
LocalDate.now().getMonth(); // AUGUST → Current month
Instant.now(); // 2025-08-27T15:45:30Z → Machine timestamp (UTC)
ZonedDateTime.now(ZoneId.of("Asia/Kolkata")); // 2025-08-27T21:15+05:30 → DateTime with zone
```






