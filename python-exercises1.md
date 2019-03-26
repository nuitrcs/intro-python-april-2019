These are during-workshop exercises that correspond to the [first Python script](python-script1.md) file.


## Calculator and Variables

Use Python to find the answer:

![square root of 17/42 + 0.45 times 3.1](images/equation.png)

Save the answer to a variable called `result`.  Print out the value of `result`.



## Strings

* Create variables `firstname` and `lastname`.  
* Join them together with a space in-between and save that in a variable called `fullname`.  
* `print()` your full name.  
* Then print your full name converted to all upper case.  
* How many letters are in your name?  
* Bonus: Replace all of the lowercase vowels in your name with `*`.


Done with the above?  Create a variable with the text of Margaret Atwood's poem "You Fit Into Me" with line breaks and empty lines included:

```
you fit into me
like a hook into an eye

a fish hook
an open eye
```


## Types

If you divide an integer by an integer, what is the type of the result?  What if you divide an integer by a float?  A float by an integer?


## String Indexing

### Part 1

Start with the variable `sentence` as defined below.

```python
sentence = "The quick brown fox jumped over the lazy dog."
```

* Get the first 10 characters of `sentence`
* Get the substring of `sentence` corresponding to "dog"


### Part 2

We got every other letter in `letters` starting with `a`.  Get every other letter starting with `b` instead.  Hint: what is the index of b in `letters`?  Use that as the start in `start:end:step`.

```python
letters = 'abcdefghijklmnopqrstuvwxyz'
```


## Lists

Make a list with 3 of your favorite words.  Referencing each word using its index, print the following sentence with each word inserted in turn: "One of my favorite words is \_\_\_."  (Hint: remember how to concatenate strings?)

Reverse the order of the list by indexing with a negative step value.  Then, find the function to reverse a list (hint: google "python reverse list" or look at your cheatsheet).

Replace the middle element of the list with a new word.

Use `in` to test if 'flamingo' is in your list.


## Dictionaries

Make a dictionary with keys being types of animals and values being their class (invertebrate, mammal, bird, amphibian, reptile, or fish).  Stuck thinking of animals?  Use: dog, cat, frog, snake, salamander.

Get the class of two of the animals you added.  Get the class of 'flamingo' using `get()`, with a default value of 'unknown'.

Get all of the keys in the dictionary.




