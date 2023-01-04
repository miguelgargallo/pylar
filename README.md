# Pylar Lang

- [Pylar Lang](#pylar-lang)
  - [About Rust](#about-rust)
  - [About Python](#about-python)
    - [Comparison points](#comparison-points)
    - [Comparison table](#comparison-table)
  - [Keywords](#keywords)
  - [Building a Compiler for the "Pylar" Programming Language](#building-a-compiler-for-the-pylar-programming-language)
    - [Requirements](#requirements)
    - [File Structure for a Basic Compiler](#file-structure-for-a-basic-compiler)
  - [If Statements](#if-statements)
    - [In Rust](#in-rust)
    - [In Python](#in-python)
    - [In Pylar](#in-pylar)
    - [Comparison](#comparison)
      - [Comparison points](#comparison-points-1)
      - [Comparison table](#comparison-table-1)
    - [Differences](#differences)
    - [Table of differences](#table-of-differences)
  - [Loops](#loops)
    - [In Rust](#in-rust-1)
    - [In Python](#in-python-1)
    - [In Pylar](#in-pylar-1)
      - [Comparison points](#comparison-points-2)
      - [Comparison table](#comparison-table-2)
  - [Semantics](#semantics)
      - [Comparison points](#comparison-points-3)
      - [Comparison table](#comparison-table-3)
  - [Algorithms](#algorithms)
    - [Dijkstra's Algorithm](#dijkstras-algorithm)

## About Rust

Rust is a programming language developed by Mozilla. It is designed to be a safe and concurrent language that is suitable for systems programming. Rust has a strong emphasis on safety, performance, and concurrency, and aims to be a viable alternative to C and C++. It is syntactically similar to C++, but has a number of features that are designed to make it easier to write safe and correct code, such as a borrow checker that prevents dangling pointers. Rust also has a growing and active community, with a number of libraries and tools available to help developers build robust and efficient applications.

## About Python

Python is a general-purpose programming language that is widely used for web development, scientific computing, data analysis, and artificial intelligence. It is a high-level language, which means that it is easy to read and write and is more abstracted from the underlying hardware than low-level languages like C and C++. Python has a large standard library that supports many common programming tasks, such as connecting to web servers, reading and writing files, and working with data. There are also many third-party libraries available for Python, which provide additional functionality and make it an attractive choice for a wide range of tasks. Python is known for its simplicity and readability, and it is often used as a first language for people learning to program.

### Comparison points

Rust and Python are both popular programming languages, but they have some significant differences. Here are a few points of comparison:

    Syntax: Rust and Python have fairly different syntax. Rust's syntax is more similar to C and C++, with a focus on explicit variable declarations and manual memory management. Python's syntax is more concise and readable, with a focus on readability and simplicity.

    Safety: Rust is designed to be a safe language, with a number of features that help prevent common programming errors such as null or dangling pointers. Python is also a safe language, but it does not have the same level of compile-time checks for issues such as null pointers.

    Performance: Rust is generally considered to be a faster language than Python, due to its emphasis on statically-typed variables and manual memory management. Python is an interpreted language, which means that it is generally slower than compiled languages like Rust. However, Python has a number of optimization techniques that can help improve its performance, and it is often fast enough for many tasks.

    Concurrency: Both Rust and Python have support for concurrent programming, but they approach it in different ways. Rust has a number of language features that make it easier to write concurrent code, such as the std::sync and std::thread libraries. Python has a similar set of tools, including the threading and multiprocessing modules, but it also has a number of third-party libraries that can be used for concurrent programming.

    Use cases: Rust is primarily used for systems programming and applications that require high performance and low-level control. Python is used for a wider range of tasks, including web development, scientific computing, data analysis, and artificial intelligence.

### Comparison table

| Language | Pros                                                                                                      | Cons                                                                                                |
| -------- | --------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Rust     | - Fast and efficient<br>- Safe and concurrent<br>- Strong support for low-level programming               | - Steep learning curve<br>- Less mature ecosystem compared to Python                                |
| Python   | - Easy to learn and read<br>- Large standard library and active community<br>- Widely used in many fields | - Can be slower than compiled languages<br>- Dynamically-typed variables can lead to runtime errors |

## Keywords

Here is a list of the 25 most commonly used keywords in Rust:

    as
    break
    const
    continue
    crate
    else
    enum
    extern
    false
    fn
    for
    if
    impl
    in
    let
    loop
    match
    mod
    move
    mut
    pub
    ref
    return
    Self
    struct

Here is a list of the 25 most commonly used keywords in Python:

    and
    as
    assert
    async
    await
    break
    class
    continue
    def
    del
    elif
    else
    except
    False
    finally
    for
    from
    global
    if
    import
    in
    is
    lambda
    None
    nonlocal

Here are the most common keywords in Pylar:

    say - used to print output to the console
    ifis - used to specify a condition in an if statement
    bye - used to break out of a loop
    rest - used to continue to the next iteration of a loop
    and - used to specify multiple variables in a for loop
    also - used to specify multiple variables in a for loop
    now - used to execute the code block in a loop or conditional statement
    small - used to find the smallest element in a list or collection
    is - used to check if a variable is present in a list or collection
    range - used to specify a range of values in a for loop
    not - used to negate a condition in an if statement
    = - used to assign a value to a variable or to check for equality in a condition
    to - used to specify a range of values in a for loop
    while - used to specify a loop that continues until a certain condition is met
    then - used to specify a block of code to be executed if a condition is met
    begin - used to specify the start of a block of code
    end - used to specify the end of a block of code
    fun - used to define a function
    let - used to define a variable
    var - used to define a variable
    do - used to specify the start of a block of code to be executed repeatedly
    end - used to specify the end of a block of code to be executed repeatedly, also to end a loop or conditional statement

say - used to print output to the console
ifis - used to specify a condition in an if statement
bye - used to break out of a loop
rest - used to continue to the next iteration of a loop
and - used to specify multiple variables in a for loop
also - used to specify multiple variables in a for loop
now - used to execute the code block in a loop or conditional statement
small - used to find the smallest element in a list or collection
big - used to find the largest element in a list or collection
is - used to check if a variable is present in a list or collection
range - used to specify a range of values in a for loop
not - used to negate a condition in an if statement
= - used to assign a value to a variable or to check for equality in a condition
to - used to specify a range of values in a for loop
pass - used to lend permissions to the next instruction or now to execute the whole code
end - used to end a loop

- - used to lend the permissions to read, write and execute only to the next instruction, the next line, one line per instruction

## Building a Compiler for the "Pylar" Programming Language

In order to build a compiler for the "Pylar" programming language, which combines elements of Rust and Python, there are a few key requirements that need to be considered.

### Requirements

- Support for Rust-like statically-typed variables and manual memory management: Since "Pylar" is intended to combine the safety and performance of Rust with the simplicity and readability of Python, it will need to support Rust's approach to variable declarations and memory management. This will require the use of a type checker and borrow checker similar to Rust's, as well as a way to safely manage memory allocation and deallocation.

- Integration with Python's standard library and third-party libraries: In order to make "Pylar" a viable option for Python developers, it will need to be able to make use of the vast ecosystem of libraries and tools available for Python. This will require the compiler to have a way to import and use these libraries, as well as support for Python's dynamically-typed variables and object-oriented programming features.

- Support for concurrent programming: Both Rust and Python have strong support for concurrent programming, and "Pylar" will need to offer similar capabilities. This will require the inclusion of language features and libraries for managing threads and synchronization, as well as tools for debugging and testing concurrent code.

- Optimization and performance enhancements: While "Pylar" will likely be faster than Python due to its statically-typed variables and manual memory management, there may still be opportunities to optimize the code and improve performance. This will require the use of optimization techniques such as loop unrolling and inlining, as well as the ability to target specific hardware architectures and use specialized instructions and features.

- Ease of use and adoption: In order for "Pylar" to be successful, it will need to be easy for developers to learn and use. This will require clear and concise documentation, as well as a friendly and supportive community. It may also be beneficial to provide tools and resources for converting existing Rust and Python code to "Pylar", in order to make it easier for developers to adopt the new language.

- Support for web development: "Pylar" will need to be able to support web development, since it is a common use case for both Rust and Python. This will require the inclusion of a web framework similar to Flask or Django, as well as a way to compile the code to a format that can be run on a web server.

### File Structure for a Basic Compiler

```
* compiler
├── src
│ ├── lexer.rs
│ ├── parser.rs
│ ├── codegen.rs
│ ├── main.rs
│ └── util.rs
└── test
├── lexer_test.rs
├── parser_test.rs
├── codegen_test.rs
└── util_test.rs
```

A basic compiler typically consists of several different components that are responsible for different tasks. Some common components include:

- Lexer (src/lexer.rs): The lexer, also known as a tokenizer, is responsible for breaking the source code up into a series of tokens that can be easily parsed. This is typically the first step in the compilation process.

- Parser (src/parser.rs): The parser is responsible for taking the tokens produced by the lexer and turning them into a structured representation of the code, such as an abstract syntax tree (AST).

- Code generator (src/codegen.rs): The code generator is responsible for taking the AST produced by the parser and turning it into machine code or bytecode that can be executed by a computer.

- Main function (src/main.rs): The main function is the entry point for the compiler and is responsible for handling command-line arguments, setting up the necessary data structures, and calling the other components in the correct order.

- Utilities (src/util.rs): The utilities module typically contains a variety of helper functions and data structures that are used by the other components of the compiler.

In addition to the source files, a basic compiler may also include a set of test files that can be used to ensure that the different components are working correctly. These test files are typically located in a `test` directory and use a testing framework to run a series of tests against the compiler.

## If Statements

### In Rust

This is a if statement in rust:

```rust
fn main() {
let n = 5;

    if n < 0 {
        print!("{} is negative", n);
    } else if n > 0 {
        print!("{} is positive", n);
    } else {
        print!("{} is zero", n);
    }

    let big_n =
        if n < 10 && n > -10 {
            println!(", and is a small number, increase ten-fold");

            // This expression returns an `i32`.
            10 * n
        } else {
            println!(", and is a big number, halve the number");

            // This expression must return an `i32` as well.
            n / 2
            // TODO ^ Try suppressing this expression with a semicolon.
        };
    //   ^ Don't forget to put a semicolon here! All `let` bindings need it.

    println!("{} -> {}", n, big_n);

}
```

### In Python

```python
def main():
n = 5

    if n < 0:
        print("{} is negative".format(n))
    elif n > 0:
        print("{} is positive".format(n))
    else:
        print("{} is zero".format(n))

    if n < 10 and n > -10:
        print(", and is a small number, increase ten-fold")
        big_n = 10 * n
    else:
        print(", and is a big number, halve the number")
        big_n = n // 2

    print("{} -> {}".format(n, big_n))

main()
```

### In Pylar

```pylar
for x = 5, ifis > say "It's higher" rest "It's lower" now
```

### Comparison

#### Comparison points

There are a few key differences between Rust and Python that are worth noting:

In Rust, print! is used to print to the standard output stream, while in Python print is used.

In Rust, {} is used to placeholders for values that will be printed, while in Python {} is used for the same purpose.

In Rust, && is used for a logical and operator, while in Python and is used.

In Rust, / is the division operator, while in Python / is the floor division operator. To perform regular division, you can use / in Python 3 or / in Python 2.

In Rust, ; is used to end a statement, while in Python it is optional.

In Rust, let is used to bind a value to a variable, while in Python = is used for the same purpose.

#### Comparison table

| Language | Syntax                                                                                                                 |
| -------- | ---------------------------------------------------------------------------------------------------------------------- |
| Pylar    | for x = 5, ifis > say "It's higher" rest "It's lower"                                                                  |
| Rust     | if x > 5 {<br>&nbsp;&nbsp;&nbsp;println!("It's higher");<br>} else {<br>&nbsp;&nbsp;&nbsp;println!("It's lower");<br>} |
| Python   | if x > 5:<br>&nbsp;&nbsp;&nbsp;print("It's higher")<br>else:<br>&nbsp;&nbsp;&nbsp;print("It's lower")                  |

### Differences

There are a few key differences between the "ifis" statement in Pylar and the if statements in Rust and Python:

    Syntax: The syntax for the "ifis" statement in Pylar is significantly different from the if statements in Rust and Python. In Rust and Python, the condition is written first, followed by a block of code that is executed if the condition is true. In Pylar, the condition is written after the loop variable and the loop body, and the keyword "say" is used to specify the code that should be executed if the condition is true, while the keyword "rest" is used for the code that should be executed if the condition is false.

    Comparison operator: In Rust and Python, the > operator is used to test if a value is greater than another value. In Pylar, it is not clear from the example provided how comparison operators are written or used.

    Loop variable: In the example provided, Pylar appears to have a loop variable x that is assigned the value 5. In Rust and Python, there is no equivalent syntax for assigning a value to a loop variable before the loop begins.

    Loop body: In the example provided, Pylar appears to have a loop body that consists of a single "ifis" statement. In Rust and Python, the loop body is typically written as a block of code between curly braces or indentation.

    Output: In Rust and Python, the println! and print functions are used to print to the standard output stream, respectively. In Pylar, the keyword "say" is used to specify the output, but it is not clear how the output is actually printed.

### Table of differences

```
| Definition       | Python       | Rust       | Pylar*(1)       |
|-----------------|---------------|------------|-------------|
| Returns a value | `return`      | `return`   | `say`       |
| Prints output   | `print()`     | `println!()` | `say`     |
| If statement    | `if`          | `if`       | `ifis`      |
| Else statement  | `else`        | `else`     | `else`      |
| Elif statement  | `elif`        | `else if`  | `else`      |
| For loop        | `for`         | `for`      | `for`       |
| While loop      | `while`       | `while`    | `while`     |
| Break loop      | `break`       | `break`    | `bye`       |
| Continue loop   | `continue`    | `continue` | `rest`      |
| And operator    | `and`         | `&&`       | `and`       |
| Or operator     | `or`          | `||`       | `or`        |
| Not operator    | `not`         | `!`        | `not`       |
| Is operator     | `is`          | `==`       | `=`         |
| In operator     | `in`          | `in`       | `in`        |
| Equal operator  | `==`          | `==`       | `=`         |
| Assign operator | `=`           | `=`        | `=`         |
| Lambda function | `lambda`      | `lambda`   | `lambda`    |
| Function definition | `def`   | `fn`       | `fn`        |
| Class definition   | `class` | `struct`   | `class`     |
| Import statement   | `import` | `use`      | `import`    |
| Class definition       | `class`       | `struct`   | `class`     |
| Import statement       | `import`      | `use`      | `import`    |
| Global keyword         | `global`      | `global`   | `global`    |
| Nonlocal keyword       | `nonlocal`    | `nonlocal` | `nonlocal`  |
| And operator           | `and`         | `&&`       | `and`       |
| Or operator            | `or`          | `||`       | `or`        |
| Not operator           | `not`         | `!`        | `not`       |
| Is operator            | `is`          | `==`       | `=`         |
| In operator            | `in`          | `in`       | `in`        |
| Equal operator         | `==`          | `==`       | `=`         |
| Assign operator        | `=`           | `=`        | `=`         |
| Lambda function        | `lambda`      | `lambda`   | `lambda`    |
| Function definition    | `def`         | `fn`       | `fn`        |
```

[(\*1)](#Table-of-differences) Pylar is a work in progress and is not yet complete, it is subject to changes.

## Loops

### In Rust

```rust
fn main() {
    // This is a for loop that counts from 1 to 10
    for i in 1..11 {
        println!("{}", i);
    }

    // This is a while loop that counts from 1 to 10
    let mut i = 1;
    while i <= 10 {
        println!("{}", i);
        i += 1;
    }

    // This is a loop that counts from 1 to 10 using a loop label
    'outer: for i in 1..11 {
        'inner: for j in 1..11 {
            if i % 2 == 0 {
                break 'outer;
            } else if j % 2 == 0 {
                continue 'inner;
            }
            println!("i = {}, j = {}", i, j);
        }
    }
}
```

### In Python

```python

def main():
    # This is a for loop that counts from 1 to 10
    for i in range(1, 11):
        print(i)

    # This is a while loop that counts from 1 to 10
    i = 1
    while i <= 10:
        print(i)
        i += 1

    # This is a loop that counts from 1 to 10 using a loop label
    for i in range(1, 11):
        for j in range(1, 11):
            if i % 2 == 0:
                break
            elif j % 2 == 0:
                continue
            print("i = {}, j = {}".format(i, j))

main()
```

### In Pylar

```pylar
for i = 1 to 10, say i pass *
```

This is a for loop that counts from 1 to 10 and lend the permissions to read, write and execute only to the next instruction, the next line, one line per instruction, ended with pass to lend permissions to the next instruction or now to execute the whole code.

```pylar
for i = 1 to 10, say i now
```

This is a for loop that counts from 1 to 10 and ended with now to execute the whole code.

```pylar
for i = 1 to 10, say i pass *
```

This is a while loop that counts from 1 to 10, then it will pass the permissions to read, write and execute only to the next instruction, the next line, one line per instruction, ended with pass to lend permissions to the next instruction or now to execute the whole code.

```pylar
while i = 1 to 10, say i, +1 pass *
```

This is a while loop that counts from 1 to 10 and ended with now to execute the whole code.

```pylar
for i = 1 to 10, say i now
```

This is a loop that counts from 1 to 10 using a loop label and ended with pass \* to lend permissions to the next instruction or now to execute the whole code.

Becareful: As you may think in Pylar would be like this:

```not-pylar
for i = 1 to 10, for j = 1 to 10, pass * if i / 2 = 0, end, pass * else if j % 2 == 0, continue pass * say "i = {}, j = {}".format(i, j) pass *
```

But in Pylar would be like this:

```pylar
for i = 1 to 10 and j also, ifis / 2 = 0 bye, rest say "i = {}, j = {}".format(i, j) pass *
```

This loop iterates over the variables i and j simultaneously and prints their values in the format "i = {}, j = {}". If the value of i is divisible by 2, the loop breaks using bye. If the value of j is even, the loop continues to the next iteration using rest.

#### Comparison points

Here are the key points of comparison between loops in Rust, Python, and Pylar:

    Syntax: The syntax for loops in Rust, Python, and Pylar is quite different. In Rust, a for loop is written using the for keyword and a range, while a while loop is written using the while keyword and a condition. In Python, for and while loops are written using the for and while keywords, respectively, and the range function or a sequence of values is used to specify the loop iteration. In Pylar, for loops are written using the for keyword, a loop variable, and the keywords to and say or now, while while loops are written using the while keyword, a loop variable, and the keyword do.

    Loop labels: Loop labels are a feature in Rust that allow you to specify a label for a loop and use the break and continue keywords to control the flow of the loop. Python does not have a similar feature. Pylar does not appear to have a similar feature either.

    Break and continue: In Rust, the break and continue keywords can be used to control the flow of a loop. In Python, these keywords have the same function. In Pylar, the break keyword is replaced by the bye keyword, and the continue keyword is not present.

#### Comparison table

| Language | For Loop                                                            | While Loop                                                                                        | Loop Label                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | Break     | Continue   |
| -------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- | ---------- |
| Rust     | `for i in 1..11 {`<br>&nbsp;&nbsp;&nbsp;`println!("{}", i);`<br>`}` | `while i <= 10 {`<br>&nbsp;&nbsp;&nbsp;`println!("{}", i);`<br>&nbsp;&nbsp;&nbsp;`i += 1;`<br>`}` | `'outer: for i in 1..11 {`<br>&nbsp;&nbsp;&nbsp;`'inner: for j in 1..11 {`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if i % 2 == 0 {`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`break 'outer;`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`} else if j % 2 == 0 {`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`continue 'inner;`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`println!("i = {}, j = {}", i, j);`<br>&nbsp;&nbsp;&nbsp;`}`<br>`}` | Yes       | Yes        |
| Python   | `for i in range(1, 11):`<br>&nbsp;&nbsp;&nbsp;`print(i)`            | `i = 1`<br>`while i <= 10:`<br>&nbsp;&nbsp;&nbsp;`print(i)`<br>&nbsp;&nbsp;&nbsp;`i += 1`         | `for i in range(1, 11):`<br>&nbsp;&nbsp;&nbsp;`for j in range(1, 11):`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if i % 2 == 0:`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`break`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`elif j % 2 == 0:`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`continue`<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`print("i = {}, j = {}".format(i, j))`                                                                                                    | Yes       | Yes        |
| Pylar    | `for i = 1 to 10, say i pass *`                                     | `while i = 1 to 10, say i, +1 pass *`                                                             | `for i = 1 to 10 and j also, ifis / 2 = 0 bye, rest say "i = {}, j = {}".format(i, j) pass *`                                                                                                                                                                                                                                                                                                                                                                                                                  | Yes `bye` | Yes `rest` |

In Pylar, break is written as bye and continue is written as rest.

For example, the following Pylar code would print the numbers 1 to 10, except for the number 5:

```pylar
for i = 1 to 10, say i, ifis = 5 bye, now
```

And the following Pylar code would print only the even numbers from 1 to 10:

```pylar
for i = 1 to 10, ifis even say i now
```

## Semantics

#### Comparison points

Here is a comparison of key points between Rust, Python, and Pylar:

Pointer Access: Rust allows direct pointer access, while Python does not. Pylar also allows direct pointer access.

Data Types: Rust has static data types, while Python has dynamic data types. Pylar also has static data types.

Static/Dynamic: Rust is a static language, while Python is a dynamic language. Pylar is also a static language.

Memory Model: Rust uses manual memory management, while Python uses garbage collection. Pylar also uses manual memory management.

Concurrency: Rust uses a locking model for concurrency, while Python uses threading. Pylar also uses a locking model for concurrency.

Primitive Functions: Both Rust and Python have primitive functions built into the language. Pylar also has primitive functions built into the language.

Paradigm: Both Rust and Python are hybrid languages, combining elements of both functional and object-oriented programming. Pylar is also a hybrid language.

Interoperability: Both Rust and Python can interface with existing libraries and languages using C Foreign Function Interface (FFI). Pylar can also interface with existing libraries and languages using C FFI.

#### Comparison table

| Language | Pointer Access | Data Types | Static/Dynamic | Memory Model       | Concurrency | Primitive Functions | Paradigm | Interoperability |
| -------- | -------------- | ---------- | -------------- | ------------------ | ----------- | ------------------- | -------- | ---------------- |
| Rust     | Yes            | Static     | Static         | Manual             | Locking     | Yes                 | Hybrid   | C FFI            |
| Python   | No             | Dynamic    | Dynamic        | Garbage Collection | Threading   | Yes                 | Hybrid   | C FFI            |
| Pylar    | Yes            | Static     | Static         | Manual             | Locking     | Yes                 | Hybrid   | C FFI            |

## Algorithms

### Dijkstra's Algorithm

Dijkstra's algorithm is an algorithm for finding the shortest paths between nodes in a graph, which may represent, for example, road networks. It was conceived by computer scientist Edsger Dijkstra in 1956 and published three years later.

Here are some new keywords used in Pylar:

create: used to create a new variable or data structure, such as create distances = {} or create unvisited = graph.keys()

set: used to assign a value to a variable, such as set distances[node] = 0 or set unvisited.remove(current)

for each: used to iterate over a sequence, such as for each node in graph or for each neighbor, weight in graph[current]

if is: used to test for a specific value or condition, such as if is neighbor in unvisited or if is alt < distances[neighbor]

do: used to perform an action, such as do unvisited.remove(current) or do distances[neighbor] = alt, predecessors[neighbor] = current

```pylar
create distances, predecessors = {}, {}
for each node in graph, set distances[node] = 0 if is node = start else inf
create unvisited = graph.keys()
while is unvisited,
    create current = small(unvisited, key=lambda x: distances[x])
    do unvisited.remove(current)
    for each neighbor, weight in graph[current],
        if is neighbor in unvisited,
            create alt = distances[current] + weight
            if is alt < distances[neighbor], do distances[neighbor] = alt, predecessors[neighbor] = current
distances, predecessors
```
