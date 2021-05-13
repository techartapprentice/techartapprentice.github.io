---
title: "Core Concepts"
permalink: /python/core/
excerpt: "How to quickly install and setup Minimal Mistakes for use with GitHub Pages."
last_modified_at: 2020-07-27
toc: true
---

## Why Python?

Python is an extremely versatile language that is incredibly versatile that's suited for developing a wide variety of tools and applications. It’s also a language that is widely supported across a range of DCC applications like Maya, Unreal Engine, Houdini, Substance & Marmoset.

<center><img src="/assets/images/005_python_core/python-logo-master-v3-tm.png" alt="python" width="200"/></center>

It's an interpreted high-level object-oriented language. This means that you don’t have to compile your code manually for it to work. It also has a vast community across multiple fields, all of whom have created vast libraries and tools to further extend the language. These are just some of the use cases where Python is integrated:

- VFX/Game Development
- Software Development
- Web/Internet Applications
- Data Sciences & Analysis
- Scientific & Numeric Computing
- Education
- Finance & Insurances
- Machine Learning

### Which Version?

There are several versions of Python that are currently being used. However, as of 1st of January 2020, the most widely used and supported version of Python, 2.7, has reached its end of life, meaning there will no longer be any official support or new features rolled into Python 2. Instead, we’ll be officially moving to Python 3. This does not mean that Python 2.7 just vanished and disappeared overnight. There are still a ton of applications, frameworks, and tools that rely on Python 2.7 and it will take time for everything to be updated to Python 3. There are currently two popular flavours of Python: 3.7 & 3.8.

The version that the VFX Industry has opted to go with is 3.7. Originally, the shift to Python 3 was meant to take place in CY2019, but due to lack of support for Qt 5.6 and PySide 2, the move was postponed to CY2020. The VFX industry has making the switch with Side Effects, Autodesk & Unreal offering Python 3 as the default python version in their most recent application updates. You can follow the latest updates via the VFX Reference Platform.

To download Python, head over to the official Python website to find all the different versions and release notes. This post will be using Python 3 as that is the version going forward.

## Variables

Variables are a way of storing data in memory so that they can be manipulated. They act as containers for holding certain types of data. You can assign a certain type of value to a variable or you can have that variable affect something within the program.

Most other programming languages require that you declare a data type explicitly before assigning a variable name and value. However, in Python, it’s the values that are assigned which determine the type of data that variable is.

For example:

{% highlight python linenos %}

# Example of a variable

full_name = 'John Smith'

# This is also a variable

age = 27
{% endhighlight %}

As per the PEP8 standards, variables should be written using lowercase letters or words, with any separate words using snake_case. Variables names should also be written in such a way that it makes sense what that variable is doing. You should be able to look at your variables and have a rough idea of what the code is doing. In other words, avoid names that are abstract or singular.

While the PEP8 standard serves as a useful style guide for writing Python, it should not be treated as a hard and fast rule. They exist as a means to provide consistency and improve readability. Use them where it makes sense, break them if it means maintaining backwards compatibility.

#### Assigning & changing variables

Variables can be assigned by simply entering a value after an equal sign, next to the variable name. Python is a type-inferred language, which means that, unlike C# or C++, you don’t have to declare the variable type before assigning the value. It also means that a variable may store one type of data now and later on, hold a different type of data. Changing the variable assignment can also be done relatively easily by assigning a different value on a different line to the same variable.

{% highlight python linenos %}

# Assigning a variable

full_name = '中村京'

# Changing a variable's assigned value

full_name = '水木奈々'
{% endhighlight %}

In the example, we first assigned the variable of full_name to 中村京. Then we changed the value to be 水木奈々.

Another way of changing variable types is by using the built-in functions. This is known as type conversion and is a common way of passing data through your code. The type() function lets us query what type of data our variable is. While the float(), str() and int() functions, lets us convert our data into floats, strings and integers respectively.

{% highlight python linenos %}

# Example of declaring different data types in variables

int_example = 100
string_example = 'foo'
float_example = 1.25
boole_example = True

# Printing out the different data types

print(type(int_example))
print(type(string_example))
print(type(float_example))
print(type(boole_example))

# Convertion our data from one type to another and printing the results.

print(type(float(int_example)))
print(type(str(float_example)))
print(type(int(boole_example)))
{% endhighlight %}

## Strings

Strings are data types that contain letters &/or words such as node names, file paths, URL’s, etc. They are essentially ways to represent text data. The snippets above contain some examples of strings. Here are a couple more:

{% highlight python linenos %}
url = 'https://www.website.com'
file_path = 'c:/folder/file_name.ext'
country = 'Country name'
node_type = 'mesh'

'This is a string'
"This too is a string"
'''This is also considered a string'''
{% endhighlight %}

Strings can be specified in either single, double, or triple quotes. According to the PEP8 standards, there are no strict rules for deciding which form of quotation to you in your strings. However, it is a good idea to pick a rule and stick to it.

