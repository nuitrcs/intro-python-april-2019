# Python Session 1

This is the material we'll cover during the first part of the workshop (Day 1 morning).  We may deviate a little, but we'll work from this.

We're working interactively with the Python interpreter to start.

On Windows, click Start -> Anaconda3 -> Anaconda Prompt, then type `python` at
the prompt to start the interpreter.

On Mac, open a Terminal window and type `python` at the prompt.  Or from the Anaconda navigator, use Jupyter QtConsole.  

Alternatively, open Spyder and use the Python console that's in the bottom right by default.


## Python as a Calculator

You can type expressions and get the output immediately

```python
2+2
```

You can combine expressions too using parentheses.  The spaces in the expressions below don't have an effect.  They are all optional.

The text that starts with `#` is a comment.  It is not executed.  The `#` denotes that the rest of the line is a comment to be ignored.

```python
50 - 5*6
(50 - 5*6) / 4
8 / 5
8 / 4  # division always returns a floating point number
```

There are additional special operators.

```python
17 / 3
17 // 3  # floor division discards fractional part
17 % 3  # gives you the remainder of the division
```

What does `**` do?

```python
5 ** 2
4 ** (1/2)
```

We can also use python to compare values.  The result is a boolean, which is True or False.

```python
3 == 3.1
3 != 3.1
3 > 3.1
3 < 3.1
```

The `not` operator reverses a boolean value:

```python
not True
not False
not 3 == 3.1
```


## Variables

Variables hold values.  From single numbers to more complex objects.  They can also hold the result of expressions.  Note that in the console, the assignment statement doesn't return anything.  We can type a variable name to get the value.  In scripts, we'd need to use the  `print()` function to see the value.

```python
width = 20
width
height = 5 * 9
width * height
```

Variables must be assigned a value before they can be used

```python
length
```

We get an error:

```
Traceback (most recent call last):

  File "<ipython-input-4-9cf56f394795>", line 1, in <module>
    length

NameError: name 'length' is not defined
```

You'll see this error if you mistype a variable name too.  

Variable names are case sensitive.


```python
Width
```

