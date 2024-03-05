# Syntax for the project:

## regular expressions
`import re``
more info: https://www.w3schools.com/python/python_regex.asp

#### Metacharacters:

| character | meaning |
|--------- | -------- |
| []  | Set of characters |
| .  | Any character except newline |
| ^  | Starts with |
| $  | Ends with |
| *  | Zero or more occurrences |
| +  | One or more occurences |
| ? | Zero or one occurences |
| {n},{m,n} | Exactly n occurrences, m to n recurrences, respectively |
| \| | Exclusive or |

#### Special Sequences: 
(for \\b and \\B, put it at the beginning or end of the string depending on where you want to check for the characters)
| character | meaning |
| --------- | ------- |
| \\A | returns match if following characters are at beginning of string |
| \\b | returns match where specified characters are at beginning or end of word |
| \\B | returns match where specified characters are present, but NOT at beginning or end |
| \\d | returns match of digits 0-9 |
| \\D | returns match of non-digit characters |
| \\s | returns match of whitespace character |
| \\S | returns match of non-whitespace character |
| \\w | returns match of word character (letter, digit, underscore _) |
| \\W | returns match of non-word character|
| \\Z | returns match if preceding characers are at end of the string|


#### Other

Use backslashes \\ to escape one of the above metacharacters.

Sets: [01234] returns a match when any of the contents are present.

[0-4] and [a-f] return a match for any character within the ranges, preserving case.

[^0123] will return a match for everything except 0123

re.MatchObject.group() returns the matched subgroup. group(n) will return the nth group (1-indexed), with group(0) being the whole group and NOT the first subgroup.

backslash \\ can screw up python syntax, so if its causing issues turn the string to a raw string literal (prefix the string with r, so like r"\\n" will be two characters, "\\" and "n" instead of the newline.)

def get_title(name):
    title_search = re.search(' ([A-Za-z]+)\.', name)
    # If the title exists, extract and return it.
    if title_search:
        return title_search.group(1)
    return ""

detailed documention:

https://docs.python.org/3/library/re.html

## pandas syntax

df.apply() - applies a function along an axis of the dataframe (default 0). docs here https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.apply.html

df.loc[] - accesses a group of rows and columns by labels? usage unclear

## Issues I ran into / Things I learned

- the variable you assign a pandas series to is just a pointer, and I got these mixed up a lot. Takeaway: always know where each pointer is pointing, and use deep copies whenever you want a copy rather than a pointer

- Modularization is awesome - ensure that helper functions don't over-rely on state variables outside of themselves. If you're mutating an object, pass it in explicitly and return it. If you need more than one return, package them as a tuple and return that. 

- Question for the future - is the above mindset wasteful of compute and memory? passing in mutable objects and stuff explicitly is far easier for me to wrap my head around, but does it take more space or time than local functions modifying state variables around them?

- the "with" syntax in python will close files automatically

- Can use snyk.io to find new packages