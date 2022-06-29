# Lua - Ternary conditionals

Sometimes, it's easiest to organize your conditional statements by using what's known as a **_ternary_ statement** in cases where you'd like to store either one value or another based on a condition.

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

could be condensed to:

```lua
a = 3
b = 4

message = a < b and "a is less than b!" or "a is greater than or equal to b!"
print(message) --> a is less than b!
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