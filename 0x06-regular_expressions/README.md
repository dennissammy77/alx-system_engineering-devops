/***Regular Expression****/
A regular expression, commonly called a “regexp”, is a sequence of characters that define a search pattern.  It is mainly for use in pattern matching with strings, or string matching (i.e. it operates like a “find and replace” command). While it is a very powerful tool, it is also very dangerous because of its complexity.

One thing you have to be careful with is that different languages use different regexp engines. That means that a regexp in Python, for example, will be interpreted differently in Javascript:

eg:- to find all texts in a file manager the regex expression will be ^.*\.txt$

____Text Patterns and Matches____
____Literal Characters____
The most basic regular expression consists of a single literal character, such as a. It matches the first occurrence of that character in the string. If the string is Jack is a boy, it matches the a after the J.
Twelve characters have special meanings in regular expressions:
	-The backslash \
	-the caret ^
	-the dollar sign $
	-the period or dot .
	-the vertical bar or pipe symbol |
	- the question mark ?
	-the asterisk or star *
	-the plus sign +
	-the opening parenthesis (
	-the closing parenthesis )
	-the opening square bracket [
	-and the opening curly brace {
If you want to use any of these characters as a literal in a regex, you need to escape them with a backslash. If you want to match 1+1=2, the correct regex is 1\+1=2. Otherwise, the plus sign has a special meaning.

____Non-Printable characters____
You can use special character sequences to put non-printable characters in your regular expression. Use \t to match a tab character (ASCII 0x09), \r for carriage return (0x0D) and \n for line feed (0x0A).
More exotic non-printables are \a (bell, 0x07), \e (escape, 0x1B), \f (form feed, 0x0C) and \v (vertical tab, 0x0B). Remember that Windows text files use \r\n to terminate lines, while UNIX text files use \n.

____Character Classes or Character Sets____
A “character class” matches only one out of several characters. To match an a or an e, use [ae]. You could use this in gr[ae]y to match either gray or grey. A character class matches only a single character. gr[ae]y does not match graay, graey or any such thing. The order of the characters inside a character class does not matter.

You can use a hyphen inside a character class to specify a range of characters. [0-9] matches a single digit between 0 and 9. You can use more than one range. [0-9a-fA-F] matches a single hexadecimal digit, case insensitively. You can combine ranges and single characters. [0-9a-fxA-FX] matches a hexadecimal digit or the letter X.

Typing a caret after the opening square bracket negates the character class. The result is that the character class matches any character that is not in the character class. q[^x] matches qu in question. It does not match Iraq since there is no character after the q for the negated character class to match.

Ref:
	https://www.regular-expressions.info/
	https://www.regular-expressions.info/quickstart.html