There are several different things that we can do with strings. So much so, that it deserves its own separate post. I’ll run through some of the more common use cases as 90% of the time, this is all that you’ll probably really need.

Certain things have changed in Python 3 such as the way strings are printed and string formatting using f-strings. Printing in Python 3 using the print() function, whereas previously in Python 2, this was not needed.

One of the more common operations when it comes to strings involves manipulation. We can replace strings, add to an existing string (also known as concatenation), subtract and even change the casing. Here are some of the common string operations that you may find yourself running into:

{% highlight python linenos %}
string_example = 'This is a string'
food = 'cake'

# Capitalizes the first letter in a string

string.capitalize()

# Replaces a part of the string with another.

string_example.replace('string', 'new world')

# Makes a string entirely uppercase.

string_example.upper()

# Makes a string entirely lowercase.

string_example.lower()

# Capitalizes the first letter of every word.

string_example.title()

# Strips out any white spacing from the string.

string_example.strip()

# Strips out any white spacing from the left side of the string.

string_example.lstrip()

# Strips out any white spacing from the right side of the string.

string_example.rstrip()

# Find the index of the first given character or sequence of characters in the string.

string_example.find('is')

# Checks if the given character or sequences of characters is in the string.

print('This' in string_example)

# Checks if the given character or sequence of characters is not in the string.

print('Foo' not in string_example)

# Returns a boole if a string is entirely in the uppercase or not.

string_example.isupper()

# Returns a boole if a string is entirely in the lowercase or not.

string_example.islower()

# Turns a string to uppercase. Returns a boole if a string is entirely in uppercase.

string_example.upper().isupper()

# Prints out the value/character based on the assigned index.

print(string_example[1])

# Returns the index value of the given supplied character or sequence.

print(string_example.index('string'))

# Printing the length of a given string.

print(len(food))

# Culls the first character from the left in a string. Also known as slicing.

print(food[1:])

# Slices the last character or the first from the rear from a string.

print(food[:-1])

# Slices the first and last character of a string.

print(food[:-1])

# Prints the first character in a string.

print(food[:1])

# Prints the first two characters in a string.

print(food[:2])

# Prints a specific range of characters in a string.

print(food[2:4])
{% endhighlight %}

## Comments & Docstrings

Comments are a way of documenting your code, making it clear what your code is doing. It is important to document your code so that if you have to return to it at a later date, or if someone else has to read your code, they will have an understanding of it, without spending hours or days trying to figure it out. There are several things to keeps in mind when writing comments:

- Keep it simple and to the point
- Use complete sentences wherever possible
- If there is a change in the code, be sure that the comments are - kept up to date
- Use block comments if it feels like the comments are going to be - fairly lengthy.
- Inline comments and docstrings should be kept relatively short
- Comments in Python are denoted by a # and comes in 3 flavours.

- Inline comments
- Block/multi-line comments
- Docstrings

---

### INLINE COMMENTS

Inline comments are comments that exist within the same line as the code. This should be used sparingly as it is often distracting and looks quite messy is spread over long pages of code.

{% highlight python linenos %}
print('Hello, strings!') # This is an inline comment
{% endhighlight %}

Generally, it is better and cleaner to have single-line comments above the piece of code/function instead but it does add an extra line to your code.

{% highlight python linenos %}

# This is a comment

print('Hello, strings!')
{% endhighlight %}
Use whichever you prefer but stick to it. Consistency is key!

---

### BLOCK COMMENTS

Block comments are a way of documenting your code, where a much more lengthy explanation of the code is required. Unlike most other programming languages, however, Python does not support multi-line comments right out of the box.

There are generally two ways of writing block comments in Python:

Have each line be treated as a single line comment with a # in front of each line

{% highlight python linenos %}

# This is a 'block comment' in Python,

# using several single-line comments.

name = 'John Smith'
print (name)
{% endhighlight %}

Contain your block comments in triple-quotes
{% highlight python linenos %}
'''
This is also a 'block comment' in Python,
but using triple quotes
'''
name = 'John Smith'
print (name)
{% endhighlight %}

The latter looks better but there is a risk involved depending on where these comments are place. If the block comments are placed after a function or class declaration, or at the start of the file/module, it becomes a docstring.

---

### DOCSTRINGS

Docstrings are strings that provide human-readable documentation for your Python modules, classes and functions. They are a special kind used by the Python compiler for creating documentation. Python packages such as sphinx can interpret the docstrings in your code, creating documentation, which you can then serve up on your website or via services such as readthedocs.

Docstrings should be included in all public functions, classes and modules. Like comments, docstrings should be concise and easy to maintain but elaborate enough so that you have a good understanding of the code’s purpose. And similar to comments, docstrings can be single-line or they can be multiline.

PEP8 recommends that docstrings should be using triple double-quotes. I personally prefer single quotes as I think it looks a lot neater but there are good reasons for using double vs single quotes, such as escape sequences or quotations within strings.

