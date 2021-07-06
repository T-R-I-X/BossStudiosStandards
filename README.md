# Code Standard

## Casing
| Occurrence                 | Casing               |
| -------------------------- | -------------------- |
| Services                   | PascalCase           |
| Modules/Classes            | PascalCase           |
| Constants                  | SCREAMING_SNAKE_CASE |
| Local Variables            | camelCase            |
| Functions                  | PascalCase           |
| Instance Variables         | PascalCase           |
| Private Instance Variables | _PascalCase          |
| Methods                    | PascalCase           |

---
## Code Layout/Template
```Lua
-- SERVICES

-- MODULES

-- CONSTANTS

-- VARIABLES

-- FUNCTIONS

-- BODY
```

---
## Example

```lua
--@@ Author Name

-- Services
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

--
local RandomPlayerModule = require(ReplicatedStorage:WaitForChild("Libs"):WaitForChild("FirstParty").PlayerModule)

--
local USE_PRINT = false

--
local startMessage = "[LOG]"

--
local Example = {
  Messages = {}
} do

  function Example.new(messageContent)
    messageContent = type(messageContent) == "string" and messageContent or error("Invalid data type for 'messageContent'; a string is expected") -- or assert() it doesn't matter
    
    Example.Messages[#Example.Messages + 1] = messageContent
  end
  
  function Example.PrintAll()
    
    for _, message in ipairs(Example.Messages)
      print(startMessage, message)
    end
    
  end

end
```
