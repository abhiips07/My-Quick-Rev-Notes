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
