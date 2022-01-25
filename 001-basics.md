# The Basics

In this chapter, we are going to learn all about variables in swift.

## 1.1 Introduction

A variable is an entity whose value can change over time. We use the the `var` keyword to make a variable.

Syntax: `var variableName: DataType = Value`

Example: `var playerName: String = "Ariel"`

## 1.2 Built-in types

We have following built-in types in swift.

1. **Integers** - `Int`
2. **Floats** - `Float` 
3. **Booleans** - `Bool` 
4. **String** - `String`
5. **Character** - `Character` 
6. **Double** = `Double`
7. **Array** - `Array`
8. **Dictionary** = `Dictionary`
9. **Set** - `Set`

**Note:** 

1. There is no such thing as default value in Swift. Each variable must be defined and declared with a initial value. Variable needs to be initialised before being used.
2. Swift is type-safe. You cannot change the type on the fly. It's fixed once declared.

Example:

```swift
var age:Int = 27
var name: String = "Ariel"
var initial: Character = "A"
var bankBalance: Float = 21.60
var isAdmin: Bool = true
```

## 1.3 Type Infernece

We can skip the data types if we provide the initial value to them. Swift will then automatically figure out the data type matchin the literal.

Example: Rewrite above code with type inference.

```swift
var age:Int = 27
var name: String = "Ariel"
var initial: Character = "A"
var bankBalance: Float = 21.60
var isAdmin: Bool = true
```

## 1.4 Constants

Constant is an entity whose value once initialized remains the same over the lifetime of program. We use `let` keyword to declare a constant. Constants must be initilaized at least and at MOST once before using it.

Syntax: `let constantName: DataType = Value`
Example: `let hoursInADay = 24`

## 1.5 Comments

Comments in swift can be written as below.

```swift
// Single line comment

/*
Multi-line
Comments
*/
```





