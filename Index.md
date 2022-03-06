# Welcome to Lua

![lua-logo]()

I've prepared this guide because I wasn't able to find a written guide on Lua's basics as I was learning, and figured it would be useful to others as well.

- [Welcome to Lua](#welcome-to-lua)
  - [Introduction to Lua](#introduction-to-lua)
    - [Pros](#pros)
    - [Cons](#cons)
  - [How to get started programming with Lua](#how-to-get-started-programming-with-lua)
  - [1 - Data Types](#1---data-types)
    - [Strings](#strings)
    - [Numbers](#numbers)
    - [Booleans](#booleans)
    - [Nil](#nil)
    - [Tables](#tables)
  - [2 - Operators](#2---operators)
    - [Arithmetic](#arithmetic)
    - [Relational](#relational)

## Introduction to Lua

Lua is a fast, simple, and portable programming language best (and most commonly) used for video games, embedded devices, and as modular libraries in other programs.

### Pros

- Fast
- Lightweight
- Easy to integrate into other programs

### Cons

- Limited error handling support

## How to get started programming with Lua

For programming, you will need to use a code editor application to create your code, as well as have the compiler for your computer to know how to run Lua code.

The easiest way to get started without installing anything is to use an in-browser editor, such as [Replit](https://replit.com/languages/lua).

Or, if you would like to run things locally on your computer you will need:

- A code editor (such as [Visual Studio Code](https://code.visualstudio.com) with a [debugging extension](https://marketplace.visualstudio.com/items?itemName=sumneko.lua) or [ZeroBrane Studio](https://studio.zerobrane.com/download?not-this-time)).
- An installed version of the [Lua language runtime](https://www.lua.org/download.html)

> Note: If you do run into any issues during this tutorial or while installing the pre-requisite software, try typing your exact question into a search engine like Google or DuckDuckGo and see what comes up!
>
> Anecdotally, about half of my time spent while working in computer programming involves finding information on the internet. It's a great skill to build up, as it's useful for finding out things you don't know, or things that you've just forgotten over time. (Which coincidentally, happens a lot when working with computers and software in general!)

## 1 - Data Types

There are 5 basic types of data in Lua:

| Type | Example | Description |
| --- | --- | --- |
| string | `Hello` | Text |
| number | `123` | Contains either an integer or a decimal number, as well as positive or negative signs |
| boolean | `false` | True or False |
| nil | `nil` | The absence of a value, often known as `null` in other languages |
 table | `{key1 = value1, key2 = value2, ...}` <br> or `{value1, value2, ...}` | Contains a collection of related values, accessible by their key or by their position in the list |

A **variable** in computer programming is used to store information inside a computer program. Each value that you can give to a variable has a **data type**, which is a term that describes what type of data is stored into a variable.

Lua is a _dynamically typed_ programming language, meaning you don't need to explicitly say what type of data a variable should contain and the Lua compiler will interpret the type for you.

### Strings

Strings are used when you want to represent text. Text data is generally used when you want to represent a more abstract form of information intended for humans to read.

> In the below example, the `print()` function outputs the result to the console.

```lua
-- Declares a variable `message` with a string
message = "Hello"

print(message) -- Output: 'Hello'
```

Sometimes, there's a need to get fancy with your strings. If you would like to insert another value inside a string, you would use _string interpolation_. In Lua, that is done with two periods: `..`

```lua
name = "Bob"
message = "Hello, "..name.."!"

print(message) -- Output: 'Hello, Bob!'
```

### Numbers

Numbers are used by computer programs to estimate something that has a numerical value to it. This can be used for doing something in the code X number of times, describing an amount of money, a pixel width/position of something on the screen, etc;

> The below example draws a filled circle onto the screen in the PICO-8 game engine.

```lua
x = 64
y = 64
radius = 32
color = 8 -- 8 represents `red` in PICO-8's color pallette

circfill(x, y, radius, color)
```

### Booleans

Booleans are simply a type that shows either a `true` or a `false`. These types are heavily relied on for conditional statements in program logic, meaning things that should happen only if something else is true or false.

> In the below example, since the variable `shouldPrintMessage` is set to false, the result will not print.

```lua
shouldPrintMessage = false 

if shouldPrintMessage == true then
    print("Mitochondria is the powerhouse of the cell.")
end
```

### Nil

The value type `nil` is an empty value that occurs when the program attempts to access something that does not exist. Typically, it's something you want to avoid since having a something with nothing in it isn't very useful.

> In the below example, the `print()` function is attempting to print the value of a variable that hasn't been created yet. So, it will be empty and contain a `nil`.

```lua
print(notARealVariable) -- Output: nil
```

### Tables

Tables are used to store collections of related data. Collecting data into a singular entity makes it significantly easier to organize as well as perform tasks on such as creating, reading, updating, or deleting data.

In Lua, Tables are the only data collection type, and are quite flexible in their usage.

> In the below example, the first item in the table list is printed to the console. Notably, Lua starts indexes at 1 instead of 0 like most other languages.

```lua
snacks = { "Fruit", "Popcorn", "Chocolate Cake" }

-- Adding a new item to the list
table.insert(snacks, "Brotwurst")

-- Reading an item from the list
print(snacks[1])

-- Updating an item in the list
snacks[4] = "Potato Chips"

-- Removing the third item from the list
table.remove(snacks, 3)
```

You can also create key-value pairs in tables. Key-value pairs are used for when it would be useful to have self-describing data.

```lua
superman = {
    firstName = "Clark",
    lastName = "Kent",
    age = 25,
    canFly = true,
    allergies = { "Kryptonite" }
}

print(superman.firstName) -- Output: Clark
```

## 2 - Operators

Operators are symbols that represent a type of action between two or more things. This can be something like comparing two values, doing arithmetic operations on them, or control flow.

### Arithmetic

Lua's arithmetic operators follow the standard set found in most other programming languages:

| Operation | Symbol |
| --- | --- |
| Add | + |
| Subtract | - |
| Multiply | * |
| Divide | / |
| Exponents | ^ |
| Remainder (Modulo) | % |

> In the below example, each arithmetic operation has two inputs and one output. (The do-end blocks are)

```lua
a = 50
b = 4

-- Addition
print(a + b) -- Output: 54

-- Subtraction
print(a - b) -- Output: 46

-- Multiplication
print(a * b) -- Output: 200

-- Division
print(a / b) -- Output: 12.5

-- Exponents
print(a^b) -- Output: 6250000.0

-- Remainder (Modulo)
-- The 'Modulo' operator divides the two numbers, then outputs the remainder
print(a % b) -- Output: 2
```

### Relational

A common thing to do in computer programs is compare two values. This can be something like checking if two values are equal, or if numerical values are greater or less than one another.

```lua
print(3 == 5) -- (Equal to) --> false
print(3 ~= 5) -- (Not equal to) --> true
print(3 > 5) -- (Greater than) --> false
print(3 >= 3) -- (Greater than or equal to) --> true
print(3 < 5) -- (Less than) --> false
print(3 <= 5) -- (Less than or equal to) --> true
```

Each of the other data types are frequently compared as well using the equal to (`==`) and not equal to (`~=`) operators.

```lua
name = "James"
isCool = true

print(name == "James") --> true
print(isCool == true) --> true
print(newVariable ~= nil) --> false
```

