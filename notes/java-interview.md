## Java

```
Static Method: Belongs to the class (no instance needed).
Instance Method: Requires an object.

Feature	  	Stack Memory	  			Heap Memory
Stores	  	Primitives, method calls, references	Objects, arrays, instance variables
Lifetime  	Short-lived (method scope)		Long-lived (until garbage collected)
Thread    	Safety	Each thread has its own stack	Shared among all threads
Speed	  	Faster access				Slower access
Memory Mgmt.	Automatic (LIFO)			Managed by Garbage Collector (GC)
Size		Fixed (can overflow)			Dynamic (can run out of memory)

Wrapper Classes (Integer, Double): Used in collections (e.g., List<Integer>). Provide utility methods (Integer.parseInt()).
Primitives (int, double): Better performance.

Array for performance-critical fixed-size data.
List for flexibility.

Set (HashSet, TreeSet) : No duplicates. Unordered (except TreeSet).
List (ArrayList, LinkedList) Allows duplicates. Ordered (index-based).

1. Comparable (java.lang.Comparable)
Purpose: Defines the natural ordering of a class (default sorting logic).
Method to Implement: compareTo(T obj)

class Student implements Comparable<Student> {
    String name;
    int age;

    @Override
    public int compareTo(Student other) {
        return this.age - other.age; // Sort by age (ascending)
    }
}

// Usage:
List<Student> students = new ArrayList<>();
students.add(new Student("Alice", 25));
students.add(new Student("Bob", 20));
Collections.sort(students); // Sorts by age (natural order)


2. Comparator (java.util.Comparator)
Purpose: Provides custom sorting logic without modifying the original class.

Method to Implement: compare(T obj1, T obj2)
// Comparator for sorting by name
class NameComparator implements Comparator<Student> {
    @Override
    public int compare(Student s1, Student s2) {
        return s1.name.compareTo(s2.name); // Sort by name (String's natural order)
    }
}

// Usage:
List<Student> students = new ArrayList<>();
students.add(new Student("Alice", 25));
students.add(new Student("Bob", 20));
Collections.sort(students, new NameComparator()); // Sorts by name

Using Lambda (Java 8+)
// Sort by age (descending)
Collections.sort(students, (s1, s2) -> s2.age - s1.age);

// Alternative (using Comparator.comparing)
students.sort(Comparator.comparing(Student::getName)); // Sort by name
students.sort(Comparator.comparingInt(Student::getAge).reversed()); // Sort by age (descending)


Interface						Abstract Class
All methods are abstract (Java 8+ allows default).	Can have abstract + concrete methods.
Supports multiple inheritance.				Single inheritance.
No constructors.					Can have constructors.

Final:
Variables: Cannot be reassigned (final int x = 5;).
Methods: Cannot be overridden.
Classes: Cannot be inherited.

== vs equals()
==: Compares memory addresses (references).
equals(): Compares content (overridden in String, Integer).

Integer a = 5;    // Autoboxing  
int b = a;        // Unboxing  

Checked Exceptions		Unchecked Exceptions
Compile-time (must handle).	Runtime (optional handling).
E.g., IOException.		E.g., NullPointerException.

StringBuilder for single-threaded apps.
StringBuffer for multithreading.

Synchronized Method: Locks the entire object : public synchronized void myMethod() { ... } 
Synchronized Block: Locks a specific section : synchronized(this) { ... }

Overloading					Overriding
Same method name, different parameters.		Same method signature in subclass.
Compile-time polymorphism.			Runtime polymorphism.

Serialization: Object → Byte stream (for storage/transfer) : ObjectOutputStream.writeObject(obj); // Serialize  
Deserialization: Byte stream → Object : ObjectInputStream.readObject();     // Deserialize  

ArrayList for frequent reads.
LinkedList for frequent modifications.

HashMap				HashTable
Not thread-safe.		Thread-safe (synchronized).
Allows null keys/values.	No null keys/values.

Best Practice: Prefer HashMap (use ConcurrentHashMap for threads).

Enum: Type-safe, can have methods.

Garbage Collection: Automatic (Java, Python). GC prevents memory leaks but adds overhead.
Manual Management: Explicit malloc/free (C/C++).



It works : return n % 2 == 0 ? n : n * 2;

Type casting : (int)


Functional      		OOP Programming
Pure functions, immutability.	Objects, state, inheritance.
E.g., Java Streams.		E.g., Java classes.
Key Difference: FP avoids side effects; OOP models real-world entities.


Shallow Copy: Copies references (shared nested objects).    ArrayList<String> shallow = original; 
Deep Copy: Copies entire object hierarchy.		    ArrayList<String> deep = new ArrayList<>(original);  


Java is always pass-by-value.		
For primitives: A copy of the value is passed.
For objects: A copy of the reference (memory address) is passed.

Thread vs Runnable
Thread: A class. Extending it limits flexibility (Java doesn’t support multiple inheritance).
Runnable: An interface. Preferred because:
Allows extending another class.
Better for thread pooling.


Switch : alternative to long if-else-if
Without break, execution will "fall through" to the next case.
default case: Optional but recommended for handling unexpected values.
duplicate case not allowed, comiplation error
Arrows syntax can also be used
Arrow and : syntax both cant be used
switch can return values
Using null in a switch statement will throw a NullPointerException.


String str = Integer.toString(number);
String str = String.valueOf(number);
String str = "" + number;

int number = Integer.parseInt(str);
Integer number = Integer.valueOf(str); 

class path : where the jar class files are located

Singleton Design Pattern : private constructor, synchronized method :  public static synchronized ThreadSafeSingleton getInstance()

Integer can store null, where int cant store null

int to String ->  String.valueOf(int) or Integer.toString(int)
String to int -> Integer.valueOf(String) or Integer.parseInt(String)

HashMap (Collision -> Linkedlist before java8, Red Black Tree after java 8)
TreeMap -> Red Black Tree

Intermediate Operations (Lazy Evaluation) -> These operations return a new stream and only execute when a terminal operation is called.

it is not possible to use two terminal operations one after another on the same Java Stream.

.flatMap(List::stream) 

List<Integer> squaredNumbers = numbers.stream()
    .peek(n -> System.out.println("Before map: " + n))
    .map(n -> n * n)
    .peek(n -> System.out.println("After map: " + n))
    .collect(Collectors.toList());
    
    
List<String> names = List.of("Alice", "Bob", "Charlie");

Set<String> nameSet = names.stream()
    .collect(Collectors.toSet());  // Convert to Set



import java.util.Scanner;
Scanner scanner = new Scanner(System.in);
String name = scanner.nextLine();

next() - Reads a single word (until whitespace)
nextLine() - Reads an entire line (until newline)
nextInt(), nextDouble(), nextBoolean()

// Always close the scanner when done
   scanner.close();

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class FileWriteBuffered {
    public static void main(String[] args) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"))) {
            writer.write("Using BufferedWriter");
            writer.newLine();
            writer.write("More efficient for multiple writes");
        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class FileReadBuffered {
    public static void main(String[] args) {
        try (BufferedReader reader = new BufferedReader(new FileReader("input.txt"))) {
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}


ExecutorService: java.util.concurrent // from Java 5 onward
ExecutorService executor = Executors.newFixedThreadPool(4); // 4 threads
ExecutorService executor = Executors.newCachedThreadPool();
ExecutorService executor = Executors.newSingleThreadExecutor();
ScheduledExecutorService scheduler = Executors.newScheduledThreadPool(2);

// execute() :
executor.execute(() -> {
    System.out.println("Task running in thread: " + Thread.currentThread().getName());
});

executor.shutdown(); // Shutdown when done

// submit() :
Future<Integer> future = executor.submit(() -> {
    Thread.sleep(1000);
    return 42; // Returns a result
});

try {
    System.out.println("Result: " + future.get()); // Blocks until result is available
} catch (Exception e) {
    e.printStackTrace();
}

executor.shutdown();


Atomic Variables :
AtomicInteger (for int)
AtomicLong (for long)
AtomicBoolean (for boolean)
AtomicReference<T> (for any object)
AtomicIntegerArray, AtomicLongArray (for arrays)

AtomicInteger counter = new AtomicInteger(0);
counter.set(10); // Sets value to 10
int value = counter.get(); // Reads value (10)
boolean success = counter.compareAndSet(10, 20); // If current value is 10, set to 20
System.out.println(counter.incrementAndGet()); // 1 (++i)
System.out.println(counter.getAndIncrement()); // 1 (i++)
AtomicInteger counter = new AtomicInteger(5);
counter.updateAndGet(x -> x * 2); // 10
counter.accumulateAndGet(3, (x, y) -> x + y); // 13


Multithreading :
Thread.currentThread().getName() // Thread-0

New: When created but not started
Runnable: When start() is called
Running: When executing
Blocked/Waiting: When waiting for resources
Terminated: When execution completes

 t1.join(); // Wait for t1 to finish


Most collections throw ConcurrentModificationException if modified during iteration.
Use Iterator.remove() for safe removal in List, Set, Map, Queue, Deque.
Java 8+? Prefer removeIf() where possible.
Concurrent collections (ConcurrentHashMap, CopyOnWriteArrayList) allow direct removal but



The default initial capacity of an ArrayList in Java is 10.
The growth factor is (oldCapacity * 3)/2 + 1
If created with new ArrayList<>(0), Java delays allocation until the first element is added.
If you know the approximate size, initialize with a higher capacity to avoid reallocations

The load factor is a critical performance parameter in hash-based collections (HashMap, HashSet, LinkedHashMap, HashTable)
Default HashMap (Capacity=16, Load Factor=0.75)
Map<String, Integer> map = new HashMap<>(16, 0.5f); // Resizes at 8 elements


Collections.synchronizedMap() (Legacy Thread-Safe Map) :
Wraps any Map (e.g., HashMap, LinkedHashMap) and makes it thread-safe.
Uses synchronized blocks on the entire map (monitor lock)

Map<String, Integer> map = new HashMap<>();
Map<String, Integer> syncMap = Collections.synchronizedMap(map); // Now thread-safe

Poor performance under high contention (only one thread can access the map at a time).

ConcurrentHashMap (Modern Thread-Safe Map) :
Uses fine-grained locking (lock striping) and CAS (Compare-And-Swap) operations.
Allows multiple threads to read and write concurrently without full synchronization.

Map<String, Integer> concurrentMap = new ConcurrentHashMap<>();

Higher throughput in multi-threaded environments.
Atomic operations (e.g., putIfAbsent(), compute()).
Scalable (better than synchronizedMap).
Does not allow null keys/values (throws NullPointerException)


ThreadLocal:
Each thread has its own instance of the variable.
No synchronization needed (since threads don’t share the variable).
Common use cases:
Storing user sessions (e.g., in web apps).
Storing transaction contexts (e.g., in JDBC).
Per-thread caching (e.g., SimpleDateFormat).

ThreadLocal<Integer> threadLocalCounter = new ThreadLocal<>();
// Each thread sets its own value
threadLocalCounter.set(0);
// Each thread increments its own copy
threadLocalCounter.set(threadLocalCounter.get() + 1);

Always threadLocal.remove() after use to prevent memory leaks



HashMap -> one null key and multiple null values : 0 index is reserved for null key


Thread-Safe Classes in Java:
Hashtable
Vector
Stack
Collections.synchronizedList(List<T> list)
Collections.synchronizedMap(Map<K,V> map)
Collections.synchronizedSet(Set<T> set)
ConcurrentHashMap	High-concurrency Map	Fine-grained locking, atomic operations (putIfAbsent, compute)
CopyOnWriteArrayList	Thread-safe List	Snapshot iteration (no ConcurrentModificationException)
CopyOnWriteArraySet	Thread-safe Set	Backed by CopyOnWriteArrayList
BlockingQueue	        Thread-safe FIFO queue	Supports producer-consumer patterns
ConcurrentLinkedQueue	Lock-free thread-safe queue	Non-blocking, high performance
ConcurrentSkipListMap	Thread-safe sorted Map	Scalable alternative to TreeMap
ConcurrentSkipListSet	Thread-safe sorted Set	Backed by ConcurrentSkipListMap





```
