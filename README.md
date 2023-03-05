
# Regex Tutorial: Matching a Hex Value

Regex or regular expression, is a sequence of characters that define a search pattern. It can be used for searching, matching, and manipulating text data. Regex patterns can include a combination of characters, symbols and modifiers.
Regular expressions are often used to search for patterns in large amounts of data, validate input data, extract information from text, or replace text with new content.

## Summary

The following is the regular espression for matching a hex value (hexadecimal color value) that we will be studying in this tutorial:
````
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
````
Hex values or Hexadecimal color values tell the display how much of a color to show. The values are commonly used in computer programming and digital design, in relation to colors, where each color is represented as a combination of red, green, and blue values in hex format. 

A practical example of a hexadecimal regex in use would be to validate input fields that require a hexadecimal color code. By using a hexadecimal regex, we can ensure that users only input valid hexadecimal color codes, which can prevent errors and inconsistencies in the display of colors on a website or application.

Hex values: 
* Generally start with the `#` character.
* Contain a combination of letters `(a-f)` and/or a combination of numbers form `0-9` 
* Can be `{3}` or `{6}` digits long. (The 3-digit hex code is a shorthand for some 6-digit hex codes).

For example,
````
Color	       RGB	        Hex Color Code
Black       (0, 0, 0)           #000000
Blue        (0, 0, 255)         #0000ff
Gray        (128, 128, 128)     #808080
Green       (0, 128, 0)         #008000
Purple      (128, 0, 128)       #800080
Red         (255, 0, 0)         #ff0000
White       (255, 255, 255)     #ffffff
````

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

### Anchors
````
Anchors dont match any character. They match a position before, after, or between characters. 
This regex is enclosed by anchors on both ends `^` and `$` after and before the `/` symbol,
indicating that is a literal notation. 
````


/`^`#?([a-f0-9]{6}|[a-f0-9]{3})`$`/ 


- The caret `^` is the starting anchor, and denotes a string that begins with the character that follow it, in this example the string begins with a `#`.

- The dollar sign `$` indicates the end of a string.

### Quantifiers

````
Quantifiers are special symbols, characters or expressions that specify how many times a particular 
character or group of characters should be repeated in a string.
````
/^#`?`([a-f0-9]`{6}`|[a-f0-9]`{3}`)$/

- The question mark `?` indicates that the element is optional, matching 0 or 1 time.
- The `{n}` indicates a quantity, either a single number or a range of numbers.
- The `{n}` quantifiers in our regex indicate that the hex values are exactly 6 digits or exactly 3 digits long
`{6}`, `{3}`.


Note:  #012345 and #012 are both valid hex values.


### OR Operator
````
The OR operator, symbolized by a vertical line `|` means exactly what is sounds like "or". The "or" operator 
indicates that it could either of the components that we are separating with the `|`.
````

/^#?([a-f0-9]{6}`|`[a-f0-9]{3})$/ 

Here we see two components separated by `|` implying that our hex value could be either `{6}` "or" `{3}` characters long.


### Character Classes
````
Character clases are components that defines a set of characters. 
````

/^#?(`[a-f0-9]`{6}|`[a-f0-9]{3}`)$/ 

In our example, character classes are inside square brackets `[]`. `[a-f0-9]` and `[a-f0-9]` here we are trying to match the same values. It would try to find lowercase letters from a to f, and digits between 0 to 9.

Hex values like #abc012, #bcd253, #fff111, and #bcbaaa, #000000 are all good match. 

### Bracket Expressions
````
Matches any character in the square brackets `[]`. We will commonly see a hyphen `-` between alphanumeric characters 
only (letters and numbers).
````

- `[a-f]` here the string can have ANY lowercase letter between a-f, it will ONLY looks for lowercase characters. 
Now, if we want to add uppercase letters we would need to write the expression like this [a-fA-F].


### Greedy and Lazy Match

A greedy match would try to match an element as "many" time as possible. Lazy match would try to match an element as "few"
times as possible.

/^#`?`([a-f0-9]{6}|[a-f0-9]{3})$/ 

Here we have `?` known as lazy quatifier. It would match the the pattern zero or one time. 

In this example, the quantifier `?` tells us that the `#` character is optional. 
Hex color value #ffffff and ffffff are both valid.

## Author

Thank you for reading! 
I'm Jennifer Scherschligt, I'm a full stack developer student at the University of Oregon. 

My first GIST: [pherpat](https://gist.github.com/pherpat/17c7e791a1b971614eb692f8cb804b70)
