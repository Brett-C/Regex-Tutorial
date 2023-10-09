# How to Read Regex!

Regular Expressions are a series of special characters that define a search. These charcters are also known as Regex for short. Regex is a method that will help make sure that a specific string matches the specific requirements for different things. You can use regex for a lot of different things such as a username, passwords, emails, even Hex Values! By using regex your code can be more concise and compact rather than using multiple methods with if statements attached to them!

## Summary

This regex is how to match a Hex Value! In this document I will explain all the parts of the regex as well as the components of regex that are not displayed in this particular one. The example of the matching a Hex Value regex is as shown: `^#?([a-f0-9]{6}|[a-f0-9]{3})$`. By clicking on the list of components in the Table of Contents, you will be taken to that particular component and there will be an explination of what is happening behind the scenes for that particular component. We will use the Hex Value regex as an example when applicable.

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

the two characters `^` and `$` are both anchors. `^` states that a string that begins with the characters that follow it. Just remember that regex is case-sensitive so the string has to be an exact match to what ever follows the anchor so, `^Hello` only allows for `Hello` or something like `Hello World` match, but `hello` and `hello world` do not. `$` is the other example of anchors, only it states that a string that ends with the characters that come before it, rather than after. In our example `^#?([a-f0-9]{6}|[a-f0-9]{3})$` we have both anchors! This means that 

### Quantifiers



### Grouping Constructs



### Bracket Expressions

Bracket Expressions are a range of characters that are inside a set of square brackers `[]`. They can also be known as positive character groups because they outline the characters that we want to include. For example the bracket expression `[abc]` would look for a string that contains a, b, or c, no matter how long the string is, so `brett`, `abracadabra`, and `aaa` would all match. To keep everything nice and neat, we usually use a hyphen (-) between alphanumeric characters, or letters and numbers only, to represent a range of the possible characters. This means that `[a-f]` will look for the same thing as `[abcdef]`. But remember, regex is case sensitive so it will only match lower case letters a, b, c, d, e, and f. If we wanted a string to be able to include let's say all letters upper case or lower case, numbers and even some special characters like the hyphen(-) and the underscore(_) we could write it out like this `[a-zA-Z0-9_-]`. It is also good to note that a bracket expression can be turned into a negative character group by adding the `^` sypbole to the start of the expression inside the brackets. This means that we want a string to exclude the characters that are inside the brackets. a common example is matching a string that doesn't have any vowels, so the pattern would show `[^aeiouAEIOU]`. This would find any string that does not include lowercase or uppercase vowels. So let's remind you of our example regex that we wanted to disect. `^#?([a-f0-9]{6}|[a-f0-9]{3})$` shows 2 sets of bracket expressions. They state that we are looking for a string that only uses the characters a-z and 0-9. So if had for example `#abc123` it would match, but `#abz123` does not. 

### Character Classes



### The OR Operator



### Flags



### Character Escapes



## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