Here’s a single line docstring used within a function:

{% highlight python linenos %}
def group*each():
'''Takes the selected nodes and groups the selection'''
sel = pm.ls(sl=True)
for g in sel:
pm.group(g, name='sm*')
group_each()
{% endhighlight %}

Here’s an example of a multi-line docstring:

{% highlight python linenos %}
'''A single line summary of the code

A further explanation of the docstring. Here, you can elaborate further on the details and intricacies of the code.
Note that the summary line is on the same line as the opening quotes.
Also, note that the summary line and the explanation are separated by a space.
'''

# Convention dictates that a blank line be added after the closing quotes, before the rest of the code.

{% endhighlight %}

The beauty of docstrings is that they can read any parameters, variable and return types for generating documentation. This has led to a few docstring formats being developed. These include:

- reStructured text (reST): The official Python documentation standard. Uses reST syntax highlighting which is similar to Markdown.
- Google Docstrings: Google’s recommended format
- Numpy/SciPy Docstrings: Usable with Sphinx. A combination of reST and Google.

Here are the examples of each of the different formats used inside a class function:

reStructured Text Format(reST):

{% highlight python linenos %}
def function_name(self, arg1):
"""Singe line summary of code.

    A more lengthy explanation of the function code goes
    here. Functions sometimes return a value to be used elsewhere,
    hence a return type is often included within the docstring but
     in this instance, nothing is being returned so, the return
     value is nothing.

    :param arg1: parameter description
    :type arg1: data_type
    :return: no value
    :rtype: none
    """

    self.some_other_variable = type(arg1)
    return

{% endhighlight %}

Google Docstrings:

{% highlight python linenos %}
def function_name(self, arg1):
"""Singe line summary of code.

    A more lengthy explanation of the function code goes
    here. Functions sometimes return a value to be used elsewhere,
    hence a return type is often included within the docstring but
    in this instance, nothing is being returned so, the return
    value is nothing.

    Args:
        arg1 (type): arg description

    Returns:
        no value
    """

    self.some_other_variable = type(arg1)
    return

{% endhighlight %}

Numpy Format:

{% highlight python linenos %}
def function_name(self, arg1):
"""Singe line summary of code.

    A more lengthy explanation of the function code goes
    here. Functions sometimes return a value to be used elsewhere,
    hence a return type is often included within the docstring but
    in this instance, nothing is being returned so, the return
    value is nothing.

    Parameters
    ----------
    arg1 : data_type
           arg description

    Returns
    -------
    no value
    """

    self.some_other_variable = type(arg1)
    return

{% endhighlight %}

Documentation can be accessed through the console by two different ways. Printing using the **doc** attribute or using the help() function. The help function tends to be a little more verbose and simpler.

## Numbers & math operators

Python supports a few different types of number representations:

- Integers
- Floats
- Complex numbers

There are a few other more advanced types including long integers and octals/hex, but those are outside the scope of what I’m covering and are not as common.

{% highlight python linenos %}
float_number = 2.5
integer = 5
complex_number = 45.j
{% endhighlight %}

Python supports all the basic math operations that you may want to apply to numbers.

{% highlight python linenos %}
x = 1 + 1 # Addition
x = 5 – 4 # Subtraction
x = 3.5 _ 2.2 # Multiplication
x = 10 / 1.2 # Division
x = 10 // 3 # Floor
x = 10 \*\* 2 # Power
x = -x # Negation
x = 10 % 3 # Modulus (division remainder)
x += 2 # Add and store the result back in x, same as x = x + 2
x -= 2 # Subtract and store the result back in x
x _= 2 # Multiply and store the result back in x
x /= 2 # Divide and store the result back in x
{% endhighlight %}

Python also supports several other mathematical functions to perform calculations via the math module.

{% highlight python linenos %}
x = abs(x) # Returns the absolute value of x: the position distance between x and 0.
x = ceil(x) # Returns the smallest integer greater than or equal to x.
x = exp(x) # Returns the exponential of x.
x = factorial(x) # Returns the factorial x.
x = floor(x) # Returns the floor of x: the largest integer not greater than x.
x = fmod(x, y) # Returns the remainder when x is divided by y
x = fabs(x) # Returns the absolute value of x.
x = log(x) # Returns the natural logarithm of x, for x> 0.
x = log10(x) # Returns the base-10 logarithm of x.
x = max(x) # Returns the largest item in an iterable.
x = min(x) # Returns the smallest item in an iterable.
x = modf(x) # Returns the fractional and integer parts of x.
x = pow(x) # Returns x raised to the power y.
x = trunc(x) # Returns the truncated integer value of x.
x = round(x, y) # Returns a rounded down float, with the specified number of decimals.
x = sqrt(x) # Returns the square root of x.
x = random(x) # Returns a random float.
{% endhighlight %}
You can also perform standard trigonometric functions within Python.

