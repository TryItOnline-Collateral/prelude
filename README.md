# [Prelude](https://esolangs.org/wiki/Prelude)

**The materials in this repository were not produced by the owner of the repository. Please click on the link in the header to go to the original web site these materials were copied from. The purpose of this copy is to automate setup of a mirror for https://tryitonline.net. It's more straight forward to clone a repository than to parse a web page.**

A program consists of sets of instructions given in parallel for
a number of "parts" or "voices". Each voice has its own stack.
Instructions given on the same vertical line are executed simultaneously;
the stacks are only updated when all simultaneous instructions
have been executed.

Each voice's stack initially contains an infinite number of zeroes.
Pushing a zero onto an empty stack is guaranteed to not consume any
memory.

Note that many instructions that in other languages would pop a value,
here merely look at it.

## Instructions:

Instruction|Description
-----------|-----------
+|pop two values, add them and push.
-| pop two values, subtract them and push
\#|drop top of the stack
(|if the top value is zero, skip past the matching ); otherwise, continue
)|if the top value is not zero, skip back past the matching (
^|push the top value from the voice above this one
v|push the top value from the voice below
?|input a character (push)
!|output a character (pop)
0..9|push a number

Everything else, including whitespace, is ignored.

( ) don't have to be on the same voice, i.e. ")" could be put anywhere you like.
Note that instructions given simultaneously with the ( are executed only
before the loop is entered; the instructions given with the ) are executed
each time as the last thing in the loop.

It is illegal to have simultaneuosly more than one bracket.

Instructions for the second voice are given below those for the first.
So a single "line" of Prelude code, with instructions for all the voices,
is more than one line of text. To break a line of code, use a line of
text with nothing but a single asterisk. Note that between
lines with asterisks there must be the same number of text lines as
between the start of the file and the first asterisk, or between the
last asterisk and the end of the file, since the number of voices
remains constant
