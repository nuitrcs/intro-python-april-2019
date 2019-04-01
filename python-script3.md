# Python Session 3

This is the material we'll cover during the second afternoon session of the workshop (Day 1 afternoon). As usual, we may deviate a little, but we'll work from this.

Questions for the first afternoon session:

* How can I automate the whole process? 

Objectives for the second part of the afternoon:

* Show Python standard documentation
* Show how to install packages with pip
* Show how to import packages (aliasing, from ___ import ___)
* Show how to read and write a file
* Demonstrate functions pass by reference
* Show calling functions with named arguments
* Show objects with member variables (in addition to methods)

We will continue to work in Spyder and use the Python console.

## Using libraries

The scripts we have created in the first part of the session only exist for the duration of the session in which they have been defined. Running each part as we did is not a problem if all of your code is in a single file.

There are however many (thousands) of useful scripts/functions which other people have written and have made available to all Python users by creating libraries (also referred to as packages or modules) of functions.

You can find out what all of these libraries are and their contents by visiting the main (python.org) site.

We need to go through a 2-step process before we can use them in our own programs.

Step 1. use the `!pip` command from the IPython console (or pip in commandline - which we will cover tomorrow). `pip` is installed as part of the Python install and is used to fetch the package from the Internet and install it in your Python configuration.

pip stands for Python install package and is a commandline function. Because we are using the Anaconda distribution of Python, all of the packages that we will be using in this lesson are already installed for us, so we can move straight on to step 2.

Step 2. In your Python code include an `import package-name` statement. Once this is done, you can use all of the functions contained within the package.

As all of these packages are produced by 3rd parties independently of each other, there is the strong possibility that there may be clashes in function names. To allow for this, when you are calling a function from a package that you have imported, you do so by prefixing the function name with the package name. This can make for long-winded function names so the `import` statement allows you to specify an `alias` for the package name which you must then use instead of the package name.

Tomorrow, we will be importing the `pandas`, but we could also use `csv`, `json`, `numpy` and `matplotlib` modules. We will describe their use as and if we use them.