{% highlight python linenos %}
x = acos(x) # Returns the arc cosine of x, in radians.
x = asin(x) # Returns the arc sine of x, in radians.
x = atan(x) # Returns the arc tangent of x, in radians.
x = atan2(y,x) # Returns the atan of (y/x), in radians.
x = cos(x) # Returns the cosine of x, in radians.
x = hypo(x, y) # Returns the Euclidean norm, sqrt(x*x + y*y).
x = sin(x) # Returns the sine of x radians.
x = tan(x) # Returns the tangent of x radians.
x = degrees(x) # Converts angle x from radians to degrees.
x = radians(x) # Converts angle x from degrees to radians.
{% endhighlight %}

## Boolean Operations

Oftentimes, you will find that you will need to compare the values of different variables. To do this, Python has a series of operators which let us control the flow of our code by returning a True or False value based on a defined condition. These include comparison, logical, identity and membership operators.

### COMPARISON OPERATORS

Comparison operators does what it says, compare two values to create a condition and returns a result

{% highlight python linenos %}
x == y # Checks if x is equal to y
x != y # Checks if x does not equal y
x > y # Checks if x is greater than y
x < y # Checks if x is less than y
x >= y # Checks if x is greater than or equal to y
x <= y # Checks is x is less than or equal to y
{% endhighlight %}

### LOGICAL OPERATORS

Logical operators can be used to combine multiple conditional statements. Often, these will be pairs with comparison operators

{% highlight python linenos %}
x and y # Returns true if both x & y are met
x or y # Returns true if either x or y is true
y not x # True if x is false, False if x is true. Essentially a reverse operation
{% endhighlight %}

###

IDENTITY OPERATORS
Identity operators are used to determine if one statement shares the same identity as another in memory. This actually not the same as ==, where two statements share equal value. Rather, the is operator checks whether both statements refer to the same object.

{% highlight python linenos %}
is # Returns true both statements are the same object
is not # Returns true if both statements are different objects
{% endhighlight %}

### MEMBERSHIP OPERATORS

Membership operators are used to test if a variable exists within a given object, usually either a string, tuple, list, set, or dictionary.

{% highlight python linenos %}
x in y # Returns true if x is found in y
x not in y # Returns true is not found in y
{% endhighlight %}

### ASSIGNMENT OPERATORS

We’ve covered mathematical operators. All, if not a few of them fall into another category known as assignment operators. Assignments operators are a way of assigning values to variables. The most obvious one being =. There are a few which can be considered compound operators where they perform an operation and then assigns the resulting value to the variable.

{% highlight python linenos %}
x = 5 # Assigns x = 5
x += 5 # Same as x = x + 5
x -= 5 # Same as x = x - 5
x _= 5 # Same as x = x _ 5
x /= 5 # Same as x = x / 5
x %= 5 # Same as x = x % 5
x //= 5 # Same as x = x // 5
x **= 5 # Same as x = x ** 5
{% endhighlight %}

## Lists

Lists are a way of storing and organizing groups of data within an array. You can have any number of items within a list and also include more than one data type within a single list. Lists in Python are denoted by [].

{% highlight python linenos %}

# List of fruits

fruits = ['apple', 'kiwi', 'banana', 'grapes']

# List of integers

age = [1, 15, 25, 65]

# List containing mixed data types

combined = ['foo', str(2), True, 1.256]
{% endhighlight %}

You can also have nested lists where you have a list within a list. It’s also possible to contain mixed data types within nested lists.

{% highlight python linenos %}
Example of a tested list
nested_list = ['foo', [a, b, c], [1, 2, 3], [3.14, 0.275, 9.76], True]
{% endhighlight %}

The key thing to remember about lists is that they’re 0 based which means that the index starts with a value of 0. Lists are also mutable, which means they can be edited or have their members changed. There are many that we can perform on a given list.

We can create a list using the list function:

{% highlight python linenos %}

# Creating an empty list

fruits = list()
{% endhighlight %}

Here are some operations and functions that we can do with lists:

{% highlight python linenos %}
fruits = ['apple', 'kiwi', 'banana', 'grapes']

# Prints the index value from the list

print(fruits[0])

# Prints the length of the list

print(len(fruits))

# Prints the last index value from the list or the first item from the end of the list

print(fruits[-1])

# Print the last item by querying the length

print fruits[len(fruits)-1]

# Changing the value of an item in the list based on a given index value

fruits[2] = 'watermelon'

# Changing the third and 4th items

fruits[3:4] = ['peaches', 'jackfruit']

# Removes the last element

print fruits[:-1]

# Prints the values from the list starting with the given index. Also known as list slicing.

print(fruits[2:])

# Slicing a list to print from a range of index values in a given list

print(fruits[1:3])

# Reversing a list via slicing

print(fruits[::-1])

# Extends a list by adding another list to the existing

fruits.extend(['pineapple', 'watermelon', 'mangoes', 'kiwi'])

