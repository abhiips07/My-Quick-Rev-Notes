> Link to [JavaCompilationProcess.md](/Java/JavaCompilationProcess.md)

> Link to [DataStructures.md](/Java/DataStructures.md)

> Link to [Algorithms.md](/Java/Algorithms.md)

---
---

# Remember these
- Reference variable default to `null` value.
Boolean values are in lowercase `true` and `false`. `false` is default value.
- Only primitive data-types: `Byte`, `Short`, `Int`, `Long`, `Double`, `Float`, `Char` and `Boolean` are stored directly in ***STACK*** memory.
- `+` is used for string concatenation
- `==` compares stack memory content only. `.equals()` must be used for other cases (if available).

#### `final`
- `final` is used, **'const'** is not valid in java
- `final <datatype> CAPTALISE_NAME`.
- final method cannot be overridden.
- final class cannot be extended

#### Assignment rules
- `x = y = 0` OR `head = tail = node` this is **correct** in java
- Assignment returns whatever value is assigned to it
  ```java
  int i = 15;
  System.out.println(i = 10);	# will print 10
  ```

#### Input stream syntax
- `BufferedReader br = new BufferedReader(new InputStreamReader(System.in));`
- `sc.next()` : Reads to next space only no new line
- `sc.nextLine()` : Reads to next newline character. Must be used two time after sc.nextInt()
- `sc.hasNext()`	to check availablity
- There is <span style="color:red;=">NO</span> `sc.nextChar()` in java

---
---