The code that we could use is shown below
```python
import csv
import json
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
The first two we don’t alias as they have short names. The last three we do. `Matplotlib` is a very large library broken up into what can be thought of as sub-libraries. As we will only be using the functions contained in the `pyplot` sub-library we can specify that explicitly when we import. This saves time and space. It does not effect how we call the functions in our code.

The `alias` we use (specified after the `as` keyword) is entirely up to us. However those shown here for `pandas`, `numpy` and `matplotlib` are nearly universally adopted conventions used for these popular libraries. If you are searching for code examples for these libraries on the Internet, using these aliases will appear most of the time.

[Exercise](python-exercises3.md#aliases)

## Using help

Help is abundant in python as it is one of the most used languages and community is trying to make everyone welcome. 
1. In the interactive python like spyder you could type question mark after the command/function/method e.g. `print?` and it will provide a help if it is available.
2. Another way is to use function `help` - type `help(print)` to get the same as above.
3. Yet another way is to use graphical tools in the upper right corner by default.
4. When there is a python there is a way, you could always use internet to search for whatever problem you might have. I would recommend typing `python problem-that-you-need-help-with` of course by replacing problem-that-you-need-help-with with appropriate content. [Stackoverflow.com](http://www.stackoverflow.com) usually has nice solutions with examples and references to documentation. 

Let's try to solve this exercise using help.
[Exercise](python-exercises3.md#for)

---
## Processing data from a file

teaching: 45 min

exercises: 25 min

Questions:
- "How can I read and write files?"
- "What kind of data files can I read?"

Objectives:
- "Describe a file handle"
- "Use `open()` to open files for reading"
- "Create and open files for writing or appending"
- "Use `close` to close files"
- "Explain what is meant by a record"

Keypoints:
- "Reading data from files is far more common than program 'input' requests or hard coding values"
- "Python provides simple means of reading from a text file and writing to a text file"
- "Tabular data is commonly recorded in a 'csv' file"
- "Text files like csv files can be thought of as being a list of strings. Each string is a complete record"
- "You can read and write a file one record at a time"
- "Python has builtin functions to parse (split up) records into individual tokens"
---

## Reading and Writing datasets

In all of our examples so far, we have directly allocated values to variables in the code we have written before using the variables.

Python has an `input()` function which will ask for input from the user, but for any large amounts of data this will be an  impractical way of collecting data.

The reality is that most of the data that your program uses will be read from a file. Additionally, apart from when you are developing, most of your program output will be written to a file.

In this session we will look at how to read and write files of data in Python.

There are in fact many different approaches to reading data files and which one you choose will depend on such things as the size of the file and the data format of the file.

In this session we will;

* We will read a file which is in .csv (Comma Separated Values) format.
* We will use standard core Python functions to do this
* We will read the file one line at a time ( line = record = row of a table)
* We will perform simple processing of the file data and print the output
* We will split the file into smaller files based on some processing

The file we will be using is only a small file (131 data records), but the approach we are using will work for any size of file. Imagine 131M records. This is because we only process one record at a time so the memory requirements of the programs will be very small. The larger the file the more the processing time required.

Other approaches to reading files will typically expect to read the whole file in one go. This can be efficient when you subsequently process the data but it require large amounts of memory to hold the entire file. We will look at this approach tomorrow when we will work with the Pandas package.

For our examples in this session we are going to use the SAFI_results.csv file. This is available for download [here](https://datacarpentry.org/python-socialsci/data/SAFI_results.csv) and the description of the file is available [here](https://datacarpentry.org/python-socialsci/data/SAFI_results.csv)

The code assumes that the file is in the work directory and we have to make sure it is. 

We will build up our programs in simple steps

### Step 1 - Open the file , read through it and close the file

~~~python
filename = "SAFI_results.csv"
f = open(filename, "r")    # open the file whose name is in filename, the 'r' means we want to read from the file
                           # the open function returns what is called a file handle. we use this to refer to the file
for line in f:             # We use a for loop to iterate through the file one line at a time.
    print(line)            # we simply print the line

f.close()                    # Always close the file at the end.
~~~

~~~output
Column1,A01_interview_date,A03_quest_no,A04_start,A05_end,A06_province,A07_district,A08_ward,A09_village,A11_years_farm,A12_agr_assoc,B11_remittance_money,B16_years_liv,B17_parents_liv,B18_sp_parents_liv,B19_grand_liv,B20_sp_grand_liv,B_no_membrs,C01_respondent_roof_type,C02_respondent_wall_type,C02_respondent_wall_type_other,C03_respondent_floor_type,C04_window_type,C05_buildings_in_compound,C06_rooms,C07_other_buildings,D_plots_count,E01_water_use,E17_no_enough_water,E19_period_use,E20_exper_other,E21_other_meth,E23_memb_assoc,E24_resp_assoc,E25_fees_water,E26_affect_conflicts,E_no_group_count,E_yes_group_count,F04_need_money,F05_money_source_other,F06_crops_contr,F08_emply_lab,F09_du_labour,F10_liv_owned_other,F12_poultry,F13_du_look_aftr_cows,F_liv_count,G01_no_meals,_members_count,_note,gps:Accuracy,gps:Altitude,gps:Latitude,gps:Longitude,instanceID

0,17/11/2016,1,2017-03-23T09:49:57.000Z,2017-04-02T17:29:08.000Z,Province1,District1,Ward2,Village2,11,no,no,4,no,yes,no,yes,3,grass,muddaub,,earth,no,1,1,no,2,no,,,,,,,,,2,,,,,no,no,,yes,no,1,2,3,,14,698,-19.11225943,33.48345609,uuid:ec241f2c-0609-46ed-b5e8-fe575f6cefef
...
~~~

You can think of the file as being a list of strings. Each string in the list is one complete line from the file.

If you look at the output, you can see that the first record in the file is a header record containing column names. When we read a file in this way, the column headings have no significance, the computer sees them as another record in the file.

### Step 2 - Select a specific 'column' from the records in the file

We know that the first record in the file is a header record and we want to ignore it. To do this we call the `readline()` method of the file handle f. We don't need to assign the line that it will return to a variable as we are not going to use it.

As we read the file the line variable is a string containing a complete record. The fields or columns of the record are separated by each other by "," as it is a csv file.

As line is a string we can use the `split()` method to convert it to a list of column values. We are specicically going to select the column which is the 19th entry in the list (remember the list index starts at 0). This refers to the C01_respondent_roof_type column. We are going to examine the different roof types.

~~~python
filename = "SAFI_results.csv"
f = open(filename, "r") # equivalent to with open(filename, "r") as f:

# first line is a header so ignore it
f.readline()

for line in f:
    print(line.split(",")[18])    # index 18, the 19th column is C01_respondent_roof_type

f.close()
~~~

~~~output
grass
grass
mabatisloping
mabatisloping
grass
grass
grass
mabatisloping
...
~~~


Having a list of the roof types from all of the records is one thing, but it is more likely that we would want a count of each type. By scanning up and down the previous output, there appears to be 3 different type, but we will play safe and assume there may be more.

### Step 3 - How many of each different roof types are there?

~~~python
# 1
filename = "SAFI_results.csv"
f = open(filename, "r")

# 2
f.readline()

# 3
grass_roof = 0
mabatisloping_roof = 0
mabatipitched_roof = 0
roof_type_other = 0

for line in f:
# 4
    roof_type = line.split(",")[18]
# 5    
    if roof_type == 'grass' :
        grass_roof += 1
    elif roof_type == 'mabatisloping' :
        mabatisloping_roof += 1
    elif roof_type == 'mabatipitched' :
        mabatipitched_roof += 1
    else :
        roof_type_other += 1
#6
f.close()

#7
print("There are ", grass_roof, " grass roofs")
print("There are ", mabatisloping_roof, " mabatisloping roofs")
print("There are ", mabatipitched_roof, " mabatipitchedg roofs")
print("There are ", roof_type_other, " other roof types")
~~~


~~~output
There are 73 grass roofs
There are 48 mabatisloping roofs
There are 10 mabatipitchedg roofs
There are 0 other roof types
~~~

What are we  doing here?

1. Open the file
2. Ignore the headerline
3. Initialise roof type variables to 0
4. Extract the C01_respondent_roof_type information from each record
5. Increment the appropriate variable
6. close the file
7. Print out the results

Instead of printing out the counts of the roof types, you may want to extract all of one particular roof type to a separate file. Let us assume we want all of the grass roof records to be written to a file.

~~~python
# 1
filename = "SAFI_results.csv"
fr = open(filename, "r")

filename = "SAFI_grass_roof.csv"
fw = open(filename, "w")

for line in fr:
# 2    
    if line.split(",")[18] == 'grass' :
        fw.write(line)

#3
fr.close()
fw.close()
~~~


What are we  doing here?

1. Open the files. Because there are now two files, each has its own file handle: `fr` for the file we read and `fw` for the file we are going to write. (They are just variable names so you can use anything you like). For the file we are going to write to we use `w` for the second parameter. If the file does not exist it will be created. If it does exist, then the contents will be overwritten. If we want to append to an existing file we can use `a` as the second parameter.
2. Because we are just testing a specific field from the record to have a certain value, we don't need to put it into a variable first. If the expression is True, then we use `write()` method to write the complete line just as we read it to the output file.
3. Close the files

In this example we didn't bother skipping the header line as it would fail the test in the if statement. If we did want to include it  we could have added the line

~~~python
fw.write(fr.readline())
~~~

before the for loop

In our example of printing the counts for the roof types, we assumed that we knew what the likely roof types were. Although we did have an `'other'` option to catch anything we missed. Had there been any we would still be non the wiser as to what they  represented. We were able to decide on the specific roof types by manually scanning the list of `C01_respondent_roof_type` values. This was only practical because of the small file size. For a multi-million record file we could not have done this.


We would like a way of creating a list of the different roof types and at the same time counting them. We can do this by using not a Python list structure, but a Python dictionary.



## The Python dictionary structure

In Python a dictionary object maps keys to values. A dictionary can hold any number of keys and values but a key cannot be duplicated.

The following code shows examples of creating a dictionary object and manipulating keys and values.

~~~python
# an empty dictionary
myDict = {}

# A dictionary with a single Key-value pair

personDict = {'Name' : 'Peter'}

# I can add more about 'Peter' to the dictionary

personDict['Location'] = 'Manchester'


# I can print all of the keys and values from the dictionary

print(personDict.items())

# I can print all of the keys and values from the dictionary - and make it look a bit nicer

for item in personDict:
    print(item, "=", personDict[item])

# or all of the keys

print(personDict.keys())

# or all of the values

print(personDict.values())

# I can access the value for a given key

x = personDict['Name']
print(x)

# I can change value for a given key

personDict['Name'] = "Fred"
print(personDict['Name'])

# I can check if a key exists

key = 'Name'

if key in personDict :
    print("already exists")
else :
    personDict[key] = "New value"
~~~


~~~output
dict_items([('Location', 'Manchester'), ('Name', 'Peter')])
Location = Manchester
Name = Peter
dict_keys(['Location', 'Name'])
dict_values(['Manchester', 'Peter'])
Peter
Fred
already exists
~~~

We are now in a position to re-write our count of roof types example without knowing in advance what any of the roof types are.

~~~python
# 1
filename = "SAFI_results.csv"
f = open(filename, "r")

# 2
f.readline()

# 3
dict_roof_types = {}

for line in f:
# 4
    roof_type = line.split(",")[18]
# 5    
    if roof_type in dict_roof_types :
        dict_roof_types[roof_type] += 1
    else :
        dict_roof_types[roof_type] = 1
# 6
f.close()

# 7

for item in dict_roof_types:
    print(item, "=", dict_roof_types[item])
~~~


~~~output
grass = 73
mabatipitched = 10
mabatisloping = 48
~~~


What are we  doing here?

1. Open the file
2. Ignore the headerline
3. Create an empty dictionary
4. Extract the C01_respondent_roof_type information from each record
5. Either add to the dictionary with a value of 1 or increment the current value for the key by 1
6. close the file
7. Print out the contents of the dictionary


You can apply the same approach to count values in any of the fields/columns of the file.

[Exercise](python-exercises3.md#open)

## How do the functions behave
### Function pass by reference
Now that we have introduced plenty of basic functions let's try to understand what is going on under the hood.  You have already used a number of functions from the core Python language. Python uses a pass by the reference by default. What do I mean by that.
Examine what happened when you wanted to print a content of the variable. You have typed `print(variable)` and it was printed whatever variable is referenced to. 

Print doesn't change the referenced variable, it just prints the contents. Now, let's dig a bit deeper and examine what happens when you use a function sort which does change the referenced variable by sorting it. Let that variable be the list.
```python
mylist = [3, 6, 1, 2, 5, 7]
print('Before sorting\n', mylist)
mylist.sort()
print('After sorting\n', mylist)
```
```output
Before sorting
 [3, 6, 1, 2, 5, 7]
