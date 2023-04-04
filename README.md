# Kotlin Cheatsheet
Kotlin is a modern, multi-paradigm programming language that runs on the Java Virtual Machine (JVM) and is designed to be more concise and safer than Java. A Kotlin cheat sheet is a quick reference guide that provides a concise summary of the most important Kotlin syntax and features. If you'd like to support me, please give a star to this repository.⭐🙏

![Kotlin logotype](https://github.com/alidehkhodaei/kotlin-cheatsheet/blob/add-cheatsheet/images/kotlin_logotype.jpg)

# Table of Contents


- [Introduction](#introduction)
  - [First Kotlin program](#first-kotlin-program)
  - [Get input from user](#get-input-from-user)
  - [Comments](#comments)
  - [KDoc](#kdoc)
  - [var vs val](#var-vs-val)
  - [Type Inference](#type-inference)
  - [Type Conversion](#type-conversion)
  - [Lazy and lateinit](#lazy-and-lateinit)
  - [Types](#types)
  - [String templates](#string-templates)
  - [Operators](#operators)
- [Control Flow](#control-flow)
  - [If-else](#if-else)
  - [Conditional Expression](#conditional-expression)
  - [When](#when)
  - [For loop](#for-loop)
  - [Ranges](#ranges)
  - [While](#while)
  - [Do while](#do-while)
  - [Break and Continue](#break-and-continue)
  - [Exceptions](#exceptions)
- [Functions](#functions)
  - [Function Declaration](#function-declaration)
  - [Default arguments and named arguments](#default-arguments-and-named-arguments)
  - [Function Return Types](#function-return-type)
  - [Local functions](#local-functions)
  - [Member functions](#member-functions)
  - [Generic functions](#generic-functions)
  - [Lambda Expressions](#lambda-expressions)
  - [Extension Functions and Properties](#extension-functions-and-Properties)
  - [Higher-Order Functions](#higher-order-functions)
  - [Inline functions](#inline-functions)
  - [Operator overloading](#operator-overloading)
  - [Variable number of arguments (varargs)](#varargs)
  - [Infix notation](#infix-notation)
  - [Tail recursive functions](#tail-recursive-functions)
- [Classes and objects](#classes-and-objects)

- [Other Topics](#other)
  - [Destructuring declarations](#destructuring-declarations)
  - [Reflection](#reflection)
  - [Annotations](#annotations)
  - [Packages and imports](#packages-and-imports)
  - [Null safety](#null-safety)
  
  
## Introduction <a name="introduction"></a>
Kotlin is a modern, open-source programming language that is used for building multi-platform applications. It is concise, expressive, and powerful, with features such as null safety, extension functions, lambdas, and many others.
This cheat sheet will cover some of the essential Kotlin concepts.

### First Kotlin program <a name="first-kotlin-program"></a>

This is an example of printing "Hello world" in Kotlin:
```kotlin
fun main() {
    println("Hello world")
}
```
### Get input from user  <a name="get-input-from-user"></a>
To get input from the user in Kotlin, you can use the readLine() function.
This is an example:
```kotlin
fun main() {
    print("Enter your name: ")
    val name = readLine()
    println("Hello, $name!")
}
```

### Comments<a name="comments"></a>

```kotlin
// This is an end-of-line comment

/* This is a block comment
   on multiple lines. */
```
Block comments in Kotlin can be nested.
```kotlin
/* The comment starts here
/* contains a nested comment *⁠/
and ends here. */
```
### KDoc <a name="kdoc"></a>
KDoc is the documentation format for Kotlin, similar to Javadoc for Java. KDoc is used to generate documentation for Kotlin classes, functions, and properties. KDoc comments start with the /** and end with */.
This is an example:
```kotlin
/**
 * Calculates the sum of two integers.
 *
 * @param a The first integer to add.
 * @param b The second integer to add.
 * @return The sum of the two integers.
 */
fun sum(a: Int, b: Int): Int {
    return a + b
}
```

### var vs val <a name="var-vs-val"></a>
In Kotlin, variables can be declared using either the var or val keyword.

var variables are mutable, meaning their value can be changed after they are initialized.

```kotlin
var x = 5
x = 10
```
val variables, on the other hand, are immutable, meaning their value cannot be changed after they are initialized.

```kotlin
val y = 5
y = 10 // This will result in a compilation error
```

### Type Inference <a name="type-inference"></a>

Kotlin supports type inference, which means the compiler can infer the type of a variable from its initial value.

```kotlin
val x = 5 // The type of x is inferred to be Int
val y = "hello" // The type of y is inferred to be String
```

Variables in Kotlin can also be declared without an initial value, but in that case, the type must be explicitly specified:

```kotlin
var z: Double // Valid, z has no initial value
// println(z) // Invalid, z is not initialized and has no value yet
z = 3.14 // Valid, z is initialized with a value
```
### Type Conversion <a name="type-conversion"></a>

Kotlin provides several methods for converting between data types. Here's an example in Kotlin that demonstrates various methods of type conversion.

```kotlin
    val str: String = "123"
    val num: Int = str.toInt() // Convert String to Int

    val dbl: Double = 123.45
    val int: Int = dbl.toInt() // Convert Double to Int

    val lng: Long = 9876543210
    val flt: Float = lng.toFloat() // Convert Long to Float

    val bol: Boolean = true
    val strBol: String = bol.toString() // Convert Boolean to String

    val char: Char = 'A'
    val intChar: Int = char.toInt() // Convert Char to Int

    val byte: Byte = 127
    val short: Short = byte.toShort() // Convert Byte to Short

```

### Lazy and lateinit  <a name="lazy-and-lateinit"></a>

A lazy variable is initialized only when it is first accessed.

```kotlin
val myLazyVar: String by lazy {
    // Perform some expensive operation to initialize the variable
    "Hello World"
}

// The variable is not initialized until it is first accessed
println(myLazyVar) // Prints "Hello World"
```
A lateinit variable is used when you know that a variable will be initialized before it is used, but you don't want to assign an initial value at the time of declaration.

```kotlin
lateinit var myLateInitVar: String

// The variable is not initialized yet, so trying to access it will throw an exception
// println(myLateInitVar) // This line would throw a "lateinit property has not been initialized" exception

// Sometime later, the variable is initialized
myLateInitVar = "Hello World"

// Now we can access the variable without an exception
println(myLateInitVar) // Prints "Hello World"
```
### Types <a name="types"></a>
Here's a brief overview of the most commonly used types:

```kotlin
    val booleanVar: Boolean = true
    val byteVar: Byte = 127
    val shortVar: Short = 32767
    val intVar: Int = 2147483647
    val longVar: Long = 9223372036854775807L
    val floatVar: Float = 3.14f
    val doubleVar: Double = 3.14159265358979323846
    val charVar: Char = 'A'
    val stringVar: String = "Hello, world!"
```

### String templates <a name="string-templates"></a>

```kotlin
val name= "Ali"
val result= "My name is $name" 
```

### Operators <a name="operators"></a>

Arithmetic operators

```kotlin
  val a = 10
  val b = 5
  println(a + b) // Prints "15"
  println(a - b) // Prints "5"
  println(a * b) // Prints "50"
  println(a / b) // Prints "2"
  println(a % b) // Prints "0"
 ```
  
 Comparison operators
```kotlin
  val c = 10
  val d = 5
  println(c > d) // Prints "true"
  println(c >= d) // Prints "true"
  println(c < d) // Prints "false"
  println(c <= d) // Prints "false"
  println(c == d) // Prints "false"
  println(c != d) // Prints "true"
  val e = Integer(10)
  val f = Integer(10)
  println(e === f) // Prints "false"
  val g = e
  println(e === g) // Prints "true"
 ```
  
Assignment operators
  
 ```kotlin
  var h = 10
  h += 5
  println(h) // Prints "15"
  h -= 5
  println(h) // Prints "10"
  h *= 2
  println(h) // Prints "20"
  h /= 4
  println(h) // Prints "5"
  h %= 3
  println(h) // Prints "2"
 ```
    
Logical operators    
```kotlin  
  val i = true
  val j = false
  println(i && j) // Prints "false"
  println(i || j) // Prints "true"
  println(!i) // Prints "false"
 ```
    
Bitwise operators

```kotlin
  val k = 0b1010
  val l = 0b1100
  println(k and l) // Prints "8" (0b1000)
  println(k or l) // Prints "14" (0b1110)
  println(k xor l) // Prints "6" (0b0110)
  println(k.inv()) // Prints "-11" (0b11111111111111111111111111110101)
 ```

Elvis operator

 ```kotlin
  val m: String? = null
  val n = m ?: "default"
  println(n) // Prints "default"
```
    
Range operator

```kotlin
  val o = 1..10
  println(o.contains(5)) // Prints "true"
  println(o.contains(11)) // Prints "false"
```
    
 In operator
 
 ```kotlin
  val p = arrayOf("apple", "banana", "orange")
  println("apple" in p) // Prints "true"
  println("grape" in p) // Prints "false"
```

## Control flow  <a name="control-flow"></a>

### If-else <a name="if-else"></a>

```kotlin
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

### Conditional Expression <a name="conditional-expression"></a>
The syntax for conditional expressions is similar to that of the ternary operator in other programming languages.

```kotlin
val max = if (a > b) a else b         
```

### When <a name="when"></a>

```kotlin
when (value) {
    condition1 -> // Code to execute if value matches condition1
    condition2 -> // Code to execute if value matches condition2
    else -> // Code to execute if value does not match any condition
}
```
### For loop <a name="for-loop"></a>
```kotlin
for (item in collection) {
    // Code to execute for each item in collection
}
```

### Ranges <a name="ranges"></a>
There is a set of tools for defining ranges in Kotlin.
```kotlin

for(i in 0..3) {             
    print(i)
}

for(i in 0 until 3) {       
    print(i)
}

for(i in 2..8 step 2) {     
    print(i)
}

for (i in 3 downTo 0) {     
    print(i)
}
```
Char ranges are also supported.
```kotlin
for (c in 'a'..'d') {   
    print(c)
}
```
Ranges are also useful in if statements.

```kotlin
if (x in 1..5) {           
    print("x is in range from 1 to 5")
}
```
### While <a name="while"></a>
```kotlin  
while (condition) {
    // Code to execute as long as condition is true
}
```

### Do While <a name="do-while"></a>

```kotlin
do {
    // Code to execute at least once
} while (condition)
```

### Break and Continue <a name="break-and-continue"></a>

```kotlin
for (i in 1..10) {
    if (i == 5) {
        break // Exit loop when i is equal to 5
    }
    if (i % 2 == 0) {
        continue // Skip even numbers and continue to the next iteration
    }
    // Code to execute for each odd number between 1 and 10
}
```
### Exceptions  <a name="exceptions"></a>

To throw an exception object, use the throw expression:

```kotlin
throw Exception("Exception...")
```
To catch an exception, use the try...catch expression:

```kotlin
try {
    // some code
} catch (e: SomeException) {
    // handler
} finally {
    // optional finally block
}
```
The Nothing type: This type has no values and is used to mark code locations that can never be reached. In your own code, you can use Nothing to mark a function that never returns.
```kotlin
fun fail(message: String): Nothing {
    throw IllegalArgumentException(message)
}
```
## Functions <a name="functions"></a>

### Function Declaration  <a name="function-declaration"></a>

```kotlin
fun sayHello() {
    println("Hello!")
}

fun greet(name: String) {
    println("Hello, $name!")
}
```

### Default arguments and named arguments  <a name="default-arguments-and-named-arguments"></a>

  ```kotlin
fun greet(name: String = "World", greeting: String = "Hello") {
    println("$greeting, $name!")
}

fun main() {
    // calling function with default arguments
    greet() // output: Hello, World!

    // calling function with named arguments
    greet(greeting = "Hi", name = "Alice") // output: Hi, Alice!

    // calling function with some named arguments
    greet(name = "Bob") // output: Hello, Bob!
}

  ```
### Function Return Types  <a name="function-return-type"></a>

```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}

fun multiply(a: Int, b: Int) = a * b
```

Unit-returning functions
If a function does not return a useful value, its return type is Unit. Unit is a type with only one value - Unit. This value does not have to be returned explicitly.

```kotlin
fun printHello(): Unit {
  print("Hello")
}
```
Or
```kotlin
fun printHello() {
   print("Hello")
}
```

### Local functions <a name="local-functions"></a>

Kotlin supports local functions, which are functions inside other functions.
printMessage() is a local function defined within the main() function.
```kotlin
fun main() {
    fun printMessage(message: String) {
        println("Message: $message")
    }

    printMessage("Hello, world!")
}
```

### Member functions <a name="member-functions"></a>

A member function is a function that is defined inside a class or object.

```kotlin
class Sample {
    fun foo() { print("") }
}
```

### Generic functions <a name="generic-functions"></a>

Functions can have generic parameters, which are specified using angle brackets before the function name

```kotlin
fun <T> function(item: T){ 
 //Code
}
```

### Lambda Expressions  <a name="lambda-expressions"></a>

```kotlin
val sum = { a: Int, b: Int -> a + b }

val square: (Int) -> Int = { it * it }
```
### Extension Functions and Properties <a name="extension-functions-and-Properties"></a>
Extension Functions and Properties in Kotlin allow adding new functionality or properties to existing classes without modifying their source code.
```kotlin
// Extension function
fun String.reverse(): String {
    return this.reversed()
}

// Extension property
val String.firstChar: Char
    get() = this[0]
```
```kotlin
fun main() {
    val str = "Ali"
    println(str.reverse())  // Prints "ilA"
    println(str.firstChar)  // Prints "A"
}

```
### Higher-Order Functions <a name="higher-order-functions"></a>

A higher-order function is a function that takes another function as parameter and/or returns a function.

Taking Functions as Parameters
```kotlin
fun calculate(x: Int, y: Int, operation: (Int, Int) -> Int): Int { 
    return operation(x, y)                                         
}

fun sum(x: Int, y: Int) = x + y                                 
```
```kotlin
fun main() {
    val sumResult = calculate(1, 7, ::sum)                         
    val mulResult = calculate(1, 7) { a, b -> a * b }             
}
```
Returning Functions
```kotlin
fun operation(): (Int) -> Int {                                     
    return ::square
}

fun square(x: Int) = x * x                                          
```
```kotlin
fun main() {
    val func = operation()                                          
    println(func(7))                                                
}
```
### Inline functions <a name="inline-functions"></a>


### Operator overloading <a name="operator-overloading"></a>
Operator overloading in Kotlin allows you to define and use custom operators for your own classes and types.

```kotlin
data class Point(val x: Int, val y: Int) {
    operator fun plus(other: Point): Point {
        return Point(x + other.x, y + other.y)
    }
}
```

```kotlin
fun main() {
    val p1 = Point(1, 2)
    val p2 = Point(3, 4)
    val p3 = p1 + p2 // using the overloaded '+' operator
    println(p3) // Output: Point(x=4, y=6)
}

```

### Variable number of arguments (varargs) <a name="varargs"></a>

 Varargs is a feature that allows you to pass a variable number of arguments of the same type to a function
 
```kotlin
fun printNumbers(vararg numbers: Int) {
    for (number in numbers) {
        println(number)
    }
}

fun main() {
    printNumbers(1, 2, 3) // prints 1, 2, 3
    printNumbers(4, 5, 6, 7, 8) // prints 4, 5, 6, 7, 8
}

```

### Infix notation <a name="infix-notation"></a>

Infix in Kotlin allows you to define functions that can be called using infix notation (i.e., without using parentheses and the dot notation).

``kotlin
infix fun Int.times(str: String) = str.repeat(this)

fun main() {
    val str = 5 times "Hello "
    println(str) // Output: "Hello Hello Hello Hello Hello "
}
```

### Tail recursive functions <a name="tail-recursive-functions"></a>

Tail recursive functions in Kotlin are functions that optimize memory usage by reusing the same stack frame for each recursive call.

```kotlin

```
## Other Topics <a name="Other-topics"></a>

### Destructuring declarations <a name="destructuring-declarations"></a>
Destructuring declarations in Kotlin allow you to break down objects into individual variables in a single line of code.

```kotlin
 val person=Person("Ali",24)
 val (name, age) = person
```
### Reflection <a name="reflection"></a>
Reflection is a set of language and library features that allows you to introspect the structure of your program at runtime. 

This is a example:
```kotlin

data class Person(val name: String, val age: Int)

fun main() {
    val person = Person("Ali", 24)
    
    // Get the class object of Person using reflection
    val personClass = Person::class
    
    // Get the properties of Person using reflection
    val properties = personClass.memberProperties
    
    // Print the values of the properties
    properties.forEach { property ->
        val value = property.get(person)
        println("${property.name}: $value")
    }
}

```
### Annotations <a name="annotations"></a>
Annotations in Kotlin are special labels that can be applied to declarations such as classes, functions, and properties to provide additional information or metadata about the declaration at compile-time and runtime.
This is a example:
```kotlin
@Deprecated("Use newMethod() instead", ReplaceWith("newMethod()"))
fun oldMethod() {
    // ...
}
```

### Packages and imports <a name="packages-and-imports"></a>
Packages are used to group related classes, functions, and other declarations together. Imports are used to make declarations from other packages accessible within your current file.

```kotlin
package com.example.models

class Person(val name: String, val age: Int) {
    // class implementation
}
```
```kotlin
import com.example.models.Person

fun main() {
    val person = Person("John", 30)
    println("Name: ${person.name}, Age: ${person.age}")
}
```

### Null safety <a name="null-safety"></a>

Kotlin has null safety, which helps prevent null pointer exceptions. Kotlin provides operators to work with nullable types, including safe call, elvis, and not-null assertion operators. These features help developers write more reliable code and avoid null pointer exceptions.

```kotlin

    var nullableStr: String? = null
    var nonNullStr: String = "Hello"

    // safe call operator
    println(nullableStr?.length) // prints null

    // elvis operator
    val len = nullableStr?.length ?: -1
    println(len) // prints -1

    // not-null assertion operator
    // throws null pointer exceptions because nullableStr is null
    println(nullableStr!!.length)

    // this would not compile because nonNullStr is not nullable
    // nonNullStr = null

```
