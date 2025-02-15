# Strings
- character <span style="color:red">cannot</span> be changed once initialised.
  ```java
  s = "hello";
  s[1] = 'o';		//WRONG
  ```
- Functions:
  - `s.length()`
  - `s.charAt(int)`
  - `s.contains(String str)`
  - `s.indexOf(int ch)`
  - `s.indexOf(String str)`
  - `s.toLowerCase()`
  - `s.toUpperCase()`
  - `s.trim()`
  - `String[] split(String regex)`
  - `s1.equals(s2)` :		compares s1 and s2
  - `s1.compareTo(s2)`:	return int value
  - Substring
    - `s.substring(0, 3)`:	0 index included, 3 index excluded		( **O(n) complexity** )
    - `s.substring(1, 1)`:	blank string
    - `s.substring(1)`:		from 1 to last
    - `s.substring(2, 1)`:	ERROR
- integer , character and strings can be added together
    ```java
	s = "abc";
	s += 'd';
	```

- convert string to integer by `Integer.parseInt(str)`
- `String.join("delimiter", string array)`		## may not be correct
- `new String(charr)` : String form char array. here `charr` is of type char[]'

# StringBuilder
- `new StringBuilder()` : It creates an empty String Builder with the initial capacity of **16**.
- `StringBuilder(String str)` It creates a String Builder with the specified string.
- `StringBuilder(int length)` It creates an empty String Builder with the specified capacity as length.

#### stringBuilder functions
- `StringBuilder append(Type s)`
- `StringBuilder insert(int offset, Type s)`
- `StringBuilder replace(int startIndex, int endIndex, String str)`
- `StringBuilder delete(int startIndex, int endIndex)`
- `StringBuilder reverse()`
- `int capacity()`
- `void ensureCapacity(int minimumCapacity)`
- `char charAt(int index)`
- `int indexOf(String str)`
- `int lastIndexOf(String str)`
- `int length()`
- `void setLength(int newLength)`
- `void setCharAt(int index, char ch)`
- `String substring(int beginIndex)`
- `String substring(int beginIndex, int endIndex)` : start inclusive, end exclusive(end -1)

# Array
> `type[] name = new type[] {value1, value2, ..., valueN};`
- `new int[5]` : allocates memory of 5 elements and assign default value of int (0) to each
- `new int[0]` is not wrong and will compile successfully
- can also  be initialised as: `new int[]{1, var + 1, 5 var * var};`
- 2D (lengths)
  -	Each row of 2d (or multidimension) can be of different length
  ```java
  int[][] arr = {{1, 2, 3}, {3, 7}, {7, 2, 8, 1}};
  int[][] arr = new int[4][];
  arr[1] = new int[6];
  arr[2] = new int[3]
  // both statements are true

  row = arr.length
  column = arr[0].length
  ```
- java.utils.Arrays
  - `Arrays.toString(arr)`:	to print an array directly
  - `Arrays.sort(arr)`:		sort arr
  - `Arrays.sort(arr, Collections.reverseOrder())`:		sort arr in reverse
  - `Arrays.fill(arr, value)` fill the array with same value

# Arraylist
Syntax:
```java
ArrayList< Integer> al = new ArrayList< >();
// Using List Interface
List< Integer> al = new ArrayList< >();
```
- It doubles the total capacity of the list on insertion at full capacity
- The initial size of Arraylist is 0 as it is empty and the initial capacity of an Arraylist in Java is 10
#### arraylist function
- `a1.size()`: returns size or count of current element(not capacity)
- `a1.add(30)`
- `a1.add(i, 1000)`
- `a1.get(i)`
- `a1.set(i, 2000)`
- `a1.remove(index)`
- `a1.indexOf(value)`
- `a1.toArray()`
- to create list use
  ```java
  Arrays.asList(new Integer[]{1, 2, 3, 4, 5})
  // OR
  List.of(elements)
  ```

# LinkedList

> Class: `java.util.LinkedList`

Syntax:

```java
LinkedList<Integer> list = new LinkedList<>();
```

### Methods:

