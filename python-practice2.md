# Part 2 Python Practice

These are additional practice exercises.  The exercises are designed to be completed using either the interactive Python interpreter, Spyder, or by writing a script or using Jupyter Notebooks if you prefer. 

## To get a Python Prompt

On Windows, click Start -> Anaconda3 -> Anaconda Prompt, then type `python` at
the prompt to start the interpreter.

On Mac, open a Terminal window and type `python` at the prompt.

Alternatively, open Spyder and use the Python console that's in the bottom right by default.  Or use QtConsole from Anaconda Navigator.  

## List Functions
We can quickly identify the smallest or largest items in a list with the min() and max() functions. Find out how to use these function from the web and then use them to identify the maximum and minumum elements of the list [-3,-2,-1,0,1,2,3,4,5,6,7]

## Tuple Functions
Use min() and max() functions to identify the maximum and minumum elements of the tuple {-3,-2,-1,0,1,2,3,4,5,6,7}

## List slicing practice
Define variable my_list as [1,2,3,5,7,11]. Is my_list[3::-1] the same as my_list[3:0:-1]. Why or why not?

## "in" operator
We can use the "in" operator to test if a list contains a particular value. Look up how to use "in" operator on the web and determine if the following values in the lists [1,2,3,4], [0, 2, 3], and [-3,-2,-1,0,1,2,3,4,5,6,7,8,9,10]. (You may want to define variables for these lists first.)

## Quote characters
Is there any difference between strings S1, S2, S3, S4 defined below? Print their lenghts (i.e. the number of characters for a string) with len() function to check.

## Sort and reverse
On the web, search for sort and reverse methods for lists. Apply these methods to list [9.02,20.4,-4,67,2,34,34.1,0]

* First, order the elements in the list from the smallest to the largest using sort methods
* Second, use the reverse method to order the list from the largest to the smallest

## Reverse Sort
Use only the sort method get the list [9.02,20.4,-4,67,2,34,34.1,0] sorted from the largest to the smallest. (Tip: sort method accepts a reverse parameter)

## Sorting Tuples
Can you apply the same sort and reverse methods to the tuple (9.02,20.4,-4,67,2,34,34.1,0)? Trying is the best way to answer!

## String Functions - Challenging
Look up the [string formatting syntax](https://docs.python.org/3.6/library/string.html#format-string-syntax).

## if/elif/else basics
Write a small python code where you check if a variable with a numeric value is negative, positive, or zero and report solution by print.

## while loop
Use while loop to print integers between 5 and 12, excluding limits (i.e. 5 and 12)

## while loop factorial - challenging
Using a while loop, write a short python script to compute 34! (the factorial of 34: n! = [n*(n-1)*(n-2)*...*2])

## for loop factorial - challenging
Write the same script (i.e. calculating 34!) using a for loop and the range function.

* Search the web for range function and its usage
* Test your understanding by constructing for loops to print the values in range(7), range(1,7), range(1,7,2)
* Construct the for loop with appropriate use of the range function to calculate n!

## More looping
Write a script that divides 50 by each integer between 1 and 20 and print results. Do this using a while loop, then a for loop. For the  for loop, you may want to use the [range](https://docs.python.org/3.6/library/functions.html#func-range) function.

## zip - challenging
You can loop over more than one counter variable in a single for loop. Search the web on how to do this. Now, loop over the elements of tuple (1,2,3,4) and lists ['a','b','c',999] and [2,4,16,256] simultaneously by zipping them (remember the zip function!)

## Print primes
Print prime numbers between 2 and 100.

First do this with while loops, then with for loops. You'll also need conditional statements.

Hint: you may want to use break.

## Define a dictionary
Define a dictionary called colors where values Red Blue Green Purple Yellow White Magenta and Orange are represented by their initial letters as keys. Print the dictionary and the dictionary's length.

## Add a value
Add Black to the colors dictionary with the same method as described before and print the dictionary and it's length.

## Looping with dictionaries
Create a dictionary with at least 5 entries. Use a for loop to loop through the dictionary (e.g. for i in my_dict:). Print the value of the loop variable (i). What gets printed?

## Deleting dictionary entries
To delete an element from dictionary del is used. Search the internet to find the usage of del. Delete the value with the fish key from the dictionary {'horse':1, 'dog':2, 'fish':3, 'bird':4, 'cat':5, 'monkey':6} and print the new dictionary

## Copying and Updating
Search the internet for available methods of dictionaries. Then:

* Copy the dictionary  {'horse':1, 'dog':2, 'fish':3, 'bird':4, 'cat':5, 'monkey':6} to another dictionary using copy method and print the result
* Add {'eagle':7,'zebra':8} to the previous dictionary using update method and print the result
* Empty the dictionary using clear method and print the result

## Temperature Conversion - challenging
Write a python code that can convert between celsius & fahrenheit. Define the temperature as a string such as '102.4F' or '23C'. If the initial temperature is not properly defined print 'Error in entered temperature'.

The conversion equation is: F = C * (9/5) + 32

Expected output should look like the following depending on your initial entry:

60C is 140.0 in Fahrenheit

24F is -4.444 in Celsius

## Fibonacci - challenging
Write a python code to print out the numbers in [Fibonacci](https://en.wikipedia.org/wiki/Fibonacci_number) series between 0 to 100. Try to use as few lines of code as possible.

## Write a Function: Absolute Difference - Challenging
Write a function that returns the absolute value of one number minus a second number (look up the function for absolute value if needed). Call it twice from another Jupyter cell, switching the order of the two numbers that you pass to the function, and write an if/else statement that prints out if the two values returned by the function are equal.

## Write a Function: Capitalize
Write a function that takes a list of six words and prints each word, but with every other word in all caps.

## Modify Function
Copy your code for the above exercise and modify it so the function returns a new list (don't modify the supplied list). Save the output from the function into a new list variable which has every other word capitalized.

## Write a Function: Remove Long Words
Write a function to remove every word that has more than numchar (a function argument) letters from a supplied list of words. Set the default value for numchar to 4. Return the values that were removed as a list. Call the function with and without specifying the value of numchar.

If you need more information on default values and optional arguments, see [http://www.diveintopython.net/power_of_introspection/optional_arguments.html](http://www.diveintopython.net/power_of_introspection/optional_arguments.html)


## Write a Function: Unique List Elements
Write a Python function that takes a list and returns a new list with unique elements of the first list.


## Write a Function: Reverse a String
Write a function to reverse a string (don't just use the built-in function).


## Write a Function: Squares
Write a function to create and print a list where the values are square of numbers between 1 and 15

## Manipulate the csv 1
From the SAFI_results.csv file extract all of the records where the `C01_respondent_roof_type` (index 18) has a value of `'grass'` and the `C02_respondent_wall_type` (index 19) has a value of `'muddaub'` and write them to a file. Within the same program write all of the records where `C01_respondent_roof_type` (index 18) has a value of `'grass'` and the `C02_respondent_wall_type` (index 19) has a value of `'burntbricks'` and write them to a separate file. In both files include the header record.

## Manipulate the csv 2

1. Create a dictionary called `dict_roof_types` with initial keys of `type1` and `type2` and give them values of 1 and 3.
2. Add a third key `type3` with a value of 6.
3. Add code to check if a key of `type4` exists. If it does not add it to the dictionary with a value of 1 if it does, increment its value by 1
4. Add code to check if a key of `type2` exists. If it does not add it to the dictionary with a value of 1 if it does, increment its value by 1
5. Print out all of the keys and values from the dictionary