# Using the + operator to combine concatenate two lists

print (fruits + ['pineapple', 'watermelon', 'mangoes', 'kiwi'])

# Appends a single item to the end of an existing list

fruits.append('peaches')

# Inserts a single list item into a specified index value

fruits.insert(2, 'jackfruit')

# Removes a single item from a list

fruits.remove('kiwi')

# Removes the last item from the list

fruits.pop()

# Deleting an item from the list based on index value

del fruits[2]

# Deleting multiple items from the list

del fruits [2:5]

# Copies an existing list. Editing on the new list does not affect the old one.

new_fruits = fruits.copy()

# Tests for a certain item within a list.

# If there is more than one instance, it prints out the first occurrence.

print(fruits.index('watermelon'))

# Counts the number of instances a specified value appears inside a list

print(fruits.count('kiwi'))

# Sorts a list in ascending order. Does not work if there is more than one type in the list.

fruits.sort()

# Sorts the list in reverse order. Does not work if there is more than one type in the list.

fruits.sort(reverse=True)

# Sorts a list in ascending order into a new list. Does not modify the original.

print(sorted(fruits))

# Sort a list in reverse order into a new list. Does not modify the original

print(sorted(fruits, reverse=True))

# Reverses the order of a list using the reverse function.

fruits.reverse()

# Empties the list

fruits.clear()

# Deleting the entire list

del fruits

# Creates a list from a range of 20 numbers starting from 0.

# The :: indicates a step and therefore prints out every second item in the list starting from the first item

numbers = list(range(20))
print(numbers[::2])

# A quick way of using multiplication to print out a long list of the same item

zeroes = [0] \* 20
print (zeroes)
{% endhighlight %}

There are certain precautions to take when working with lists. If for example, you remove an item from a list and then try to access it, or you’re simply trying to access an item that does not exist inside of a list, Python will return an error.

{% highlight python linenos %}
print(fruits[50])

# Error: list index out of range

# Traceback (most recent call last):

# File "", line 1, in

# IndexError: list index out of range

{% endhighlight %}

This can be quite a common occurrence when working with lists. There are ways of catching these sorts of errors, such as wrapping the function within a try and except or using a conditional to first check if an item exists within the list.

## Tuples

Tuples are similar to lists in that, they are arrays for storing data. And like lists, tuples can contain any number of items and even mixed data types. Similarly, tuples are 0 based. However, the one big difference is that tuples are immutable, meaning, once they’ve been created, they cannot be changed. Use tuples when you know you don’t want the data to change.

{% highlight python linenos %}

# A single tuple

coordinates = (4,5)
{% endhighlight %}

You can also have a list of tuples

{% highlight python linenos %}

# A list of tuples

coordinates = [(4,5), (6,7), (80,34)]
{% endhighlight %}

It is also possible to convert a list into a tuple

{% highlight python linenos %}

# Creating a tuple from a list

coordinate = tuple([1,2])
{% endhighlight %}

Tuples can also be nested

{% highlight python linenos %}

# A nested tuple

coordinate = ((1,2), (10, 5))
{% endhighlight %}

Tuples by all accounts are just another type of list, albeit with more restrictions. That said, it means a few of the behaviours such as indexing and slicing also apply here:

{% highlight python linenos %}
letters = ('s', 'i', 'n', 'g', 'e', 'r')

# Accessing an element inside a tuple via indexing

print (letters[2])

# Negative indexing to access the last tuple element

print (letters[-1])

# Printing the length of a tuple

print (len(letters))

# Accessing a specific range of items inside a tuple

print(letters[1:4])

# Printing the reverse of a tuple

print(letters[::-1])
{% endhighlight %}

## Packing & Unpacking

Within Python, there is a powerful feature known as packing and unpacking, which allows us to take a list or tuple and ‘unpack’ them into separate variables within a single line. Below is an example of unpacking.

{% highlight python linenos %}
birthday = ['November', 9, 2019]
month, date, year = birthday
{% endhighlight %}

Here, we have a list with 3 items in it. We’ve essentially taken the list and for each of the 3 elements, created a separate variable for them. Right now, they are spread across two lines, but we can even unpack them in a single line.

{% highlight python linenos %}
month, date, year = ['November', 9, 2019]
{% endhighlight %}

The above is exactly the same as the previous example. One thing to keep in mind is that the number of variables created has to match the number of elements within the list. Each variable assigned represents each index value. If an element or variable was missing, Python will throw an error.

Here’s the error if the number of variable assignments is less the length of the list:

{% highlight python linenos %}

> > > month, date = ['November', 9, 2019]
> > > Traceback (most recent call last):
> > > File "<stdin>", line 1, in <module>
> > > ValueError: too many values to unpack (expected 2)
> > > {% endhighlight %}

And vice versa

{% highlight python linenos %}

> > > month, date, year = ['November', 9]
> > > Traceback (most recent call last):
> > > File "<stdin>", line 1, in <module>
> > > ValueError: not enough values to unpack (expected 3, got 2)
> > > {% endhighlight %}