- `size()` - Returns the number of elements in the linked list.
- `display()` - Prints the elements of the linked list from front to end in a single line. All elements are separated by space.
- `addAt(index, value)` - Adds a new element at a given index.
- `addFirst(value)` - Adds a new element with the given value at the front of the linked list.
- `addLast(value)` - Adds a new element with the given value to the end of the linked list.
- `getAt(index)` - Returns the data of the element at the given index.
- `getFirst()` - Returns the data of the first element.
- `getLast()` - Returns the data of the last element.
- `removeAt(index)` - Removes an element at the given index.
- `removeFirst()` - Removes the first element from the linked list.
- `removeLast()` - Removes the last element of the linked list.

# Stack

- **LIFO (Last In, First Out)**
  > Class: `java.util.Stack`
- Syntax:
  ```java
  Stack<type> st = new Stack<type>();
  ```
- Common Methods
  ```java
  st.push(ele);    // Push an element onto the stack
  st.pop();        // Remove and return the top element
  st.peek();       // View the top element without removing it
  st.empty();      // Check if the stack is empty
  st.size();       // Get the number of elements in the stack
  ```
- `java.util.EmptyStackException`

# Queue

- **FIFO (First-In-First-Out)**

- **Queue** is an interface in Java.
- The common classes that can be used to instantiate queue objects are:
  - `LinkedList`
  - `ArrayDeque`

### Example Usage:

```java
Queue<Integer> q = new ArrayDeque<>();
```

Common Methods:

- `.add(ele)` - Adds an element to the queue.
- `.remove()` - Removes an element from the queue.
- `.peek()` - Retrieves, but does not remove, the front element of the queue.
- `.empty()` - Checks if the queue is empty.
- `.size()` - Returns the number of elements in the queue.

## PriorityQueue

- By default, **MINIMUM** is given higher priority.
- **Normal Priority Queue:** `PriorityQueue<Integer> pq = new PriorityQueue<>();`
- **Reverse Priority Queue:** `PriorityQueue<Integer> pq = new PriorityQueue<>(Collections.reverseOrder());`
- `add()` and `remove()` functions work with **O(log(n))** complexity.
- `poll()` retrieves and removes the head of the queue.

# Tree

> ## Traverse and Change tecnique

# Graph

```java
static class Edge {
  int src;
  int nbr;
  int wt;

  Edge(int src, int nbr, int wt) {
    this.src = src;
    this.nbr = nbr;
    this.wt = wt;
  }
}

public static void main(String[] args) throws Exception {
  int vertices = 7; //0 1 2 3 4 5 6
  ArrayList[] graph = new ArrayList[7];			// array of (arraylist of edge)

  graph[0].add(new Edge(0, 1, 10));
  graph[0].add(new Edge(0, 2, 20));
}
```

# HashMap
- **Insertion, Deletion, Searching: O(1) Time Complexity**
- **Directly Printable:** `System.out.println(hm);`
- Syntax:
  ```java
  HashMap<String, Integer> hm = new HashMap<>();
  ```
- Common Methods:
  ```java
  hm.put("India", 135);          // Add or update key-value pair
  hm.get("Utopia");              // Retrieve value, or null if not found
  hm.getOrDefault(key, defaultValue); // Get value or return default if absent
  hm.containsKey("India");       // Check if key exists (true/false)
  hm.remove("key");              // Remove key from HashMap
  ```
- Iteration:
  ```java
  Set<String> keys = hm.keySet();
  for (String key : keys) {
      // Access each key
  }
  ```

# Set

- **Unordered Collection with Unique Elements**
  > Interface: `java.util.Set`
  > Implementation: `java.util.HashSet`
- Syntax:
  ```java
  Set<type> set = new HashSet<>();
  ```
- Common Methods:
  ```java
  set.add(ele);          // Add an element to the set
  set.addAll(collection); // Add all elements from a collection
  set.remove(ele);       // Remove an element from the set
  set.contains(ele);     // Check if an element exists in the set
  set.size();           // Get the number of elements in the set
  set.toArray();        // Convert the set to an array
  ```
