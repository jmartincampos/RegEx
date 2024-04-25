# Title (replace with your title)

Welcome to RegEx Tutorial - Watching an email address.  In this tutorial, we wil navigate how to use regular expressions to validate and match email addresses.  


## Summary

What exactly is RegEx?
 A regex, short for regular expression, is a sequence of characters that defines a specific search pattern. In this tutorial, we'll focus on understanding and using a regular expression to match email addresses.

 The regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` are used to match email addresses.



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
Flags in regular expressions are optional parameters that modify the behavior of the pattern matching. They are appended to the end of the regular expression and alter how the matching is performed. Here are some common flags:

i: Case-insensitive matching.
g: Global matching (find all matches rather than stopping after the first match).
m: Multi-line matching (treats beginning and end characters (^ and $) as working across multiple lines).
s: Dot-all matching (treats the dot (.) as matching any character, including newlines).
u: Unicode matching (treats the pattern and subject strings as UTF-16 encoded).
y: Sticky matching (matches only from the index indicated by the lastIndex property of the RegExp object).
Here is a simple example of a # FLAG 
                    /cat/i
    - Matches: "cat", "Cat", "cAt", "CAT", etc.
In this example, the i flag makes the regular expression case-insensitive, so it matches "cat" regardless of whether it's in uppercase or lowercase.

Here is a more compex example:
                    /cat/gi
    - Matches: "cat", "Cat", "cAt", "CAT", etc., and all occurrences in the text. 
In this example, the g flag makes the regular expression global, so it matches all occurrences of "cat" in the text. The i flag still makes it case-insensitive, allowing it to match variations of "cat" regardless of case.

Flags provide flexibility in how regular expressions are applied, allowing for more customizable and powerful pattern matching in text data.
### Grouping and Capturing
Grouping and capturing in regular expressions allow you to define subpatterns within your regex and capture the matched substrings for later use. They are denoted by parentheses () and are useful for applying quantifiers or alternations to multiple characters or groups.

Here's the breakdown:

Grouping ( ): Groups parts of the regular expression together. This allows you to apply quantifiers or alternations to multiple characters or groups.
Capturing ( ... ): In addition to grouping, capturing allows you to capture the matched substring enclosed within the parentheses.

Here's a simple example:
                    /(cat)/1\
    -Matches: "catcat
    -Does NOT match: "cat"
In this example, (cat) is a capturing group that matches the substring "cat". \1 is a backreference to the first captured group (cat). This regex matches the repeated substring "catcat" 
                    /(John) (Doe)/
    -Matches: "John Doe"
    -Does NOT match: "JohnDoe","Doe John"
In this example, (John) and (Doe) are capturing groups that match the first and last name, respectively. The space between them ensures that both parts are present and in the correct order.

Grouping and capturing allow you to structure your regular expressions more effectively and extract specific parts of the matched text for further processing or validation. They are essential tools for working with complex patterns in text data.
### Bracket Expressions
Bracket expressions and character classes refer to the same concept in regular expressions. Both terms describe the use of square brackets [ ] to define a set of characters that can match at a specific position in the text.

The terms "bracket expressions" and "character classes" are often used interchangeably to describe this feature of regular expressions. They provide a way to specify a group of characters that can be matched at a single position, allowing for flexible pattern matching in text data. See above example for context.

### Greedy and Lazy Match

Greedy and lazy matching in regular expressions refer to the behavior of quantifiers when matching patterns in text.

Greedy matching: The default behavior of quantifiers, where they match as much of the string as possible while still allowing the overall pattern to match. Greedy quantifiers are denoted by appending *, +, ?, or {} to the pattern.
Lazy (or non-greedy) matching: A mode where quantifiers match as little of the string as possible, only consuming as many characters as needed for the overall pattern to match. Lazy quantifiers are denoted by appending *?, +?, ??, or {} to the pattern.

Here are examples to illustrate the difference:
1 - Greedy matching:
                /(.*\d)/

- String: "1234567890"
- Greedy match: "1234567890"

In this example, the `.*` quantifier matches as many characters as possible (greedy behavior) until it encounters a digit `\d`. As a result, the entire string is consumed and matched.

2-  Lazy (non-greedy) matching:
                /(.*?\d)/

- String: "1234567890"
- Lazy match: "1"

In this example, the `.*?` quantifier matches as few characters as possible (lazy behavior) until it encounters a digit `\d`. As a result, only the first character "1" is matched, allowing the overall pattern to still match.

Greedy and lazy matching behavior can significantly impact the behavior of regular expressions, especially when dealing with patterns that contain multiple quantifiers. Understanding and appropriately using greedy and lazy quantifiers is crucial for writing efficient and accurate regular expressions.

### Boundaries
Boundary assertions in regular expressions define positions in the text where certain conditions must be met for a match to occur. These assertions don't consume any characters themselves, but they assert that certain conditions must be true at a particular position in the text.

Here's the breakdown:

Boundary assertions: Specify positions in the text where certain conditions must be met for a match to occur.
Common boundary assertions include:
^: Matches the beginning of a line.
$: Matches the end of a line.
\b: Matches a word boundary (a position between a word character and a non-word character).
\B: Matches a non-word boundary.
\A: Matches the beginning of the text.
\Z: Matches the end of the text (or before a newline at the end of the text).
\z: Matches the end of the text.
Here's a simple example:
            /^hello/
    - Matches: "hello world"
    - Does not match: "world hello"
In this example, ^ asserts that the pattern hello must appear at the beginning of a line for a match to occur.

And here's a more complicated example:
            /\bcat\b/
    - Matches: "cat", "The cat is black."
    - Does not match: "cats", "scatter"
In this example, \b asserts that the pattern cat must be surrounded by word boundaries for a match to occur. This ensures that the regex matches the whole word "cat" and not part of a larger word like "cats" or "scatter".

Boundary assertions provide a powerful way to define precise conditions for matches in regular expressions, allowing for more accurate pattern matching in text data.

### Back-references
Back-references in regular expressions allow you to refer back to previously captured groups within the same regular expression pattern. They are denoted by \ followed by a digit representing the index of the captured group.

Here's the breakdown:

Back-references: Refer back to previously captured groups within the same regular expression pattern.
They allow you to match the same text that was previously matched by a capturing group.
Back-references are particularly useful when you want to match repeated occurrences of the same text.
Here's an easy example:

Matching repeated words:
                /(\w+) \1/
        - Matches: "hello hello", "cat cat"
        - Does not match: "hello world", "cat dog"
In this example, (\w+) captures a word, and \1 is a back-reference to the first captured group. This regex matches repeated occurrences of the same word separated by a space.

And here's a more difficult example:
Matching repeated HTML tags:
                /<(\w+)>\s*.*<\/\1>/
        - Matches: "<div>some content</div>", "<p>more content</p>"
        - Does not match: "<div>some content</p>", "<p>more content</div>"
In this example, <(w+)> captures an HTML tag, \s* matches optional whitespace, .* matches any content between the opening and closing tags, and </\1> is a back-reference to the name of the opening tag. This regex matches pairs of HTML tags with matching opening and closing tags and any content in between.

Back-references provide a powerful way to match repeated occurrences of the same text within a regular expression pattern, allowing for more flexible and precise pattern matching in text data.

### Look-ahead and Look-behind
Look-ahead and look-behind assertions in regular expressions allow you to assert whether a certain pattern is (or is not) followed or preceded by another pattern, without including the matched text in the overall match. They are denoted by (?= ... ) for positive look-ahead, (?<= ... ) for positive look-behind, (?! ... ) for negative look-ahead, and (?<! ... ) for negative look-behind.

Here's the breakdown:

Look-ahead and look-behind assertions: Assert whether a certain pattern is (or is not) followed or preceded by another pattern.
They do not consume any characters themselves, only asserting whether a certain condition is met at a specific position in the text.

Here is an easy example:
Matching a word followed by a coma:
                /\w+(?=,)/
        - Matches: "hello" in "hello,", "world" in "world,"
        - Does not match: "hello" in "hello world"
In this example, (?=,) is a positive look-ahead assertion that asserts the presence of a comma , after the word \w+. This regex matches words that are followed by a comma.

And here's a more challenging example:
Matching a word preceded by a certain prefix:
                 \/(?<=prefix )\w+/
        - Matches: "word" in "prefix word"
        - Does not match: "word" in "prefix suffix word"
In this example, (?<=prefix ) is a positive look-behind assertion that asserts the presence of the prefix "prefix" before the word \w+. This regex matches words that are preceded by the specific prefix "prefix".

Look-ahead and look-behind assertions provide a powerful way to assert conditions on the text surrounding a pattern without including the matched text in the overall match, allowing for more complex and precise pattern matching in text data.                


## Author

A short section about the author with a link to the author's GitHub profile (https://github.com/jmartincampos)