There is a built-in mechanism within Python to get around this using the \* symbol.

{% highlight python linenos %}
month, year, \*date = ['November', 2019, 5, 6, 7, 8, 9]
{% endhighlight %}

This bit of code is saying that the first item in the list will be store in the variable month, the second item in the list will be store inside of the variable year and anything after that will be stored in date in a separate list.

The variable with the asterisk does not have to be last, in the list, you can move it around. The key thing here is that the asterisk is placed before the variable. Note that unpacking tuples work in exactly the same way.

{% highlight python linenos %}
month, \*date, year = ('November', 5, 6, 7, 8, 9, 2019)
{% endhighlight %}

While tuples cannot be edited or changed, there is a way around which involves swapping the variables around and unpacking them. Here’s an example

{% highlight python linenos %}
x = 10
y = 11
x, y = y, x
print ('x', x)
print ('y', y)
{% endhighlight %}

Here we have assigned the values 10 & 11 to x & y respectively. We then unpack them into the same variables but here, the values are the reverse of the variable assignments. This means, when we print out those values again, we get the reverse of what we started with.

One cool thing about this is, in situations like this, Python allows the parenthesis usually used to define a tuple, to be left out. It works the same way, regardless.

## Sets

Sets are another type of array in Python for handling data. However, unlike lists and tuples, sets cannot contain duplicate elements. While sets can be modified, a set’s members have to be of an immutable type.

Sets in Python are denoted by a {}. However, you cannot create an empty set by way of using empty {} because Python will recognize those as a dictionary. Instead, the more common approach is to use the set() function, to create a set from an existing list.

{% highlight python linenos %}

> > > x = set([1,1,2,3,4])
> > > x
> > > {1, 2, 3, 4}
> > > {% endhighlight %}

Here, we are creating a set from a range of 5 numbers. Notice how 1 appears twice in the list but the moment we create a set, we are reduced down to a single instance.

We can perform several operations on a set. Keep in mind that set elements have to be immutable, which means you can’t have lists or dictionaries within a set.

{% highlight python linenos %}
first_numbers = {1,2,3,4}
second_numbers = {3, 4, 10, 20, 30, 40}

# Adding an item to a set. Adding items that already exist will have no effect.

second_numbers.add(7)

# Remove an item from a set. An exception will be raised if the item is not in the set.

second_numbers.remove(7)

# Removes an item from a set. However, this will not raise an exception.

second_numbers.discard(7)

# Removes an arbitrary element from a set.

second_numbers.pop()

# Clears a set.

second_numbers.clear()

# Querying the length of a set.

print(len(first_numbers))

# Adding list members to a set. This is not adding the list but the list items.

first_numbers.update([4,5], {7,6,8})

# Joins the elements of two sets.

print (first_numbers | second_numbers)

# Using the union function to join two sets.

first_numbers.union(second_numbers)

# Finds the intersection of two sets. Returns the values that exists in both sets.

print (first_numbers & second_numbers)

# Using the intersection function to find elements that are common in two sets.

first_numbers.intersection(second_numbers)

# Returns the difference between two sets.

print (first - second)

# Finding the difference of two sets using the difference function.

first_numbers.differene(second_numbers)

# Return the values that exist in either set but not both.

print (first ^ second)
{% endhighlight %}

## Dictionaries

Another common data type that Python offers are dictionaries. Dictionaries are powerful in that they can mutable, meaning they can be changed. And similar to lists, dictionaries can be nested or expanded and contracted as need be. However, dictionaries differ from lists in that while lists elements are accessed via index values, dictionary elements are accessed via key-value pairs.

An example use case would be, say you need to categorise a group of cars, and for each car, you need to know the model year, the make and the type, whether it’s an suv or sedan. With dictionaries, you can have a single dictionary where each of the elements that you need to query is a separate key and the values are simply, what you need answered.

In Python, that dictionary would look something like this:

{% highlight python linenos %}
car = {
'Model': 'Model A',
'Type': 'Sedan',
'Year': '2020',
}
{% endhighlight %}

This becomes extremely powerful because it means that we can parse is different sorts of data and categorise things even further, instead of having to create separate lists for each element type.

Another use case here is say, you are working on a translator and you need to convert the months of the year from one language to another. With dictionaries, you can have each of the months represented as separate individual keys and then the value can become whatever language that key needs to translate into.

{% highlight python linenos %}
months = {
'Jan': '一ヶ月',
'Feb': '二ヶ月',
'Mar': '三ヶ月',
'Apr': '四ヶ月',
'May': '五ヶ月',
'Jun': '六ヶ月',
'Jul': '七ヶ月',
'Aug': '八ヶ月',
'Sep': '九ヶ月',
'Oct': '十ヶ月',
'Nov': '十一ヶ月',
'Dec': '十二ヶ月'
}
{% endhighlight %}

