# Part 2 Python Practice

These are the solutions for additional practice exercises.  

## List Functions
We can quickly identify the smallest or largest items in a list with the min() and max() functions. Find out how to use these function from the web and then use them to identify the maximum and minumum elements of the list [-3,-2,-1,0,1,2,3,4,5,6,7]

```python
my_list = [-3,-2,-1,0,1,2,3,4,5,6,7]
print("Largest item in my_list is", max(my_list))
print("Smallest item in my_list is", min(my_list))
```

Largest item in my_list is 7

Smallest item in my_list is -3

## Tuple Functions
Use min() and max() functions to identify the maximum and minumum elements of the tuple {-3,-2,-1,0,1,2,3,4,5,6,7}

```python
my_tuple = (-3,-2,-1,0,1,2,3,4,5,6,7)
print("Largest item in my_tuple is", max(my_tuple))
print("Smalles item in my_tuple is", min(my_tuple))
```
Largest item in my_tuple is 7

Smallest item in my_tuple is -3

## List slicing practice
Define variable my_list as [1,2,3,5,7,11]. Is my_list[3::-1] the same as my_list[3:0:-1]. Why or why not?

```python
my_list=[1,2,3,5,7,11] 
print(my_list[3::-1]) 
print(my_list[3:0:-1])
```
[5, 3, 2, 1]

[5, 3, 2]

When indexing a list with [start : end : stride] the end element is not included, however an omitted index is equivalent to the end of the list (positive stride) or the beginning of the list (negative stride).

## "in" operator
We can use the "in" operator to test if a list contains a particular value. Look up how to use "in" operator on the web and determine if the following values in the lists [1,2,3,4], [0, 2, 3], and [-3,-2,-1,0,1,2,3,4,5,6,7,8,9,10]. (You may want to define variables for these lists first.)

* integer 1
* string "10.0"
* boolean True
* boolean False

```python
my_list=[1, 2, 3, 4]
easy_list=[0, 2, 3]
long_list=[-3,-2,-1,0,1,2,3,4,5,6,7,8,9,10]

print("Is 1 in these lists?")
print(1 in my_list)
print(1 in easy_list)
print(1 in long_list)

print("Is '10.0' in these lists?")
print("10.0" in my_list)
print("10.0" in easy_list)
print("10.0" in long_list)

print("Is True in these lists?")
print(True in my_list)
print(True in easy_list)
print(True in long_list)

print("Is False in these lists?")
print(False in my_list)
print(False in easy_list)
print(False in long_list)
```

Is 1 in these lists?

True

False

True

Is '10.0' in these lists?

False

False

False

Is True in these lists?

True

False

True

Is False in these lists?

False

True

True

## Quote characters
Is there any difference between strings S1, S2, S3, S4 defined below? Print their lenghts (i.e. the number of characters for a string) with len() function to check.

```python
S1='a string'
S2="a string"
S3="""a string"""
S4="""a string
"""
print(S1)
print(S2)
print(S3)
print(S4)
```
a string

a string

a string

a string

```python
print(len(S1))
print(len(S2))
print(len(S3))
print(len(S4))
```
8

8

8

9

## Sort and reverse
On the web, search for sort and reverse methods for lists. Apply these methods to list [9.02,20.4,-4,67,2,34,34.1,0]

* First, order the elements in the list from the smallest to the largest using sort methods
* Second, use the reverse method to order the list from the largest to the smallest

```python
my_list=[9.02,20.4,-4,67,2,34,34.1,0]
my_list.sort()
my_list
```
[-4, 0, 2, 9.02, 20.4, 34, 34.1, 67]

```python
my_list.reverse()
my_list
```
[67, 34.1, 34, 20.4, 9.02, 2, 0, -4]

Note that the `sort` and `reverse methods` of a list object modify its order permanently. Use the `sorted()` and `reversed()` functions if you don't want to modify the list.

## Reverse Sort
Use only the sort method get the list [9.02,20.4,-4,67,2,34,34.1,0] sorted from the largest to the smallest. (Tip: sort method accepts a reverse parameter)

