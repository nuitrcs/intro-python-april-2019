# Python Session 2

This is the material we'll cover during the first afternoon session of the workshop (Day 1 afternoon). As usual, we may deviate a little, but we'll work from this.

Questions for the first afternoon session:

* What constructs are available for changing the flow of a program?

* How can I repeat an action many times?

* How can I perform the same task(s) on a set of items?

* How can I automate the whole process? 

Objectives for the first part of the afternoon:

* Change program flow using available language constructs

* Demonstrate how to execute a section of code a fixed number of times

* Demonstrate how to conditionally execute a section of code

* Demonstrate how to execute a section of code on a list of items

* Demonstrate how to run the script


We will continue to work interactively with the Python interpreter to start the afternoon. As we are going to gradually move towards using files/scripts, please,
 open Spyder and use the Python console that's in the bottom right by default.


## Programs are rarely linear

Most programs do not work by executing a simple sequential set of statements. The code is constructed so that decisions and different paths through the program can be taken based on changes in variable values.

To make this possible all programming language have a set of control structures which allow this to happen.

In this session we are going to look at how we can create loops and branches in our Python code. Specifically we will look at two control structures, namely:

* If..Else..
* For ..

## Branching - The `if` statement and variants

The simple if statement allows the program to branch based on the evaluation of an expression

The basic format of the if statement is:

```python
if expression :
    statement 1
    statement 2
    ...
    statement n

statement always executed
```
If the expression evaluates to `True` then the statements 1 to n will be executed followed by `statement always executed` . If the expression is `False`, only `statement always executed` is executed. Python knows which lines of code are related to the `if` statement by the indentation, no extra syntax is necessary.

**Note:** In python, every object can be evaluated in a boolean context. The following evaluate to false: `False`, `None`, `0`, `""` (the empty string), and empty containers (lists, dictionaries, etc).
Everything else evaluates to true.


Below are some examples:

**Input:**
```python
print("\nExample 1\n")
value = 3
threshold = 2
if value > threshold:
    print("value is greater than threshold.")
print("\nvalue = ", value, "\nthreshold = ", threshold)

print("\nExample 2\n")
if value < threshold: # Print statement below is skipped
    print("value is less than threshold.")  
print("value = ", value, "\nthresold = ", threshold)
```

**Output:**
```
Example 1

value is greater than threshold.
value = 3
threshold = 2

Example 2

value = 3
threshold = 2
```

In the examples above there are four things to notice:

1. The colon `:` at the end of the if line. Missing this out is a common error.
2. The indentation of the print statement. If you remembered the `:` on the line before, any Python IDE will automatically do the indentation for you. All of the statements indented at this level are considered to be part of the `if` statement. This is a feature fairly unique to Python, that it cares about the indentation. If there is too much, or too little indentation, you will get an error.
3. The if statement is ended by removing the indent. There is no explicit end to the if statement as there is in many other programming languages.
4. In the last example, notice that in Python the operator used to check equality is ==.

Other comparison operators are: 
```
Operator    Meaning

==          Equal to

!=          Not equal to

<           Less than

>           Greater than

<=          Less than or equal to

>=          Greater than or equal to
```
[Exercise](python-exercises2.md#if)

Instead of using two separate `if` statements to decide which is larger we can use the `if ... else ...` construct

**Input:**
```python
# If ... Else ...

value = 3
threshold = 2

if value > threshold :
    print("above threshold")
else :
    print("below threshold")
print("value = ", value, " and threshold = ", threshold)
```

**Output:**
```
below threshold
value = 4 and threshold = 5
```

[Exercise](python-exercises2.md#if-else)

A further extension of the `if` statement is the `if ... elif ...else` version.

The example below allows you to be more specific about the comparison of value and threshold.

```python
# If ... Elif ... Else ... EndIf

value = 3
threshold = 2
print("value = ", value, " and threshold = ", threshold)

if value > b :
    print(value, " is greater than ", threshold)
elif value == b :
    print(value, " equals ", threshold)
else :
    print(value, " is less than ", threshold)
```

```
value = 3 and threshold = 2
3 is greater than 2
```

The overall structure is similar to the `if ... else` statement. There are three additional things to notice:

1. Each `elif` clause has its own test expression.
2. You can have as many `elif` clauses as you need
3. Execution of the whole statement stops after an `elif` expression is found to be `True`. Therefore the ordering of the `elif` clause can be significant.

Therefore, instead of combining several comparisons by `elif` clauses we could combine comparison operators. For that we could use the `and` and `or` keywords to combine multiple comparisons into a single test.</p>

```python
value = 50
threshold1 = 50  
threshold2 = 60
if (value >= threshold1 and value < threshold2):
  print("value is between threshold1 and threshold2")
```

Notice that after any math and comparison operators evaluate, Python evaluates the `not` operators first, then the `and` operators, and then the `or` operators.  You can use parentheses () to group statements.

## The `for` loop

The Python for statement iterates over each item in a sequence.

```python
for variable_name in some_sequence :
    statement1
    statement2
    ...
    statementn
```

Lists are one kind of some_sequence, but there are others.

```python
words = ['cat', 'window', 'defenestrate']
for w in words:
    print(w, len(w))
```

Like an if statement, the "body" of the loop must be indented.

All lines within the loop body must be indented by the same amount.

[Exercise](python-exercises2.md#for-indentation)

```python
# This is proper indentation
words = ['cat', 'window', 'defenestrate']
for word in words:
    print(word)
    print(len(word))
```

```python
# This is bad indentation
words = ['cat', 'window', 'defenestrate']
for word in words:
 print(word)
  print(len(word))
```

### The range() Function

If you need to iterate over a sequence of numbers, the `range()` function comes in handy. It generates arithmetic progressions:

```python
for i in range(5):
    print(i)
```

The given end point is never part of the generated sequence; `range(10)` generates 10 values, the legal indices for items of a sequence of length 10. It is possible to let the range start at another number, or to specify a different increment (even negative; sometimes this is called the "step"):

```python
for i in range(5, 10):
    print(i)
```
```python
for i in range(5, 0, -1):
    print(i)
```
```python
# what is a range, exactly?
print(range(5))
```
A range object (the thing returned by the `range()` function) is something that Python calls an "iterable". That means, you can count through the sequence, starting at the beginning and stopping at the end.
Some Python functions expect an object they can obtain successive items from until the supply is exhausted, but the items are not generated until requested. This saves space in memory.
There are many examples of things which are iterable some of which we have already come across.

* Lists are iterable - they don’t have to contain numbers, you iterate over the elements in the list.
* The `range()` function
* The characters in a string

[Exercise](python-exercises2.md#for-range)

## Key Points

* Most programs will require ‘Loops’ and ‘Branching’ constructs.

* The if, elif, else statements allow for branching in code.

* The for and while statements allow for looping through sections of code
