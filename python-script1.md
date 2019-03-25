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
3 > 3.1
3 < 3.1
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

one = '1'
two = '2'
one + two
```

There are functions that will take a string as an argument:

```python
string_var = 'abcdefg'
len(string_var)
```

But strings also have functions that are called on the string with dot notation.  Here, the string value itself is implicitly the first argument to the function.  The function is a property of the string type.

```python
string_var.upper()
string_var.count('a')
string_var.replace('a', 'X')
string_var
```

Note that `replace()` didn't change the value of `string_var`.  How could we change it?

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

[Exercise](python-exercises1.md#types)



## Indexing

A string is made up of individual characters.  We can access these individual characters using square brackets.  The index of the first element is always 0.


```python
string_var = 'abcde'
string_var[0]
string_var[5]
```

```python

```


```python

```

```python

```

```python

```

```python

```

```python

```

```python

```

```python

```

```python

```



