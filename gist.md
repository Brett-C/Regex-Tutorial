# How to Read Regex!

Regular Expressions are a series of special characters that define a search. These charcters are also known as Regex for short. Regex is a method that will help make sure that a specific string matches the specific requirements for different things. You can use regex for a lot of different things such as a username, passwords, emails, even Hex Values! By using regex your code can be more concise and compact rather than using multiple methods with if statements attached to them!

## Summary

This regex is how to match a Hex Value! In this document I will explain all the parts of the regex as well as the components of regex that are not displayed in this particular one. The example of the matching a Hex Value regex is as shown:

 `^#?([a-f0-9]{6}|[a-f0-9]{3})$`
 
By clicking on the list of components in the Table of Contents, you will be taken to that particular component and there will be an explination of what is happening behind the scenes for that particular component. We will use the Hex Value regex as an example when applicable.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

First lets start of with a list of regex components that are out there. Regex uses several different components that help identify requirements for specific strings. the components of a regex have specific qualities that have a very specific notation. The regex components are: Anchors, Bracket Exprerssions, Quantifiers, Grouping Constructs, The OR Operator, Character Escapes, Character Classes, and Flags. We will go into further detail around what each component does and what it might look like!

### Anchors

the two characters `^` and `$` are both anchors. `^` states that a string that begins with the characters that follow it. Just remember that regex is case-sensitive so the string has to be an exact match to what ever follows the anchor so, `^Hello` only allows for `Hello` or something like `Hello World` match, but `hello` and `hello world` do not. `$` is the other example of anchors, only it states that a string that ends with the characters that come before it, rather than after. In our example 

`^#?([a-f0-9]{6}|[a-f0-9]{3})$`

we have both anchors! This means that have to start and end with the string for it to match the regex. 

### Quantifiers

Quantifiers set the limits of the string that a regex matches. They typically include the minimum and maximum number of characters that a regex is looking for. They also tend to match as many occurrences of a particular pattern as possible and include the following symbols:

`*` - matches the pattern zero or more times

`+` - matches the pattern one or more times

`?` - matches the pattern zero or one time

`{}` - the curly brackets provide 3 possible different ways to set limits for a match. These are:

`{ n }` -  matches the pattern exactly `n` times 

`{ n, }` - matches the pattern at least `n` times

`{ n, x }` - matches the pattern from a minimum of `n` times to a maximum of `x` times.

If we throw a `?` behind any of the quantifiers they will match as few occurrences as possible instead of matching as many as possible. If we take a look at our Hex Value regex we can look at what quantifiers it shows. 

`^#?([a-f0-9]{6}|[a-f0-9]{3})$` 

Our regex shows 3 different quantifiers in it `{6}` and `{3}`. That means that our regex is looking a string that has either 6 characters of 3 characters following the `#`. The 3rd quantifier is located behind the `#` and is the `?`, and this means that the string will need to have 0 or 1 `#` it it for it to match the regex. 

### Grouping Constructs

If we have a really long regex we may need to break it up so that we can check different sections of a string. We can do this by using the grouping constructs. The best way to group a section of regex is by using `()`. Each section within parentheses is known as a subexpression. Subexpressions will look for an exact match within the parentheses, so `(abc):(xyz)` will only look for a string of "abc", "xyz" and even "abc:xyz" , anything else will not match. Now let us look at our Hex Value regex and see what grouping constructs it shows. 

`^#?([a-f0-9]{6}|[a-f0-9]{3})$`

It appears that we have one grouping construct within our regex `([a-f0-9]{6}|[a-f0-9]{3})`. This grouping construct means that we are looking to match a string to what is exactly within the parentheses. We have 2 bracket expressions that are linked by an OR operator. We will go over this in a little while. 

### Bracket Expressions

Bracket Expressions are a range of characters that are inside a set of square brackers `[]`. They can also be known as positive character groups because they outline the characters that we want to include. For example the bracket expression `[abc]` would look for a string that contains a, b, or c, no matter how long the string is, so `brett`, `abracadabra`, and `aaa` would all match, but `Brett` would not . To keep everything nice and neat, we usually use a hyphen (-) between alphanumeric characters, or letters and numbers only, to represent a range of the possible characters. This means that `[a-f]` will look for the same thing as `[abcdef]`. But remember, regex is case sensitive so it will only match lower case letters a, b, c, d, e, and f. If we wanted a string to be able to include let's say all letters upper case or lower case, numbers and even some special characters like the hyphen(-) and the underscore(_) we could write it out like this `[a-zA-Z0-9_-]`. It is also good to note that a bracket expression can be turned into a negative character group by adding the `^` sypbole to the start of the expression inside the brackets. This means that we want a string to exclude the characters that are inside the brackets. a common example is matching a string that doesn't have any vowels, so the pattern would show `[^aeiouAEIOU]`. This would find any string that does not include lowercase or uppercase vowels. So let's remind you of our example regex that we wanted to disect. 

`^#?([a-f0-9]{6}|[a-f0-9]{3})$`

shows 2 sets of bracket expressions. They state that we are looking for a string that only uses the characters a-z and 0-9. So if had for example `#abc123` it would match, but `#abz123` does not. 

### Character Classes

A character class within a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. The bracket expression discussed earlier including positive and negative character groups, are also considered character classes. Some other examples of character classes are:
`.` - matches any character except the newline charcter (\n).
`\d` - matches any Arabic numeral digit. This class is the same to the bracket expression `[0-9]`.
`\w` matches any alphanumeric character from the basic Latin alphabet, including the underscore. It is the same as the bracket expression `[A-Za-z0-9_]`.
`\s` matches a single whitespace character, including tabs and line breaks.

The last 3 character classes can be changed to do the inverse match by capitalizing the letter character which means `\D `would match a non-digit character. 

Unfortunately our Hex Value regex does not have any Character Escapes in it.

### The OR Operator

The OR Operator is a way to  seperate the bracket expression. We also may want to use an OR Operator outside of a bracket expression, especially within a grouping construct, or even between grouping constructs. for example `[abc]` could be written as `(a|b|c)`. If we look at the example of `(abc):(xyz)`, and then rewrite it using OR operator to look like `(a|b|c):(x|y|z)`. This means that "abc:xyz" and "acb:xzy" would match, and even "a:z" would match as well, but "xyz:abc" would not because the two grouping constructs are not in the correct order. Again let us look at our Hex Value regex and see what OR operators it shows. 

`^#?([a-f0-9]{6}|[a-f0-9]{3})$`

We have 1 OR operator within the grouping construct. `([a-f0-9]{6}|[a-f0-9]{3})` shows that we will match anything from "a-f and 0-9" with 6 characters OR 3 characters. that means that "abc123" would match as well as "a12". Anything more or less than 3 characters (except for 6 obviously) would not match just like anything more or less than 6 characters (except 3) would also not match.

### Flags



### Character Escapes

A character escape can be a character that would be interpreted literally. To do this, we need to use the backslash "\" key. for example if we used the open curly brace "{" it would be used to begin a quantifier, but by adding a backslash before the open curly brace (\{) it means that the regex should look for the open curly brace character instead of beginning to define a quantifier. This is pretty common when looking for strings with special characters that are the same as a particular component of a regex. On a side note it is important to understand that all special characters, including the backslash, lose their special significance inside bracket expressions. Unfortunately our Hex Value regex does not have any Character Escapes in it. 

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