[Exercise](python-exercises1.md#calculator-and-variables)


## Strings

Strings hold alphanumeric data (letters, numbers, punctuation, etc.) -- text.  You can use single or double quotes, but they need to be matched.

```python
'spam and eggs'
'doesn\'t'
"doesn't"
'"Yes," he said.'
```

You can store values, even emojis!  (in Python 3) 

```python
my_string_variable = 'hi I am a string 😛'
my_string_variable
```

```python
"Python in Korean: 파이썬"
```

New line character, and `print()`.

```python
two_line_string = "This is line 1.\nThis is line2."
two_line_string
print(two_line_string)
```

`print()` is a function.  It's built into Python.  In a script, you'd need to use `print()` to see the output.  Just typing the variable name won't do anything.

You can also use triple quotes for multi-line strings.  They can contain new lines in them.  You can triple either single or double quotes.

```python
long_text = """This is a multiline
  string of text with newline
  characters built in.  Spaces are respected."""
print(long_text)
```

We can join, or concatenate, strings with `+`:

```python
prefix = 'super'
suffix = 'duper'
prefix + suffix
prefix + ' ' + suffix

one = '1'
two = '2'
one + two
```

And we can compare string too based on alphabetical order:

```python
'cat' < 'dog'
'dog' < 'cat'
```

And you can test if a substring is in a string with the `in` operator:

```python
'fox' in 'The quick brown fox'
'dog' in 'The quick brown fox'
```

There are functions that will take a string as an argument:

```python
string_var = 'abcdefg'
len(string_var)
```

But strings also have functions that are called on the string with dot notation.  If you're familiar with other languages, everything in Python is an object.  

Here, the string value itself is implicitly the first argument to the function.  The function is a property of the string object.

```python
string_var.upper()
string_var.count('a')
string_var.replace('ab', 'X')
string_var
```

Note that `replace()` didn't change the value of `string_var`.  How could we change it?


With dot notation, you can chain function calls together.  `string_var.replace('a', 'X')` returns a string, so we can call `replace()` on the string that is returned too:

```python
string_var.replace('a', 'X').replace('b', 'Y')
```

[Exercise](python-exercises1.md#strings)



## Types

We've used numeric values and strings.  Every value (including those stored in variables) has a type:


```python
type('abc')
type(123)
type(0.1)
```

Values of one type can be converted to other types with built-in functions.


```python
float(3)
float('3.2')
string(3.56)
```

But not all conversions are defined:

```python
int('1.1')
```

Instead:

```python
x = float('1.1')
int(x)
```

Or, we could nest our function calls:

```python
int(float('1.1'))
```

Type matters when doing comparisons

```python
ten_int = 10
ten_string = '10'
ten_int == ten_string
ten_int == int(ten_string)
```

```python
'3' > 3
```

And operators behave differently for different types of data:

```python
ten = '10'
ten + ten
ten = int(ten)
ten + ten
```

And certain functions expect certain types of data.

There's a special type, `None`, that can be used to represent no value.

```python
x = None
x
print(x)
type(x)
```

[Exercise](python-exercises1.md#types)



## String Indexing

A string is made up of individual characters.  We can access these individual characters using square brackets.  The index of the first element is always 0.


```python
string_var = 'abcde'
string_var[0]
string_var[5]
```

Negative numbers count from the end:

```python
string_var[-1]
string_var[-2]
```

We can get consecutive values to extract a substring with `start:end`.  End is exclusive.  This take each integer value from start to end.

```python
string_var[0:3]
```

If we go over the end, we only get what's available:


```python
string_var[0:30]
```

We can do ranges with negative values too.  Smallest value goes first:

```python
string_var[-3:-1]
```

We can leave out either half of the range (leave it blank):

```python
string_var[2:]
string_var[:2]
```

or both:

```python
string_var[:]
```

Instead of taking each integer value between `start:end`, we can step by other values instead of just 1: `start:end:step` (step is assumed to be 1 if not specified).


```python
letters = 'abcdefghijklmnopqrstuvwxyz'
letters[0:26:1]
letters[0:26:2]
letters[::2]
```

Now, we can reverse order with a step of -1:

```python
letters[26:0:-1]
letters[-1::-1]
letters[-1::-2]
```


[Exercise](python-exercises1.md#string-indexing)

## Lists

So how do we build up more complex structures?  Python has another fundamental type called a list.  A list is a collection of other values, other lists, or other objects (string, integers, lists, etc. are all objects, but packages (and you!) can define new objects too).

A list is created with `[]` or you can make an empty list with `list()`.  

```python
my_list = ['a', 'b', 'c', 'd']
my_list
```

The elements in a list don't have to be of the same type, but they usually are.

```python
my_mixed_list = [1, 'a', 2.3, [4, 5, 6]]
my_mixed_list
```

Lists are indexed like strings:

```python
my_list[0]
my_list[:2]
```

And you can get their length with `len()`:

```python
len(my_list)
```

When you have nested lists, you need a separate set of brackets for each list:

```python
nested_lists = [[2, 3, 5, 7, 11], [2, 4, 6, 8]]
len(nested_lists)
nested_lists[0]
nested_lists[0][1]
nested_lists[-1][-1]
```

You can join lists by adding them:

```python
primes = [2, 3, 5, 7, 11]
more_primes = [13, 17, 19]
primes + more_primes
```

You can add a single element to a list with `append()`.  THIS CHANGES THE LIST!

```python
primes.append(13)
primes
```

If you append a list, you get a nested list:

```python
primes.append(more_primes)
primes
```

To  have them in one list instead, use `extend()`

```python
primes = [2, 3, 5, 7, 11]
more_primes = [13, 17, 19]
primes.extend(more_primes)
primes
```

Lists are mutable, meaning you can change the elements.  

```python
fruit = ['apple', 'banana', 'pear']
fruit[0] = 'fig'
fruit
```

Strings are not mutable.  The following gives you an error.

```python
my_name = 'Christina'
my_name[0] = 'c'
```

You can assign to slices of lists too

```python
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
letters
letters[2:5] = ['C', 'D', 'E']
letters
```

Be careful, since the replacement length doesn't need to match.  Replacement will go in the same spot in the list, but can be longer or shorter.

```python
letters[2:5] = ['c']
letters
```

There are additional list functions that can change a list:

```python
list1 = ['x', 'g', 'v', 'a']
list1.sort()  
list1
```

The `in` operator lets you test whether a specific value is in your list:

```python
'a' in list1
'b' in list1
'b' not in list1
```


[Exercise](python-exercises1.md#lists)

## Dictionaries

Dictionaries hold key-value pairs.  Keys are labels you can use to look up the stored values associated with them.

Keys are usually strings, but they don't have to be.  Keys are unique.

Create a dictionary with `{}` or an empty dictionary with `dict()`.


```python
ages = {'Casey': 41, 'Henry': 4, 'Madison': 2, 'Caroline': 0, 'Brian': 36}
ages
```

Instead of indexing with positions, we index with keys:

```python
ages['Casey']
ages['Madison']
ages['Christina']
```

Or we can use the `get()` function, which optionally lets us specify a default value if the key isn't present:

```python
ages.get('Brian')
ages.get('Christina')  # None is the default
ages.get('Christina', 50)
```

For dictionaries, `in` tests keys:

```python
'Madison' in ages
41 in ages
```

We can get all of the keys or values with functions:

```python
ages.keys()
ages.values()
```

We can get the keys and values together with `items()`

```python
ages.items()
```

These functions are most useful in combination with loops, which we'll get to later.

[Exercise](python-exercises1.md#lists)




