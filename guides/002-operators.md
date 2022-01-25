# Chapter 2 - Operators


## 2.1 Introduction

An operator is a special symbol or phrase that you use to check, change, or combine values. For example, the addition operator (`+`) adds two numbers, as in `let i = 1 + 2`, and the logical AND operator (`&&`) combines two Boolean values, as in `if enteredDoorCode && passedRetinaScan`.

## 2.2 Assignment operator

The operator symbol is `=`. It is used to assign values to variables and constants.

Example: `var age = 21`

## 2.3 Arithmentic operators

Swift supports the four standard arithmetic operators for all number types:

1. Addition (`+`)
2. Subtraction (`-`)
3. Multiplication (`*`)
4. Division (`/`)

Example:
```swift
1 + 2       // equals 3
5 - 3       // equals 2
2 * 3       // equals 6
10.0 / 2.5  // equals 4.0
let message = "Hello,"+" World
```

>**NOTE:** We can use `+` for string concatenation as well. `let message = "Hello,"+" World"`.

## 2.4 Remainder Operator

The remainder operator (`a % b`) works out how many multiples of `b` will fit inside `a` and returns the value that’s left over (known as the remainder).

Example: `5 % 2 //outputs 1`

## 2.5 Unary Minus Operator
The sign of a numeric value can be toggled using a prefixed -, known as the unary minus operator:

```swift
let three = 3
let minusThree = -three       // minusThree equals -3
let plusThree = -minusThree   // plusThree equals 3, or "minus minus three"
```

The unary minus operator (-) is prepended directly before the value it operates on, without any white space.

## 2.6 Unary Plus Operator

The unary plus operator (+) simply returns the value it operates on, without any change:

```swift
let minusSix = -6
let alsoMinusSix = +minusSix  // alsoMinusSix equals -6
```
Although the unary plus operator doesn’t actually do anything, you can use it to provide symmetry in your code for positive numbers when also using the unary minus operator for negative numbers.

## 2.7 Compound Assignment Operators

Like C, Swift provides compound assignment operators that combine assignment (=) with another operation. One example is the addition assignment operator (+=):

```swift
var a = 1
a += 2

// a is now equal to 3
```
The expression a += 2 is shorthand for a = a + 2. Effectively, the addition and the assignment are combined into one operator that performs both tasks at the same time.

>**NOTE:** The compound assignment operators don’t return a value. For example, you can’t write let b = a += 2.

## 2.8 Comparison Operators

Swift supports the following comparison operators:

1. Equal to (a == b)
2. Not equal to (a != b)
3. Greater than (a > b)
4. Less than (a < b)
5. Greater than or equal to (a >= b)
6. Less than or equal to (a <= b)

>**NOTE:** Swift also provides two identity operators (`===` and `!==`), which you use to test whether two object references both refer to the same object instance. For more information, see [Identity Operators](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html#ID90).

Each of the comparison operators returns a Bool value to indicate whether or not the statement is true:

```swift
1 == 1   // true because 1 is equal to 1
2 != 1   // true because 2 isn't equal to 1
2 > 1    // true because 2 is greater than 1
1 < 2    // true because 1 is less than 2
1 >= 1   // true because 1 is greater than or equal to 1
2 <= 1   // false because 2 isn't less than or equal to 1
```

## 2.9 Ternary Conditional Operator

The ternary conditional operator is a special operator with three parts, which takes the form `question ? answer1 : answer2`. It’s a shortcut for evaluating one of two expressions based on whether question is `true` or `false`. If question is `true`, it evaluates `answer1` and returns its value; otherwise, it evaluates `answer2` and returns its value.

The ternary conditional operator is shorthand for the code below:

```swift
if question {
    answer1
} else {
    answer2
}
```

Here’s an example, which calculates the height for a table row. The row height should be 50 points taller than the content height if the row has a header, and 20 points taller if the row doesn’t have a header:

```swift
let contentHeight = 40
let hasHeader = true
let rowHeight = contentHeight + (hasHeader ? 50 : 20)
// rowHeight is equal to 90
```

The example above is shorthand for the code below:

```swift
let contentHeight = 40
let hasHeader = true
let rowHeight: Int
if hasHeader {
    rowHeight = contentHeight + 50
} else {
    rowHeight = contentHeight + 20
}
// rowHeight is equal to 90
```

## 2.9 Nil-Coalescing Operator

The nil-coalescing operator (`a ?? b`) unwraps an optional `a` if it contains a value, or returns a default value `b` if a is `nil`. The expression a is always of an optional type. The expression `b` must match the type that’s stored inside `a`.

The nil-coalescing operator is shorthand for the code below:

```swift 
a != nil ? a! : b
```

The code above uses the ternary conditional operator and forced unwrapping (a!) to access the value wrapped inside a when a isn’t nil, and to return b otherwise. The nil-coalescing operator provides a more elegant way to encapsulate this conditional checking and unwrapping in a concise and readable form.

>**NOTE:** If the value of a is non-nil, the value of b isn’t evaluated. This is known as short-circuit evaluation.

The example below uses the nil-coalescing operator to choose between a default color name and an optional user-defined color name:

```swift
let defaultColorName = "red"
var userDefinedColorName: String?   // defaults to nil

var colorNameToUse = userDefinedColorName ?? defaultColorName
// userDefinedColorName is nil, so colorNameToUse is set to the default of "red"
```

The `userDefinedColorName` variable is defined as an optional `String`, with a default value of `nil`. Because `userDefinedColorName` is of an optional type, you can use the nil-coalescing operator to consider its value. In the example above, the operator is used to determine an initial value for a `String` variable called `colorNameToUse`. Because `userDefinedColorName` is `nil`, the expression `userDefinedColorName ?? defaultColorName`returns the value of `defaultColorName`, or `"red"`.

If you assign a non-nil value to `userDefinedColorName` and perform the nil-coalescing operator check again, the value wrapped inside `userDefinedColorName` is used instead of the default:

```swift
userDefinedColorName = "green"
colorNameToUse = userDefinedColorName ?? defaultColorName
// userDefinedColorName isn't nil, so colorNameToUse is set to "green"
```

## 2.10 Range operators

Swift includes several range operators, which are shortcuts for expressing a range of values.

### 2.10.1 Closed Range Operator

The closed range operator (`a...b`) defines a range that runs from `a` to `b`, and includes the values `a` and `b`. The value of `a` must not be greater than `b`. It's bound is as follows: `[a,b]`.

The closed range operator is useful when iterating over a range in which you want all of the values to be used, such as with a `for-in` loop:

```swift
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```

### 2.10.2 Half-Open Range Operator

The half-open range operator (`a..<b`) defines a range that runs from `a` to `b`, but doesn’t include `b`. It’s said to be half-open because it contains its first value, but not its final value. As with the closed range operator, the value of a must not be greater than b. If the value of a is equal to b, then the resulting range will be empty. It's bound is as follows: `[a,b)`.

Half-open ranges are particularly useful when you work with zero-based lists such as arrays, where it’s useful to count up to (but not including) the length of the list:

let names = ["Anna", "Alex", "Brian", "Jack"]
let count = names.count
for i in 0..<count {
    print("Person \(i + 1) is called \(names[i])")
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack