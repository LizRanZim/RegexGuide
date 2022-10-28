# Regex Guide to Matching a Hex Value

The goal of this tutorial is to explain the Regex or Regular Expression for matching a Hex Value. Regex is a series of special characters that defines a search pattern. So if you need to make sure the input entered in a form is a hex value, you could use a Regex to verify that in Javascript.

## Summary

Here is the Regex for matching a hex value:
`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

We will disassemble each set of characters in order to explain how the code above matches a hex value. 

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
Regex is considered a literal so that means the expression must have a beginning slash / and an ending / slash wrapped around the expression. Sometimes you'll see additional characters after the ending / slash, those are known as flags which are discussed below.

### Anchors
Anchors are the characters that begin and end the expression. 

The character ^ begins the expression and occurs after the first slash /.

The character $ ends the expression and occurs before the last slash /.


### Quantifiers

After the anchors you'll see a # sign, that just means that the hex code you are matching against must start with a # sign. 

Next you see a ? just after the # sign. That ? is a quantifier. That ? means that whatever you are matching against must follow the expression rules noted between the parenthesis 0 or 1 time.

There are other quantifiers here also. Those are noted with the {6} and later the {3} in our expression.

These quantifiers denote what the limit of the string, or section of the string, is. In our example, the first section of the string, [a-f0-9]{6} , can be a letter from a-f or an integer from 0-9 and that {6} in the curly bracket means that section of the string has a length of 6.

Similarly the second section of the string [a-f0-9]{3} ,  can be a letter from a-f or an integer from 0-9 and that {3} in the curly bracket means that section of the string has a length of 3.


### Grouping Constructs

The parenthesis in the Regex are called grouping constructs. They allow us to break the expression into subexpressions within the parenthesis.
Our example just hast one grouping construct between the opening parenthesis ( and the closing parenthesis ).

### Bracket Expressions

We glossed over our bracket expressions above when talking about quantifiers, but basically the bracket expression just refers to anything inside the brackets. It is the pattern for the set of characters that we are trying to match to, which in this example is [a-f0-9]. In this case it is any lower case string from a-f or any number between 0-9.

We use it twice in this expression because of how they interact with the quantifiers, meaning that our first bracket expression [a-f0-9]{6} has to have string length of 6, and the second bracket expression [a-f0-9]{3} has to have a string length of 3. The pattern doesn't mean that the string we are trying to match to meets all of the requirements, it can meet any of the requirements.


### Character Classes

Character classes define a group of characters. This group of characters can be in a string to make the string match our Regex. Bracket expressions are character classes. 

### The OR Operator

We haven't talked yet about this | pipe character in our expression in between the bracket expressions. It just means "or". So in our Regex for this section [a-f0-9]{6}|[a-f0-9]{3} , that | is just saying that the value we are matching to must have either a 6 string length value that contains a lower case a-f or 0-9 or (this or is where the | comes in) a 3 string length value that contains a lower case a-f or 0-9. 


### Flags

Flags can occur after the last / slash in a Regex but we don't have any in our example. There are 6 optional flags that can be used as of this writing. The most common are g (global search), i(case-insensitive), m (multi-line search).

### Character Escapes

Character Escapes are used when one of the characters that makes up a Regex is also one of the characters that you need to use in your regex. So if you had a regex where you needed to match to something that contained a { bracket, you could use a backslash \ before the open curly { , like this \{ .
This tells the regex that you are not starting a bracket expression but are instead wanting to use the { as a part of your match rules within your bracket expression.


## Author

At the time of writing LizRanZim is Full Stack Web Developer Bootcamp Student. 
GitHub Profile: <a href="https://github.com/LizRanZim">
https://github.com/LizRanZim</a>

