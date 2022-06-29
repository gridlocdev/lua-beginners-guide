# Lua - Modules

Depending on the size and scope of your computer program, it could be a great idea to compartmentalize code into smaller, more re-usable chunks.

In Lua, you typically spread these chunks out into separate files called **modules**.

## Creating your own Module

Modules are any Lua files that have something that it exports. Everything in a Lua file that is globally scoped can be accessed by other files that import it as a module.

To import a module, you use the `require()` function, and supply the name of a Lua file (without the `.lua` file extension) that exists in the same directory.

```lua
-- File: talker.lua
local message = "Hello!"

function sayHello()
    print(message)
end

------------------------------------

-- File: main.lua

require "talker"

sayHello()
```

> In the above example, the globally scoped function `sayHello()` is able to be accessed by the file that imports the module. But, since the variable `message` is _locally_ scoped, it cannot be explicitly used in the file that imports the `mod.lua` file.

Although the above example works, common practice for modules is to export a _table_ with all of the exported functions and variables tied to it. This helps make the code easier to read and lets programmers more easily know where module variables and functions are coming from as they use the module.

```lua
-- File: tambre.lua
local tambre = {}

function tambre.shout(message)
    local shoutyMessage = string.upper(message)
    print(shoutyMessage)
end

function tambre.whisper(message)
    local lowercaseMessage = string.lower(message)
    local quietMessage = string.format("(%s)", lowercaseMessage)
    print(quietMessage)
end

return tambre

------------------------------------

-- File: main.lua

local tambre = require "tambre"

tambre.shout("Hello,")
tambre.whisper("World")
```

## Using Modules in Packages from the Internet

To save time, effort, and reduce complexity, it's also common practice to use chunks of code that other people/teams have written. These authors put chunks of code on the internet in the form of **packages** for other people to use!

> Note: When using a package from the internet, make sure that you trust the author(s) and/or have a general understanding of what the code you are downloading is doing! 

To use a package, rather than downloading the files from the internet directly, most programming ecosystems have a centralized entity that stores packages called a **package manager**. For Lua, the most popular package manager is [LuaRocks](https://luarocks.org/). 

To get started, install the LuaRocks package manager using the installation instructions provided on their website!

From there, once you've installed a package, you can `require()` it just like any other local modules.
