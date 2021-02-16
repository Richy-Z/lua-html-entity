# lua-html-entity
lua-html-entity is a lightweight library which can translate HTML Entity Numbers in a given string to a plain string (and the other way round too).
## Features
- Conversion of strings containing HTML Entity Numbers to a normal string
- Conversion of normal strings to strings formatted with HTML Entity Numbers
- More features will probably come soon

## Installation
```sh
lit install iiRichyDev/lua-html-entity
```

## Documentation

### convert(<method (required)>, <string (required)>, <custom-entity-table (optional)>)
This command converts strings to / from strings formatted with HTML Entity Numbers.
#### Parameters
| Parameter | Value | Type | Description |
| ------ | ------ | ------ | ------ |
| method | `to_html` | String | The required argument which tells the converter to convert to HTML |
| method | `from_html` | String | The required argument which tells the converter to convert from HTML |
| string | * (User Input) | String | The required argument which tells the converter what to convert |
| custom-entity-table | * (User Input) | Lua Table | The optional argument which tells the converter how to convert strings. If left empty, the default entity table will be used. |

## Examples

```lua
local html_entity = require("lua-html-entity")

local convert_to_html_example = html_entity:convert("to_html", [[Don't, "Donut head", ˆˆˆˆˆ etc ♥♥♥♥♥]])
print(convert_to_html_example)
-- Output: Don&#8217;t, &#8220;Donut head&#8220;, &#710;&#710;&#710;&#710;&#710; etc &#9830;&#9830;&#9830;&#9830;&#9830;

local convert_from_html_example = html_entity:convert("from_html", "Don&#8217;t, &#8220;Donut head&#8220;, &#710;&#710;&#710;&#710;&#710; etc &#9830;&#9830;&#9830;&#9830;&#9830;")
print(convert_from_html_example)
-- Output: Don't, "Donut head", ^^^^^ etc ♥♥♥♥♥
```