## printf()
- similar to printf in [C Programming](https://github.com/MASTREX/My-Quick-Rev-Notes/tree/main/C#printf)
- System.out.printf(format, arguments);
- System.out.printf(locale, format, arguments);
- `%[flags][width][.precision]conversion-character`

## Math module
- For vey precise calculation use `BigDecimal`
- `Integer.MAX_VALUE`
- `Integer.MIN_VALUE`
- `Long.MAX_VALUE`
- 273469738462784L	: 'L' at last of long literals
- Math.PI	value of pi
- Math.max(a, b)
- Math.abs(x) absolute value (mainly for absolute difference)
- ceil, floor, sin, cos, etc

## BigInteger

- **Use Cases:**
  - Use `BigInteger` for large integer values beyond `long` range.
  - Use `BigDecimal` for floating-point numbers.
  - `BigInteger` can grow as large as available RAM allows.

- **Syntax:**
  ```java
  BigInteger num = new BigInteger("<String>");
  ```

- **Common Methods:**
  ```java
  num.add(BigInteger val);       // Returns sum as BigInteger
  num.mod(BigInteger val);       // Returns remainder as BigInteger
  num.pow(int val);              // Returns num^val as BigInteger
  num.compareTo(BigInteger val); // Returns -1, 0, or 1 (less than, equal, greater than)
  ```

## Conditional and Control Flows
### `switch`
- switch statement and switch expression are different. switch expression do not use break and has `->` instead of `:`

### foreach
- `for(int i: int Array[]) {}`
- `for(char ch: String s) {}`  <span style="color:red">// DO NOT WORK</span>, Instead use: `for (char ch: "xyz".toCharArray()) {}`	// this works

## Functions
Fucnction can not be referenced like object and hence Class variable and method can have **same name**.
 > like `Queue.size` will refer to instance variable size not `size()` method.

---
---

# Classes and Objects
### package
- When importing another package, package declaration must be the first statement followed by package import.

### Inheritance
'super' is used to call from parent class when child class has same name variable and methods
### Polymorphism
> ParentClass name = new ChildClass;
- A parent class reference can refer to a child class object.
- Only the overridden methods(of child class) can be called using the parent class reference. Any new method created in the child class will not be accessible using the parent class reference.
- If both classes has same name variable but called with parent reference then parent variable will be accessed.
- Static methods are not overridden. They will be called based on the type of reference used.
Nested Class

### Method of class `Object`
- `tostring()`: convert object ot string
- `hashCode()`
- `equals(Object obj)`: compare passed object with current object
- `finalize()`:
- `getClass()`
- `clone()`
- `wait()`, `notify()`, `notifyAll()`

## Static Variable
- single copy to all instances.
- single value can be directly initialised but expression which must be processed before initialisation should be in static block.
- static variable SHOULD be accessed using class name and not object name
- A static method or static block can only access static variables and cannot access instance variables.
- A static inner class is a nested class which is a static member of the outer class. It can be accessed without instantiating the outer class, using other static members. Just like static members, a static nested class does not have access to the instance variables and methods of the outer class
- static keyword can be used before class "static class \<ClassName> {***}". They execute as soon as class is loaded

## Iterator
	java.util.Iterator;
  hasNext();
  next();
  <!-- // TODO -->

## Generics classes
- Class
  ```java
	public class <T> classname{
	}
  ```

- method:
  ```java
	public static <T, V> void func(T typeTpara, V typeVpara) {
	}
  ```

## Comparable
Example usage
```java
public static class Person implements Comparable<Person> {
  String name;
  int height;

  Person(String name, int h) {
    this.name = name;
    height = h;
  }

  @Override
  public int compareTo(Person o) {
    if (this.height > o.height) {
      return 1;
    } else if (this.height == o.height) {
      return 0;
    } else {
      return -1;
    }
  }
}
```

## Interface

- **Enforces function signatures**
- **Key Characteristics:**
  - Interface reference variable can hold the object of its implementing class only, not of itself.
  - Contains method signatures and constant declarations.
  - Methods declared in an interface are implicitly `public` and `abstract`.
  - Data fields are implicitly `public`, `static`, and `final` (constants).
- **Inheritance & Implementation:**
  - An interface can extend multiple interfaces.
  - A class can implement multiple interfaces (simulating multiple inheritance).
  - A class can extend only one class but implement any number of interfaces.
  - The `implements` keyword is used to implement an interface.
  - A class implementing an interface must implement all specified methods or be declared `abstract`.
- **Dynamic Binding:**
  - An interface creates a type; its reference can be used to refer to objects of implementing classes, enabling dynamic binding.

## Exception

- **Exception Handling Rules:**
  - The catch block of a parent class exception must appear after the catch block of a child class exception.
  - A generic `catch` block can handle all exceptions.
  - The generic `catch` block must be the last catch block in a try-catch sequence.

- **Explicit Exception Raising:**
  - Exceptions can be raised explicitly using the `throw` keyword.
    ```java
    throw new <exceptionclass>("error message");
    ```

- **Types of Exceptions:**
  - **Checked Exception** – Must be handled using `try-catch` or declared with `throws`.
  - **Unchecked Exception** – Typically derived from `RuntimeException`, not mandatory to handle.

- **Exception Propagation:**
  - If an exception is propagated using `throw`, the method must be declared with the `throws` keyword.

- **User-Defined Exception:**
  - Must extend the `Exception` class.

## try-catch-finally Example:
```java
try {
    // assumed arr.length = 3
    int i = arr[4];  // This statement raises an exception
    System.out.println("Inside try block");  // Will not execute
}
catch (ArrayIndexOutOfBoundsException ex) {
    System.out.println("Exception caught in catch block");
}
finally {
    System.out.println("finally block executed");
}
```

---
---

## Annotations

- **@Override**
  - Ensures that a method is actually overriding a parent method.
  - If applied to a method that does not override any parent method, a compilation error occurs.
  - Improves readability and prevents accidental method signature mismatches.

## Enum
```java
// Defining an Enum
public enum DayOfTheWeek {
    SUN, MON, TUES, WED, THUR, FRI, SAT
}

// Working with Enum Methods
DayOfTheWeek weekDay = DayOfTheWeek.TUES;
System.out.println(weekDay);  // Output: TUES

// Supported Methods
weekDay.name();     // Returns the name as a String ("TUES")
weekDay.ordinal();  // Returns the index (2, since index starts from zero)

// Getting all enum values
DayOfTheWeek[] allDays = DayOfTheWeek.values();
System.out.println(Arrays.toString(allDays));  // Output: [SUN, MON, TUES, WED, THUR, FRI, SAT]
```
Enum Properties
- Enums have an implicit order
- `.ordinal()` provides the index of an enum constant
- `.name()` returns the name of the constant as a string
- `EnumName.values()` returns an array of all enum values

## Lambda Expression

- **Syntax:**
  ```java
  parameter -> expression
  (parameter1, parameter2) -> expression
  (parameter1, parameter2) -> { code block }  // Code block must have a return statement
  ```
- **Example:**
  ```java
  ArrayList<Integer> numbers = new ArrayList<Integer>();
  numbers.add(5);
  numbers.add(9);
  numbers.add(8);
  numbers.add(1);

  // Using lambda expression to iterate and print elements
  numbers.forEach((n) -> { System.out.println(n); });
  ```

## Bit Manipulation

- **Shift Operators:**
  - `<<` : Left shift
  - `>>` : Signed (Arithmetic) right shift
  - `>>>` : Unsigned (Logical) right shift

- **Key Differences:**
  - `>>` (Arithmetic Right Shift): Preserves the sign bit (sign-extension).
  - `>>>` (Logical Right Shift): Fills the leftmost bits with zeros (zero-extension).
  - Java **does not** support an unsigned left shift operator.

- **Behavior:**
  ```java
  int n = -8;  // 11111111 11111111 11111111 11111000 (in 32-bit binary)
  System.out.println(n >> 2);  // Arithmetic shift: 11111111 11111111 11111111 11111110 (-2)
  System.out.println(n >>> 2); // Logical shift:   00111111 11111111 11111111 11111110 (1073741822)
  ```

## JUnit

- **Overview:**
  - JUnit is used for unit testing in Java.
  - A test method can either make assertions or expect exceptions.

- **Assertions (`org.junit.Assert`):**
  - The `Assert` class provides methods to verify expected outcomes in tests.

- **Common Assertions:**
  ```java
  import static org.junit.Assert.*;

  assertEquals(expected, actual);      // Checks if values are equal
  assertTrue(condition);               // Checks if condition is true
  assertFalse(condition);              // Checks if condition is false
  assertNotNull(object);               // Checks if object is not null
  assertNull(object);                  // Checks if object is null
  assertArrayEquals(expected, actual); // Checks if arrays are equal
  ```

## package `java.util.function`

| Interface | Function Method | No of Arguments | Returns a value | Can be chained |
|-|-|-|-|-|
| Consumer | accept() | 1 or 2 (Bi) | No | Yes |
| Supplier | get() | 0 | Yes | No |
| Predicate | test() | 1 or 2 (Bi) | Yes - boolean | Yes |
| function | apply() | 1 or 2 (Bi) | Yes | Yes |
| UnaryOperator | depends on type | 1 | Yes - smae type as argument | Yes |
||||||