```python
my_list=[9.02,20.4,-4,67,2,34,34.1,0]
print(my_list)
my_list.sort(reverse=True)
my_list
```
[9.02, 20.4, -4, 67, 2, 34, 34.1, 0]

[67, 34.1, 34, 20.4, 9.02, 2, 0, -4]

## Sorting Tuples
Can you apply the same sort and reverse methods to the tuple (9.02,20.4,-4,67,2,34,34.1,0)? Trying is the best way to answer!

```python
my_tuple = (9.02, 20.4, -4, 67, 2, 34, 34.1, 0)
print(my_tuple, type(my_tuple))
```
(9.02, 20.4, -4, 67, 2, 34, 34.1, 0) <class 'tuple'>

```python
my_tuple.sort()
```
---------------------------------------------------------------------------

AttributeError                            Traceback (most recent call last)

<ipython-input-15-bce961af8708> in <module>()

----> 1 my_tuple.sort()

AttributeError: 'tuple' object has no attribute 'sort'

Tuple type is unhashable (i.e. cannot be changed) so has no sort or reverse methods.

## String Functions - Challenging
Look up the [string formatting syntax](https://docs.python.org/3.6/library/string.html#format-string-syntax).

Define variable errorrate as .020456. Print val as part of a string with two decimal digits and a percentage using the string formatting syntax so that the output looks like:

Error rate: 2.05%

```python
errorrate=.020456
print('Error rate: {:.2%}'.format(errorrate))
```
Error rate: 2.05%

## if/elif/else basics
Write a small python code where you check if a variable with a numeric value is negative, positive, or zero and report solution by print.

```python
num = 8

if num < 0:
    print(num, "is negative")
elif num > 0:
    print(num, "is positive")
else:
    print('zero')
```
8 is postive

## while loop
Use while loop to print integers between 5 and 12, excluding limits (i.e. 5 and 12)

```python
t = 6
while 5 < t <12:
    print(t)
    t += 1
```
6

7

8

9

10

11

## while loop factorial - challenging
Using a while loop, write a short python script to compute 34! (the factorial of 34: n! = [n*(n-1)*(n-2)*...*2])

```python
t = 2
n_factorial = 1
while t <= 34:
    n_factorial = n_factorial*t
    t+=1

print(n_factorial)
```
295232799039604140847618609643520000000

## for loop factorial - challenging
Write the same script (i.e. calculating 34!) using a for loop and the range function.

* Search the web for range function and its usage
* Test your understanding by constructing for loops to print the values in range(7), range(1,7), range(1,7,2)
* Construct the for loop with appropriate use of the range function to calculate n!

```python
for t in range(7):
    print(t)
```
0

1

2

3

4

5

6

```python
for t in range(1,7):
    print(t)
```
1

2

3

4

5

6

```python
for t in range(1,7,2):
    print(t)
```
1

3

5

```python
n_factorial = 1
for t in range(1,35):
    n_factorial = n_factorial*t
    
print(n_factorial)
```
295232799039604140847618609643520000000

## More looping
Write a script that divides 50 by each integer between 1 and 20 and print results. Do this using a while loop, then a for loop. For the  for loop, you may want to use the [range](https://docs.python.org/3.6/library/functions.html#func-range) function.

```python
# while loop
t = 1
while t <= 20:
    print(50/t)
    t+=1
```
50.0

25.0

16.666666666666668

12.5

10.0

8.333333333333334

7.142857142857143

6.25

5.555555555555555

5.0

4.545454545454546

4.166666666666667

3.8461538461538463

3.5714285714285716

3.3333333333333335

3.125

2.9411764705882355

2.7777777777777777

2.6315789473684212

2.5

```python
# for loop
for i in range(1,21):
    print(50/i)
```
50.0

25.0

16.666666666666668

12.5

10.0

8.333333333333334

7.142857142857143

6.25

5.555555555555555

5.0

4.545454545454546

4.166666666666667

3.8461538461538463

3.5714285714285716

3.3333333333333335

3.125

2.9411764705882355

2.7777777777777777

2.6315789473684212

2.5

## zip - challenging
You can loop over more than one counter variable in a single for loop. Search the web on how to do this. Now, loop over the elements of tuple (1,2,3,4) and lists ['a','b','c',999] and [2,4,16,256] simultaneously by zipping them (remember the zip function!)

```python
a = (1,2,3,4)
b = ['a','b','c',999]
c = [2,4,16,256,88]

for i,j,k in zip(a,b,c): 
    print(i,j,k)
```
1 a 2

2 b 4

3 c 16

4 999 256

## Print primes
Print prime numbers between 2 and 100.

First do this with while loops, then with for loops. You'll also need conditional statements.

Hint: you may want to use break.

```pythhon
n=100 # not necessary to define 100 as a variable, but it makes it easy to update code for another number
i = 2
while i<=n:
    prime=True
    j=2
    while 2<=j<i:
        if(i%j == 0):
            prime=False
            break
        j+=1
    if(prime==True):
        print(i)
    i+=1
```
2

3

5

7

11

13

17

19

23

29

31

37

41

43

47

53

59

61

67

71

73

79

83

89

97

```python
n=100 # not necessary to define 100 as a variable, but it makes it easy to update code for another number
for i in range(2, n+1):
    for j in range(2, i):
        if(i%j==0):
            break
    else:
        print(i)
```
2

3

5

7

11

13

17

19

23

29

31

37

41

43

47

53

59

61

67

71

73

79

83

89

97

## Define a dictionary
Define a dictionary called colors where values Red Blue Green Purple Yellow White Magenta and Orange are represented by their initial letters as keys. Print the dictionary and the dictionary's length.

```python
colors = {
    'R': 'Red',
    'B': 'Blue',
    'G': 'Green',
    'P': 'Purple',
    'Y': 'Yellow',
    'W': 'White',
    'O': 'Orange',
}
print(colors)
len(colors)
```
{'R': 'Red', 'B': 'Blue', 'G': 'Green', 'P': 'Purple', 'Y': 'Yellow', 'W': 'White', 'O': 'Orange'}

7

## Add a value
Add Black to the colors dictionary with the same method as described before and print the dictionary and it's length.

```python
colors['B']='Black'
print(colors)
len(colors)
```
{'R': 'Red', 'B': 'Black', 'G': 'Green', 'P': 'Purple', 'Y': 'Yellow', 'W': 'White', 'O': 'Orange'}

7

**What happened?** We can only have one value per key. We overwrote the B key with a new value. If you want to store more than one value for a given key, you have to put them in a list.

## Looping with dictionaries
Create a dictionary with at least 5 entries. Use a for loop to loop through the dictionary (e.g. for i in my_dict:). Print the value of the loop variable (i). What gets printed?

```python
my_dict={'horse':1, 'dog':2, 'fish':3, 'bird':4, 'cat':5, 'monkey':6}
for i in my_dict:
    print(i)
```
horse

dog

fish

bird

cat

monkey

If you use a for loop with a dictionary, the counter variable is set to each key. In this case, they printed in order, but order is not guaranteed and should be considered random.

## Deleting dictionary entries
To delete an element from dictionary del is used. Search the internet to find the usage of del. Delete the value with the fish key from the dictionary {'horse':1, 'dog':2, 'fish':3, 'bird':4, 'cat':5, 'monkey':6} and print the new dictionary

```python
dictionary_01={'horse':1, 'dog':2, 'fish':3, 'bird':4, 'cat':5, 'monkey':6}

del dictionary_01['fish']
print(dictionary_01)
```
{'horse': 1, 'dog': 2, 'bird': 4, 'cat': 5, 'monkey': 6}

## Copying and Updating
Search the internet for available methods of dictionaries. Then:

* Copy the dictionary  {'horse':1, 'dog':2, 'fish':3, 'bird':4, 'cat':5, 'monkey':6} to another dictionary using copy method and print the result
* Add {'eagle':7,'zebra':8} to the previous dictionary using update method and print the result
* Empty the dictionary using clear method and print the result

```python
animals={'horse':1, 'dog':2, 'fish':3, 'bird':4, 'cat':5, 'monkey':6}
animals_copy=animals.copy()
print(animals_copy)
```
{'horse': 1, 'dog': 2, 'fish': 3, 'bird': 4, 'cat': 5, 'monkey': 6}

```python
animals_delta={'eagle':7,'zebra':8}
animals.update(animals_delta)
print(animals)
```
{'horse': 1, 'dog': 2, 'fish': 3, 'bird': 4, 'cat': 5, 'monkey': 6, 'eagle': 7, 'zebra': 8}

```python
animals.clear()
print(animals)
```
{}

## Temperature Conversion - challenging
Write a python code that can convert between celsius & fahrenheit. Define the temperature as a string such as '102.4F' or '23C'. If the initial temperature is not properly defined print 'Error in entered temperature'.

The conversion equation is: F = C * (9/5) + 32

Expected output should look like the following depending on your initial entry:

60C is 140.0 in Fahrenheit

24F is -4.444 in Celsius

```python
temp = '60C'
degree = float(temp[:-1])
i_convention = temp[-1]

if i_convention == "C":
  result = ((9 * degree) / 5) + 32
  o_convention = "Fahrenheit"
elif i_convention == "F":
  result = (degree - 32) * 5 / 9
  o_convention = "Celsius"
else:
  print("Input proper convention.")
  quit()
print("The temperature", temp, "is", result, "in", o_convention,)
```
The temperature 60C is 140.0 in Fahrenheit

## Fibonacci - challenging
Write a python code to print out the numbers in [Fibonacci](https://en.wikipedia.org/wiki/Fibonacci_number) series between 0 to 100. Try to use as few lines of code as possible.

```python
i,j=0,1

while j<=100:
    print(j)
    i,j = j,i+j
```
1

1

2

3

5

8

13

21

34

55

89

## Write a Function: Absolute Difference - Challenging
Write a function that returns the absolute value of one number minus a second number (look up the function for absolute value if needed). Call it twice from another Jupyter cell, switching the order of the two numbers that you pass to the function, and write an if/else statement that prints out if the two values returned by the function are equal.

```python
def num_between(a,b):
    difference = abs(a - b)    
    return(difference)
```
```python
a = 3
b = 7
diff_ab = num_between(a,b)
diff_ba = num_between(b,a)
if diff_ab == diff_ba:
    print("the function is correct, the values are equal")
else:
    print("the function is in error, the values aren't equal")
```
the function is correct, the values are equal

## Write a Function: Capitalize
Write a function that takes a list of six words and prints each word, but with every other word in all caps.

```python
def cap_every_other(my_list):
    counter=0
    for word in my_list:
        if counter%2==0:
            print(word.upper())
        else:
            print(word)
        counter = counter+1
    return
```
```python
words = ("yellow", "green", "blue", "orange", "white", "black")
cap_every_other(words)
```
YELLOW

green

BLUE

orange

WHITE

black

## Modify Function
Copy your code for the above exercise and modify it so the function returns a new list (don't modify the supplied list). Save the output from the function into a new list variable which has every other word capitalized.

```python
def cap_every_other_new(my_list):
    new_list=[]
    counter=0
    for word in my_list:
        if counter%2==0:
            new_list.append(word.upper())
        else:
            new_list.append(word)
        counter = counter+1
    return(new_list)
```
```python
words = ["January", "February", "April", "May", "June", "July"]
better_words = cap_every_other_new(words)
print(better_words)
print(words) ## should be unchanged
```
['JANUARY', 'February', 'APRIL', 'May', 'JUNE', 'July']

['January', 'February', 'April', 'May', 'June', 'July']

## Write a Function: Remove Long Words
Write a function to remove every word that has more than numchar (a function argument) letters from a supplied list of words. Set the default value for numchar to 4. Return the values that were removed as a list. Call the function with and without specifying the value of numchar.

If you need more information on default values and optional arguments, see [http://www.diveintopython.net/power_of_introspection/optional_arguments.html](http://www.diveintopython.net/power_of_introspection/optional_arguments.html)

```python
def rem_big_words(my_list, numchar=4):
    remove_these=[]
    for word in my_list:
        if (len(word)> numchar):
            remove_these.append(word)
    # remove in a separate loop, because you'll get errors if you change my_list while iterating through it
    for word in remove_these: 
        my_list.remove(word)
    return(remove_these)
```
```python
months = ["January", "February", "March","April", "May", "June", "July",
          "August", "September","October","November","December"]
long_months=rem_big_words(months)
print(months)
print(long_months)
print(rem_big_words(long_months, numchar=5))
```
['May', 'June', 'July']

['January', 'February', 'March', 'April', 'August', 'September', 'October', 'November', 'December']

['January', 'February', 'August', 'September', 'October', 'November', 'December']

## Write a Function: Unique List Elements
Write a Python function that takes a list and returns a new list with unique elements of the first list.

```python
def uniq_list(my_list):
    # The simplest way to do this is simply `return set(my_list)`.

    # However, you can also iterate over each element of `my_list`,
    # using the `in` keyword to test if `unique_list` already contains it.
    
    unique_list = []
    for thing in my_list:
        if thing not in unique_list:
            unique_list.append(thing)
    return unique_list
```
```python
dup_list = [1,1,3,4,4,6,1,5,1,4,4,2]
unique = uniq_list(dup_list)
print(unique)
```
[1, 3, 4, 6, 5, 2]

## Write a Function: Reverse a String
Write a function to reverse a string (don't just use the built-in function).

```python
def string_reverse(stringy):
    reversed_string = ''
    index = len(stringy)
    while index > 0:
        reversed_string += stringy[ index - 1 ]
        index = index - 1
    return reversed_string
```
```python
print(string_reverse('Janna'))
```
annaJ

## Write a Function: Squares
Write a function to create and print a list where the values are square of numbers between 1 and 15

```python
def printValues():
    squares_list = list()
    for num in range(1,16):
        squares_list.append(num**2)
    print(squares_list)

printValues()
```
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121, 144, 169, 196, 225]

## Manipulate the csv 1
From the SAFI_results.csv file extract all of the records where the `C01_respondent_roof_type` (index 18) has a value of `'grass'` and the `C02_respondent_wall_type` (index 19) has a value of `'muddaub'` and write them to a file. Within the same program write all of the records where `C01_respondent_roof_type` (index 18) has a value of `'grass'` and the `C02_respondent_wall_type` (index 19) has a value of `'burntbricks'` and write them to a separate file. In both files include the header record.

~~~python
filename = "SAFI_results.csv"
fr = open(filename, "r")

filename = "SAFI_grass_roof_muddaub.csv"
fw1 = open(filename, "w")
filename = "SAFI_grass_roof_burntbricks.csv"
fw2 = open(filename, "w")

headerline = fr.readline()
fw1.write(headerline)
fw2.write(headerline)

for line in fr:
    if line.split(",")[18] == 'grass' :
        if line.split(",")[19] == 'muddaub' :
            fw1.write(line)
        if line.split(",")[19] == 'burntbricks' :
            fw2.write(line)    
fr.close()
fw1.close()
fw2.close()
~~~

## Manipulate the csv 2

1. Create a dictionary called `dict_roof_types` with initial keys of `type1` and `type2` and give them values of 1 and 3.
2. Add a third key `type3` with a value of 6.
3. Add code to check if a key of `type4` exists. If it does not add it to the dictionary with a value of 1 if it does, increment its value by 1
4. Add code to check if a key of `type2` exists. If it does not add it to the dictionary with a value of 1 if it does, increment its value by 1
5. Print out all of the keys and values from the dictionary


~~~
# 1
dict_roof_types = {'type1' : 1 , 'type2' : 3}

# 2
dict_roof_types['type3'] = 6

# 3
key = 'type4'
if key in dict_roof_types :
    dict_roof_types[key] += 1
else :
    dict_roof_types[key] = 1

# 4
key = 'type2'
if key in dict_roof_types :
    dict_roof_types[key] += 1
else :
    dict_roof_types[key] = 1
 
# 5
for item in dict_roof_types:
    print(item, "=", dict_roof_types[item])
     
~~~


