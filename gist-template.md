# Title (replace with your title)

Welcome to RegEx Tutorial - Watching an email address.  In this tutorial, we wil navigate how to use regular expressions to validate and match email addresses.  


## Summary

What exactly is RegEx?
 A regex, short for regular expression, is a sequence of characters that defines a specific search pattern. In this tutorial, we'll focus on understanding and using a regular expression to match email addresses.

 The regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` is used to match email addresses.



## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components
RegEx components is a specific part or an element of a regular expression. Regular expressions consist of various components that havce distinct funcationality and purposes. Eac of these components contributes defining the search pattern that the regular expression represents. 

Each of the followng components will be defined below:

### Anchors
Specify the location. For example: 
('^') the start
^Hello
In this example:

^ is the anchor.
Hello is the text pattern to match.
The ^ anchor indicates the start of a line. Therefore, the regular expression ^Hello will match any string that starts with "Hello" at the beginning of a line.

Here are some examples of strings that would match this regular expression:

"Hello, world!"
"Hello there"
"Hello"
"Hello123"
But the following strings would not match:

"Hi, Hello"
"World, Hello"
"Say Hello"
"Goodbye, Hello"
In these cases, the "Hello" does not occur at the beginning of a line, so the anchor ^ fails to match.

('$') the end
world$
In this example:

$ is the anchor.
world is the text pattern to match.
The $ anchor indicates the end of a line or string. Therefore, the regular expression world$ will match any string that ends with "world" at the end of a line or at the end of the string.

Here are some examples of strings that would match this regular expression:

"Hello, world"
"Goodbye, world"
"This is the end of the world"
"world"
But the following strings would not match:

"world, hello"
"world is big"
"world war"
"world war ii"
In these cases, the "world" does not occur at the end of a line or at the end of the string, so the anchor $ fails to match.


### Quantifiers
A quantifier in regular expressions specifies the quantity or repetition of a character or group. Quantifiers allow you to define how many times a character, group, or character class should be matched. Here's the general syntax for some common quantifiers:

*: Matches zero or more occurrences of the preceding character or group.
+: Matches one or more occurrences of the preceding character or group.
?: Matches zero or one occurrence of the preceding character or group.
{n}: Matches exactly n occurrences of the preceding character or group.
{n,}: Matches n or more occurrences of the preceding character or group.
{n,m}: Matches between n and m occurrences of the preceding character or group.

# Here are some examples of how quantifiers work.
# 1.
a*: Matches zero or more occurrences of  the letter "a".
Matches: "", "a", "aa", "aaa", ...
Does not match: "b", "ab", "ba", ... 

# 2.
b+: Matches one or more occurrences of the letter "b".
Matches: "b", "bb", "bbb", ...
Does not match: "", "a", "ab", ...

# 3
f{1,3}: Matches between one and three occurrences of the letter "f".
Matches: "f", "ff", "fff"
Does not match: "", "ffff", "fffff", ...

### OR Operator
The OR operator in regular expressions allows you to specify alternative matches for a pattern. It's represented by the | character and is useful when you want to match one pattern or another. Here's the syntax:
            pattern1|patern2

This means that the regular expression will match either pattern1 or pattern2. If either of the patterns is found in the text being searched, the match is successful.

Here are two examples of how the OR operator works:
                cat|dog
    -Matches: "cat","dog"
    -Does NOT match: "bird","fish","catdog"

                colo(u)r
    -Matches: "color","colour"
    -Does NOT match: "collar","coloured"
In the first example, the regular expression cat|dog will match either "cat" or "dog" in the text. In the second example, the regular expression colo(u)r will match either "color" or "colour". The OR operator provides flexibility in specifying multiple possible patterns to match in a single regular expression

### Character Classes
Character classes in regular expressions allow you to specify a set of characters that can match at a specific position in the text. They are enclosed within square brackets [ ] and provide a way to match any single character from the defined set. Here's the general syntax:
            [characters]
Inside the square brackets, you can list individual characters or ranges of characters. Character classes can also include predefined shorthand character classes for common sets of characters, such as '\d' for digits, '\w' for word characters, and '\s' for whitespace characters.
Here is a simple character class example:
                [aeiou]
     - Matches: "a","e","i","o","u"
     - Does NOT match: "b","c","d","f"
in this simple illustration character class [aeiou] matches any single lowercase vowel.  Here is a more complex character class:
                [0-9a-fA-F]
    -Matches: ""0", "1", ..., "9", "a", "b", ..., "f", "A", "B", ..., "F"
    -Does NOT match: "g", "h", ..., "z"

In this example, the character class [0-9a-fA-F] matches any single hexadecimal digit, including both lowercase and uppercase letters.

Character classes provide a powerful way to match specific sets of characters within a regular expression, allowing for more precise pattern matching in text data.
### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)