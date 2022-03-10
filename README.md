# Welcome to Lua

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/c/cf/Lua-Logo.svg" width="300px" alt="Lua logo"/> 
</p>  

This is a beginner-friendly guide to the Lua programming language. This guide is intended for people that are completely new to programming as well as folks that already might have experience with other programming languages (such as Python, JavaScript, or C#).

I wasn't able to find a written and easy-to-understand tutorial anywhere else, so I've gathered all of the most fundamental concepts here in the case it might be useful to you as well.

- [Welcome to Lua](#welcome-to-lua)
  - [Introduction to Lua](#introduction-to-lua)
    - [Pros](#pros)
    - [Cons](#cons)
  - [What can I do with Lua?](#what-can-i-do-with-lua)
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
    - [Lexical - Comparisons](#lexical---comparisons)
  - [3 - Conditionals](#3---conditionals)
  - [4 - Ternary conditionals](#4---ternary-conditionals)
    - [How does the Ternary operator work?](#how-does-the-ternary-operator-work)
  - [5 - Loops](#5---loops)
    - [For (Numeric)](#for-numeric)
    - [For (Generic)](#for-generic)
    - [Repeat Until](#repeat-until)
    - [While](#while)
  - [6 - Functions](#6---functions)
    - [Both Input + Output](#both-input--output)
    - [Neither](#neither)
    - [Only Input](#only-input)
    - [Only Output](#only-output)
    - [Alternative Function Syntax](#alternative-function-syntax)
  - [7 - Scoping](#7---scoping)
  - [8 - Modules](#8---modules)

## Introduction to Lua

Lua is a fast, simple, and portable programming language best (and most commonly) used for video games, embedded devices, and as modular libraries in other programs.

### Pros

- Fast execution
- Lightweight
- Easy to integrate into other programs

### Cons

- Limited error handling support due to its small size

## What can I do with Lua?

Lua is quite a versatile programming language. But, it's mostly best at things like:

| Use Case | Description | Examples |
| --- | --- | --- |
| Embedded programming | Writing code to run on IoT or small computing devices | Raspberry Pi |
| Video game programming | Writing video game logic | PICO-8, LOVE2D, Defold, ROBLOX, Godot |
| Network programming | Writing fast and small programs for computer networking | CISCO Systems, nmap, ModSecurity |
| Complex config files | Writing configuration files that require lots of complexity and advanced features | Neovim config |
| Cross-language libraries | Writing flexible and interoperable libraries that can work with multiple programming languages | NLua (.NET / C#) |

## How to get started programming with Lua

For programming, you will need to use a code editor application to create your code, as well as have the compiler for your computer to know how to run Lua code.

The easiest way to get started without installing anything is to use an in-browser editor, such as [Replit](https://replit.com/languages/lua).

Or, if you would like to run things locally on your computer you will need:

- A code editor (such as [Visual Studio Code](https://code.visualstudio.com) with a [debugging extension](https://marketplace.visualstudio.com/items?itemName=sumneko.lua) or [ZeroBrane Studio](https://studio.zerobrane.com/download?not-this-time)).
- An installed version of the [Lua language runtime](https://www.lua.org/download.html)

> Note: If you do run into any issues during this tutorial or while installing the pre-requisite software, try typing your exact question into a search engine like Google or DuckDuckGo and see what comes up!
>
> Troubleshooting issues by looking up information online is one of the main portions of time spent computer programming; there's no sense wracking your brain to try and remember something specific when a refresher is usually just a moderately-crafted Google search away. It's a great skill to build up as it's useful for finding out things you don't know or things that you've just forgotten over time!

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

print(message) --> 'Hello'
```

Sometimes, there's a need to get fancy with your strings. If you would like to insert another value inside a string, you would use _string interpolation_. In Lua, that is done with two periods: `..`

```lua
name = "Bob"
message = "Hello, "..name.."!"

print(message) --> 'Hello, Bob!'
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
print(notARealVariable) --> nil
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

print(superman.firstName) --> Clark
print(superman.canFly) --> true
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

```lua
a = 50
b = 4

-- Addition
print(a + b) --> 54

-- Subtraction
print(a - b) --> 46

-- Multiplication
print(a * b) --> 200

-- Division
print(a / b) --> 12.5

-- Exponents
print(a^b) --> 6250000.0

-- Remainder (Modulo)
-- The 'Modulo' operator divides the two numbers, then outputs the remainder
print(a % b) --> 2
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

### Lexical - Comparisons

The word _lexical_ means something that relates to the vocabulary of a language. In the case of programming, it typically refers to a written word that has a meaning in the program.

The following words function as _operators_ in Lua:

- and
- or
- not

The `and` operator checks if both conditions are true. If they are, it returns the appropriate result.

```lua
name = "James"
isCool = true

print(name == "James" and isCool == false) --> false
```

Conversely, if you would like to check if either one of the conditions is true, you would use `or`:

```lua
name = "James"
isCool = true

print(name == "James" or isCool == false) --> true
```

When you would like to check for the _opposite_ of a boolean result, you would use the `not` operator.

```lua
isCool = true

print(not isCool) --> false
```

## 3 - Conditionals

Sometimes you would only like to execute certain logic in certain cases. To do this, you would use a _conditional_ statement like `if`.

```lua
a = 3
b = 4

if (a < b) then
    print("a is less than b!")
end
```

But what if you wanted to print something in the cases where `a` was _greater than_ or _equal to_ `b`? In that case, you would use an `else`.

```lua
a = 3
b = 4

if (a < b) then
    print("a is less than b!")
else
    print("a is greater than or equal to b!")
end
```

Now, let's say you wanted to know exactly when the two values were equal. To do that, you would add an `elseif` in the middle.

```lua
a = 3
b = 4

if (a < b) then
    print("a is less than b!")
elseif (a == b)
    print("a is equal to b!")
else
    print("a is greater than b!")
end
```

## 4 - Ternary conditionals

Sometimes, it's easiest to organize your conditional statements by using what's known as a **_ternary_ statement** in cases where you'd like to return either one value or another based on a condition.

The word **ternary** means "Composed of three parts"; and a ternary _statement_ is a conditional that is composed of three parts:

1. A condition
2. A result to return if the condition is true
3. A result to return if the condition is false

For example, the following code without a ternary:

```lua
a = 3
b = 4

if (a < b) then
    print("a is less than b!")
else
    print("a is greater than or equal to b!")
end
```

could be simplified to:

```lua
a = 3
b = 4

message = a < b and "a is less than b!" or "a is greater than or equal to b!"
print(message)
```

### How does the Ternary operator work?

> Feel free to skip this part if you were satisfied by the above explanation. But, if you're curious on the `and` and `or` operator feel free to read on to learn more!

But _what exactly is going on here?_  That ternary statement kind of looks funky. Well, in Lua, the `and` and `or` operators also double up as a second type of operator that lets you split the type of output you receive.

Each value in a Lua program under the hood (even though they don't seem to) is considered as either `true` or `false`. Every value evaluates to `true`, except for `nil` and `false`.

Ternary (and other statements using `and` and `or`) are evaluated from left to right:

- `and` continues forward if everything to the left is `true`
- `or` continues forward if everything to the left is `false`
If the evaluator can't continue forward any further, it returns the value from where it's at.

In the below example, the combination of a statement `and` then a value will return the value since anything that isn't `false` or `nil` is **always** true.

```lua
a = 3
b = 4
conditionalMessage = a < b and "a is less than b!"

print(conditionalMessage) --> "a is less than b!"
```

Conversely, `or` does the opposite:

```lua
a = 3
b = 4
conditionalMessage = a < b or "a is less than b!"

print(conditionalMessage) --> true
```

> The `or` example returns `true` as the result of `a < b`.

## 5 - Loops

When you'd like to run the same chunk of code repeatedly, you would use a **loop** statement.

There's a few different flavors each with their own use cases.

- For
- Foreach
- While
- Repeat until

### For (Numeric)

When you know the exact number of times to do something repeatedly, you would use a **numeric** for loop.

```lua
for i = 1, 10 do
    print("This loop has run "..i.." times!")
end
```

For loops in Lua consist of a few parts, each separated by a comma (`,`).

1. The first argument (usually named `i`, short-form for _index_) is a variable that represents the number that the loop starts from.
2. The second argument is the end number that the loop index should be able to reach. When the loop index `i` is about to pass this number, the loop stops and the code moves on to the next statement after the loop.
3. (Optional) There is also an optional third argument that represents a number to be added to the index _before_ each time the loop should repeat. By default, the loop adds 1 to the index.

Here is an example with the third argument included:

```lua
-- Increments by 2 each iteration
for i = 1, 10, 2 do
    print("The index is: "..i)
end

-- Increments by -1 (subtracts) each iteration
for i = 10, 1, -1 do
    print("The index is: "..i)
end
```

> Notice that in the second example with subtraction, the loop has to start from a higher number and count down to the lower number.

### For (Generic)

When you would like to loop over elements in a table, you could use a **generic** for loop.

Generic loops can be used for tables that have _named_ keys

> `{ key1 = value1, key2 = value2, ... }`

as well as when a table does not have named keys

> `{ value1, value2, ...}`

Because of this, Lua provides two (virtually identical) functions. Each of these is optimized for those use cases:

- `ipairs()` - Loop over a table with no keys (index-valued keys), for when you care about the order the items are processed
- `pairs()` - Loop over a table with keys, does not preserve the same order

When a table does not contain named keys and just contains values, the `key` value is just the index in the table (e.g. 1, 2, 3).

```lua
snacks = { "Fruit", "Popcorn", "Chocolate Cake" }

for index, value in ipairs(snacks) do
    print(index, value)
end

-- The above outputs:
--  1       Fruit
--  2       Popcorn
--  3       Chocolate Cake
```

You also don't technically need to write out the first argument if you don't plan on using the index. A common code convention is to use an underscore (`_`) known as a _discard_ variable.

```lua
snacks = { "Fruit", "Popcorn", "Chocolate Cake" }

for _, value in ipairs(snacks) do
    print(value)
end

-- The above outputs:
--  Fruit
--  Popcorn
--  Chocolate Cake
```

To loop over a table that contains keys, you would do so in the same way, but just using the `pairs()` function instead:

```lua
superman = {
    firstName = "Clark",
    lastName = "Kent",
    age = 25,
    canFly = true,
    allergies = { "Kryptonite" }
}

for key, value in pairs(superman) do
    print(key, value)
end

-- The above outputs:
--  canFly          true
--  lastName        Kent
--  allergies       table: 0x55b668f326b0
--  firstName       Clark
--  age             25
```

### Repeat Until

The **repeat until** loop is used when you would like to do something over and over until a condition is true.

> Remember: If your condition never becomes false, your code will run in an **infinite loop**. So, make sure that your condition will eventually return true.

The key difference between this and a `while` loop is what happens on their first round.

- Use a `while` loop if you would like to check your condition **before** running the code on the first round.
- Use a `repeat until` loop if you would like to check your condition **after** running the code on the first round.

A very common use case for these type of loops is to check user input, where you would like to only proceed once you've verified the user has typed in the correct thing.

```lua
print("What is 2 + 2?")
answer = "4"

repeat
    input = io.read() -- Read the user's keyboard input
    if input ~= answer then
        print("Wrong answer, try again!")
    end
until input == answer

print("Congrats, that's right!")
```

> The above example will ask the user to keep guessing until they guess the number `4` into the console input.

Hey but wait a minute, in this game it repeats forever until they guess the correct number. What if we wanted to let the user manually exit the program?

To do that, we would use the `break` keyword, which allows _breaking_ out of a loop.

> In the below example, if the user types in "quit", the `break` statement will exit out of the loop it is in and not prompt the user for another answer.

```lua
print("What is 30 + 12?")
answer = "42"

print("(Type 'quit' to exit if this is too hard)")

repeat
    input = io.read() -- Read the user's keyboard input
    if input == "quit" then 
        break -- Exits out of the `repeat until` loop
    elseif input ~= answer then
        print("Wrong answer, try again!")
    else
        print("Congrats, that's right!")
    end
until input == answer
```

> Syntactically, the `repeat until` loop is Lua's named flavor of the `do while` loop commonly found in other programming languages.

### While

**While** loops are used when you would like to do something over and over until a condition is true, but check the condition first before running it for the first time.

The key difference between this and a `repeat until` loop is what happens on their first round.

- Use a `while` loop if you would like to check your condition **before** running the code on the first round.
- Use a `repeat until` loop if you would like to check your condition **after** running the code on the first round.

```lua
colors = {}
print("What are your two favorite colors?")

-- Note: `#` in `#colors` is for the length of a table with non-named keys.
while #colors < 2 do
    print("Colors entered: "..#colors)
    input = io.read()
    table.insert(colors, input)
end

print(colors[1].." and "..colors[2].." are awesome! I wonder what they would look like together.")
```

## 6 - Functions

**Functions** are used when you would like to re-use the same chunk of code in more than one place. This helps keep code readable and easier to manage.

Functions can have two parts, an _input_ and an _output_. Depending on what type of logic you have, you may have either none of these, both of these, or just one of the two.

- **input** - A set of one or more values that help determine what the function should do or output (also known as "arguments" or "parameters")
- **output** - The resulting value(s) of the action taken by the function.

To output something from a function, you would use the `return` keyword, followed by the one or more values you would like to return. After it gets returned, it is passed back to whichever line of code called the function.

### Both Input + Output

```lua
function sum(number1, number2)
    return number1 + number2
end

print(sum(3, 3))
print(sum(33, 26))
print(sum(335, 834))
```

> In the above example, the `sum()` function takes two numbers to add as parameters, then outputs the sum as a result. The result then is passed to `print()`, which then prints it to the console.

### Neither

```lua
function printCurrentTime()
    print(os.date())
end

printCurrentTime()
```

> In the above example, the `printCurrentTime()` function prints the computer's date and time to the console.

### Only Input

```lua
function printGreeting(name)
    print("Hello there, "..name.."!")
end

printGreeting("John")
printGreeting("Mervis")
```

> In the above example, the `printGreeting()` function takes a name and prints a greeting message to the console.

### Only Output

```lua
function getDayOfWeek()
    return os.date("%A")
end

dayOfWeek = getDayOfWeek()

if dayOfWeek == "Wednesday" then
    print("It is Wednesday, my dudes.")
    print("AAAAAAAAAAAAAAAAAAAAAAAAA")
else 
    print("Today is "..dayOfWeek)
end
```

### Alternative Function Syntax

If your function happens to take a **string** as a parameter, you can also omit the parenthesis `()` and call your function like this:

```lua
    function printGreeting(name)
    print("Hello there, "..name.."!")
end

printGreeting "John" --> Hello there, John!
printGreeting "Mervis" --> Hello there, Mervis!
```

## 7 - Scoping

In simple programs like the examples mentioned previously, limiting the access of which variables/functions can see other variables/functions is not too important, as most of the program executes within the same scope.

But, as your project grows in complexity with more features and starts branching to multiple files, it becomes _drastically_ more important to make sure that you limit things from accessing things it should probably not need to.

This prevents quite a bit of headache when debugging, as you can more easily track where your functions are being called, as well as where each of your variables are being set / read from.

There are two types of scope in Lua, **global** scope and **local** scope.

- Global scope: Accessible to be read from and written to anywhere in the current file, as well as in any [modules](#8---modules) that are imported.
- `local` scope: Only accessible from within the parent code-block (such as a function, conditional, loop, etc; or just within the file if the variable/function is not located within any other blocks of code)

> A good rule of thumb is just to create everything under `local` scope, and then when you specifically have a use case for using global values you would create those as necessary. 

To locally scope your variables/functions, you would use the `local` keyword.

```lua
local names = {
    "Jimmy",
    "Johnny",
    "Fred"
}

local function printInUpperCase(text)
    local upperCaseName = string.upper(text)
    print(upperCaseName)
end

printInUpperCase("Hello friends:")

for _, value in ipairs(names) do
    printInUpperCase(value)
end
```

> Note: Since function and loop parameters would _always_ be local, you do not need to explicitly state those as local as the Lua interpreter will do that for you.

## 8 - Modules