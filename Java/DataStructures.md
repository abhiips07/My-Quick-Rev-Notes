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