Dictionaries in Python are denoted by the {}, with the key-value separated by a :. You can also create dictionaries by using the dict() function. Tuples are a great way of creating dictionaries as the first item inside a tuple becomes the key. And so, you would pass in a list of tuples for however many key-value pairs there are.

{% highlight python linenos %}
month = dict([('Jan','一ヶ月'), ('Feb','二ヶ月')])
{% endhighlight %}
If the key values are just basic, simple strings, those key-value pairs can be specified as keyword arguments. Therefore, another way of writing the dictionary above could be done like so:

{% highlight python linenos %}
months = (
Jan = '一ヶ月',
Feb = '二ヶ月',
Mar = '三ヶ月'
)
{% endhighlight %}
Using our car example, we can access a dictionary value by specifying the key that it corresponds to

{% highlight python linenos %}

> > > car['Type']
> > > 'Sedan'
> > > {% endhighlight %}
> > > If we try to access a key that does not exist within the dictionary, however, Python will raise an exception

{% highlight python linenos %}

> > > car['Make']
> > > Traceback (most recent call last):
> > > File "<stdin>", line 1, in <module>
> > > KeyError: 'Make'
> > > {% endhighlight %}

Python has several functions built-in for manipulating those dictionaries, one of which is to query if a key exists inside of a dict. Using the get() function, we can check to see if a specific key exists, if it doesn’t Python will return a ‘None’ instead of raising an exception.

{% highlight python linenos %}

> > > x = car.get('Make')
> > > print(x)
> > > None
> > > {% endhighlight %}

Dictionaries don’t necessarily have to use just strings for their values, or keys for that matter. You can even pair, integers with strings and have the integers be representative of the keys such as below and even mix different data types.

{% highlight python linenos %}
material_property = {1:112, 2:2.76, 'parameter':'roughness', 'set_state':False}
{% endhighlight %}
Because of this, dictionaries become an extremely useful and powerful tool when working with different sorts of data. As such, there are several built-in functions to help us manage and work with these dictionaries.

{% highlight python linenos %}
material_property = {1:112, 2:2.76, 'parameter':'roughness', 'set_state':False}

# Clears a dictionary

material_property.clear()

# Prints the length of a dictionary

print(len(material_property))

# Returns a value of a specified key

material_property.get('parameter')

# Returns a list of all the keys within a dictionary

material_property.keys()

# Returns a list of all the values within a dictionary, including duplicates.

material_property.values()

# Returns a list of tuples, containing the key-value pairs.

material_property.items()

# Removes a key from a dictionary and returns its value.

material_property.pop(2)

# Removes a random key-value pair arbitrarily and returns it as a tuple.

material_property.popitem()

# Merges one dictionary into another.

add_dict = {1:112, 2:2.76}
material_property.update(add_dict)

# Returns a sorted list of keys in the dictionary. Keys have to be of equal type.

fov = {0: 27, 2: 35, 4: 60, 1: 50, 3: 24}
print(sorted(fov))
{% endhighlight %}

## String formatting

An important concept when working with strings is known as string formatting. String formatting lets you automatically substitute parts of a string for some kind of data that you may want to include. Here’s an example use case.

{% highlight python linenos %}
name = 'Keichi'
age = 27
place = 'Tokyo'
sentence = name + ' is ' + str(age) + ' years old and lives in ' + place + '.'
{% endhighlight %}

A lot is going on with this string. Several concatenations, type conversion, and a lot of spaces in very specific places. This makes things hard to keep track of and difficult to read.

String formatting allows us to simplify a lot of this clutter, making it easier to manage and thus format our strings. There are several methods of formatting strings. Python 2 popularly used the .format() function. The formula goes something like below:

{% highlight python linenos %}
name = 'Keichi'
age = 27
place = 'Tokyo'
print('{0} is {1} year old and lives in {2}.'.format(name, age, place))
{% endhighlight %}

What we’ve done here is replaced where each of the variables would normally be called with {} that act as placeholders and then within the format function parenthesis, we’ve called on each of the different variables in the order as we would want them to be called in the string. name being {0}, age being {1} and place being {2}.

Here we have explicitly replaced each of the different placeholders with each of the variables that we want to replace them with. If we leave the {} in our string empty, then it’s just going to replace each of them, based on the order in which you specify those keywords within the format parenthesis. name in the first, age in the second, and place last.

It is generally however, good practice to not leave the {} blank. This is most useful in situations where you might want to repeat a certain value across multiple places. Such as below:

{% highlight python linenos %}
name = 'Keichi'
age = 27
place = 'Tokyo'
print('{0} is {1} year old. {0} lives in {2}.'.format(name, age, place))
{% endhighlight %}
We can also store our variables within a dictionary and call on each of the dictionary keys within our parenthesis.

{% highlight python linenos %}
person = {'name': 'Keichi', 'age': 27, 'place': 'Tokyo'}
print('{0['name']} is {1['age']} year old and lives in {2['place']}.'.format(person, person, person))
{% endhighlight %}

