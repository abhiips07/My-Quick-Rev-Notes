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

## Functions
Fucnction can not be referenced like object and hence Class variable and method can have **same name**.
 > like `Queue.size` will refer to instance variable size not `size()` method.

## Classes and Objects
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
