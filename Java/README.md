- For vey precise calculation use `BigDecimal`
- `Integer.MAX_VALUE`
- `Integer.MIN_VALUE`
- `Long.MAX_VALUE`
- 273469738462784L	: 'L' at last of long literals

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
- Math.PI	value of pi
- Math.max(a, b)
- Math.abs(x) absolute value (mainly for absolute difference)
- ceil, floor, sin, cos, etc

## Conditional and Control Flows
### `switch`
- switch statement and switch expression are different. switch expression do not use break and has `->` instead of `:`

### foreach
- `for(int i: int Array[]) {}`
- `for(char ch: String s) {}`  <span style="color:red">// DO NOT WORK</span> `for (char ch: "xyz".toCharArray()) {}`	// this works

## Array
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

## Strings
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
  - - `s.substring(0, 3)`:	0 index included, 3 index excluded		( **O(n) complexity** )
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

## StringBuilder
- `new StringBuilder()` : It creates an empty String Builder with the initial capacity of **16**.
- `StringBuilder(String str)` It creates a String Builder with the specified string.
- `StringBuilder(int length)` It creates an empty String Builder with the specified capacity as length.

#### functions
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

## Functions
Fucnction can not be referenced like object and hence Class variable and method can have **same name**.
 > like `Queue.size` will refer to instance variable size not `size()` method.

---
---

# Classes and Objects
### Method of class `Object`
- `tostring()`: convert object ot string
- `hashCode()`
- `equals(Object obj)`: compare passed object with current object
- `finalize()`:
- `getClass()`
- `clone()`
- `wait()`, `notify()`, `notifyAll()`

## enum
- enum has order
- `.ordinal()` : to get the index of any enum constant
- `.name()` : for name string
- `EnumName.values()` : to convert enum to a list

## package `java.util.function`
| Interface | Function Method | No of Arguments | Returns a value | Can be chained |
|-|-|-|-|-|
| Consumer | accept() | 1 or 2 (Bi) | No | Yes |
| Supplier | get() | 0 | Yes | No |
| Predicate | test() | 1 or 2 (Bi) | Yes - boolean | Yes |
| function | apply() | 1 or 2 (Bi) | Yes | Yes |
| UnaryOperator | depends on type | 1 | Yes - smae type as argument | Yes |
||||||