But notice how we’re repeating our dictionary call in the format function 3 times? Here, we’re essentially calling out dictionary 3 times which we don’t need to, since we already know out dictionary keys

{% highlight python linenos %}
person = {'name': 'Keichi', 'age': 27, 'place': 'Tokyo'}
print('{0['name']} is {0['age']} year old and lives in {0['place']}.'.format(person))
{% endhighlight %}

This is also how you can read in lists or tuples. Replace the values within the square brackets [] with the index number and it’ll return a similar result. This is fine and all however it’s still quite messy. Python 3.6 introduced a new concept known as f-strings. There’s an even older way of dealing with string formatting which I’m not going to go into.

The idea behind f-strings is somewhat similar to using the format function but instead, you attach an f in the front of your string to denote that string is to be formatted. Using the above example without our dictionaries, an f-string would look something like this.

{% highlight python linenos %}e = 'Keichi'
age = 27
place = 'Tokyo'
print(f'{name} is {age} year old and lives in {place}.')
{% endhighlight %}

This is a much simpler and easier way of formatting. It makes reading the code a whole lot easier. What if we want to pass in our dictionary? Yes, we can still do that but there’s one thing we need to change. In our string, where we have specified the keys that we want to access if the keys are strings and we are using single quotes to enclose our entire f-string, then those key-strings need to be in double quotes, otherwise, Python assumes that we are terminating our string and will error out.

{% highlight python linenos %}
person = {'name': 'Keichi', 'age': 27, 'place': 'Tokyo'}
print(f'{person["name"]} is {person["age"]} year old and lives in {person["place"]}.')
{% endhighlight %}

We can also perform calculations within our f-string

{% highlight python linenos %}
print(f'25 multiplied by 2 is equal to {25 \* 2}.')
{% endhighlight %}

We can even use other string functions within f our f-strings

{% highlight python linenos %}
name = 'keichi'
print(f'{name.upper()} is 27 year old.')
{% endhighlight %}

## Escape Sequences

In a previous section, we briefly covered strings and talked about the different quotation marks. There are a few things to note regarding that. If your string is enclosed in single ', then the quotation marks within your string need to use double " and vice versa. Python does permit single quote quotations if the entire strings are already enclosed in single quote. This is due to a concept known as an escape sequence. So strings like below are considered illegal and will throw an error if you try to run it

{% highlight python linenos %}

# This is an illegal string in Python

''This is a string in quotations''

# This is also an illegal string

""This is a string in quotations""

# This is a legal string

"'This is a string in quotations'"

# This is also a legal string

'"This is a string in quotations"'
{% endhighlight %}

What happens if we use the same quotations somewhere else within the string and not just for our string declaration?

{% highlight python linenos %}

# Placing quotations somewhere else within the string

> > > print("This is a "string" in quotations")
> > > File "<stdin>", line 1

    print("This is a "string" in quotations")
                           ^

SyntaxError: invalid syntax
{% endhighlight %}
Here we see the problem. Our entire string is encased with double ". But we’re also attempting to encase a word in the string with another pair of ". Python is unable to reconcile this because it thinks that the second " from the left is the closing tag of the string and thus throws an error. This would be the same if the string were all using single ', regardless. What if we were to switch one of the pairs to use single quotes instead?

{% highlight python linenos %}

# Placing quotations somewhere else within the string

> > > print('This is a "string" in quotations')
> > > This is a "string" in quotations
> > > {% endhighlight %}

Python resolves this. The same would be true if the quotes were reversed. This works but it breaks any established convention you may have and doesn’t solve the problem. Say you had a sentence that is encased in single quotes ' and had words containing '. You’ll likely still run into issues.

Instead, it is better to use escape sequences so that you can maintain consistency. They work like this. Your entire string gets enclosed within quotation marks, whether it’s single 'or double ". If you want to add other quotation marks within your string, you simply need to insert a backslash \, which is the symbol for escaping a sequence, before your quotation marks. This becomes extremely important, especially when dealing with paths. Here are some examples of using escape sequences.

{% highlight python linenos %}

# Using escape sequence to add double quote inside a string

print('This is a \"string" using double quotations')

# Using escape sequence to escape single quote in a string.

print("This is a \'string' using single quotations")

# Using escape sequence to add a single backslash to a string.

print('c:\\some_folder\\some_sub_folder\\file.ext')

# Using \r escape sequence as an alternate means for using single backslashes.

print(r'c:\some_folder\some_sub_folder\file.ext')

# Using escape sequence to add a double backslash to a string.

print('c:\\\\some_folder\\\\some_sub_folder\\\\file.ext')

# Using the \n escape sequence to print onto a new line.

print('This is a string in quotations. \nThis prints a string onto a new line.')

# Using the \t escape sequence to add a tab to a string.

print('\tThis is a string in quotations.')
{% endhighlight %}