After sorting
 [1, 2, 3, 5, 6, 7]
```
Function sort acted upon mylist and sorted the elements. You could say, yes, that's what I wanted. But, be careful what you wish for. Where is your original data? mylist is changed!

### Calling functions with positional and named arguments
Let's take a look at another interesting python feature named arguments. We used open to open files. We did open files simply by 
```python
filename = "SAFI_results.csv"
f = open(filename, "r")
```
If we wanted to read the file, or with "w" if wanted to write to the file. We used positional arguments here. Namely, function `open` assumes that first argument would be what we want to open, second argument would be how we would like it opened. To get more arguments in the mix let's put the information whether we want our file buffered or not. Buffering is on if we put any number other than 0, off if we put 0. CSV file should be opened as buffered, so let's put 1 there.

```python
filename = "SAFI_results.csv"
f = open(filename, "r", 1)
```

Let's take a look at the help for the function `open`. Notice the following line
```output
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```
there is a lot more arguments and all but the first one are given default values. Also, notice that each argument is named. Therefore, we could use that to see what would happen if we used named arguments instead of positional arguments.

```python
filename = "SAFI_results.csv"
f = open(file=filename, mode = "r", buffering = 1)
```

It works, right? Now, let's try to mix the order of the named arguments:

```python
filename = "SAFI_results.csv"
f = open(buffering = 1, mode = "r", file=filename)
```

It still works!

However, if we try to mix the order without naming the arguments:

```python
filename = "SAFI_results.csv"
f = open(1, "r", filename)
```
We get all kinds of errors since positional arguments are expected.

## A bit more about objects
Python is an object oriented programming language. Unlike procedure oriented programming, where the main emphasis is on functions, object oriented programming stress on objects.

Object is simply a collection of data (variables) and methods (functions) that act on those data. And, class is a blueprint for the object. 

So far we focused on methods, but objects have member variables. One of the examples is dictionary that you have seen this morning and keys and values are the variables of the object. Note, methods are callable attributes, nothing more.

## Key Points

* Functions are used to create re-usable sections of code
* Using parameters with functions make them more flexible
* You can use functions written by others by importing the libraries containing them into your code
* Reading data from files is far more common than program ‘input’ requests or hard coding values
* Python provides simple means of reading from a text file and writing to a text file
* Tabular data is commonly recorded in a ‘csv’ file
* Text files like csv files can be thought of as being a list of strings. Each string is a complete record
* You can read and write a file one record at a time
* Python has builtin functions to parse (split up) records into individual tokens
* Python functions use pass by reference - be careful about that
* Arguments in the function could be positional and named
* Objects are simply a collection of data (variables) and methods (functions) that act on those data
