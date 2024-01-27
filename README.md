Syntax:

##regular expressions
`import re``
more info: https://www.w3schools.com/python/python_regex.asp

Metacharacters:

| character | meaning |
|--------- | -------- |
| []  | Set of characters |
| .  | Any character except newline |
| ^  | Starts with |
| $  | Ends with |
| *  | Zero or more occurrences |
| +  | One or more occurences |
| ? | Zero or one occurences |
| {n} | Exactly n occurrences |
| \| | Exclusive or |

Special Sequences: 
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




Use backslashes \\ to escape one of the above metacharacters.

Sets: [01234] returns a match when any of the contents are present.

[0-4] and [a-f] return a match for any character within the ranges, preserving case.

[^0123] will return a match for everything except 0123

re.MatchObject.group() returns the matched subgroup. group(n) will return the nth group (1-indexed), with group(0) being the whole group and NOT the first subgroup.

def get_title(name):
    title_search = re.search(' ([A-Za-z]+)\.', name)
    # If the title exists, extract and return it.
    if title_search:
        return title_search.group(1)
    return ""

##pandas syntax

df.apply() - applies a function along an axis of the dataframe (default 0). docs here https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.apply.html


