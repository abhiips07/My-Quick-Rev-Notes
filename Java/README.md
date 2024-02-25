- For vey precise calculation use `BigDecimal`

## Conditional and Control Flows
### `switch`
- switch statement and switch expression are different. switch expression do not use break and has `->` instead of `:`

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
