# Python

### Python is a programming language.

## Python Install

Many PCs and Macs will have python already installed.

To check if you have python installed on a Windows PC, search in the start bar for Python or run the following on the Command Line.

python --version

### Hello World


```python
print("Hello World")
```

    Hello World
    

##### Python is indented language. It means indentation is must i.e matters while you code. As in other language indentation is for readability but in python it is to indicate a block of code.


```python
if 10>2:
    print("here indentation matters")
```

    here indentation matters
    


```python
#This is a comment.
#This will give an error because we skip the indentation
if 10>2:
print("here indentation matters")
```


      File "<ipython-input-4-a0308ada4adf>", line 3
        print("here indentation matters")
            ^
    IndentationError: expected an indented block
    


#### Note

##### Indentation Rules 
    - The number of spaces is up to you as a programmer, but it has to be at least one.
    - You have to use the same number of spaces in the same block of code
##### Variable Rules
    - Variables are created when you assign a value to it.
    - Python has no command for declaring a variable.
##### Multi-Line Comment
    - Comments can be used to explain Python code.
    - To add a multiline comment you could insert a # for each line.
    - """ This is Multiline Comment """  

### Python Variables

Python has no command for declaring a variable.

A variable is created the moment you first assign a value to it.


```python
x = 1
y = "Saurav"
print(x)
print(y)
```

    1
    Saurav
    

Variables do not need to be declared with any particular type, and can even change type after they have been set.


```python
x = 1       # x is of type int
x = "Zoho" # x is now of type str
print(x)
```

    Zoho
    

###### Casting
If you want to specify the data type of a variable, this can be done with casting.


```python
x = str(3)    # x will be '3'
print(type(x))
y = int(3)    # y will be 3
print(type(y))
z = float(3)  # z will be 3.0
print(type(z))
```

    <class 'str'>
    <class 'int'>
    <class 'float'>
    

###### Variable names are case-sensitive.
Rules for Python variables:
    - A variable name must start with a letter or the underscore character.
    - A variable name cannot start with a number.
    - A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ ).
    - Variable names are case-sensitive (age, Age and AGE are three different variables).

##### Many Values to Multiple Variables.

Python allows you to assign values to multiple variables in one line:


```python
x, y, z = "Ram", "Shyam", "Hari"
print(x)
print(y)
print(z)
```

    Ram
    Shyam
    Hari
    

##### One Value to Multiple Variables
And you can assign the same value to multiple variables in one line


```python
x = y = z = "Dragon Fruit"
print(x)
print(y)
print(z)
```

    Dragon Fruit
    Dragon Fruit
    Dragon Fruit
    

##### Unpack a Collection

If you have a collection of values in a list, tuple etc. Python allows you extract the values into variables. This is called unpacking.


```python
group = ["Rajan", "Rohit", "Saurav"]
x, y, z = group
print(x)
print(y)
print(z)
```

    Rajan
    Rohit
    Saurav
    

##### Output Variable


```python
x = "MNNIT is Located "
y = "in Allahabad"
print(x+y)
```

    MNNIT is Located in Allahabad
    

If you try to combine a string and a number, Python will give you an error:


```python
x = 5
y = "John"
print(x + y)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-20-00c66e4310ff> in <module>
          1 x = 5
          2 y = "John"
    ----> 3 print(x + y)
    

    TypeError: unsupported operand type(s) for +: 'int' and 'str'


##### Global Variables

Variables that are created outside of a function (as in all of the examples above) are known as global variables.

Global variables can be used by everyone, both inside of functions and outside.


```python
x = "Allahabad"

def myfunc():
  x = "fantastic"
  print("MNNIT is in " + x)

myfunc()

print("SVBH is in " + x)
```

    MNNIT is in fantastic
    SVBH is in Allahabad
    

##### Global Keyword
Normally, when you create a variable inside a function, that variable is local, and can only be used inside that function.

To create a global variable inside a function, you can use the global keyword.



```python
def myfunc():
 global x 
 x = "fantastic"
 print("MNNIT is in " + x)

myfunc()

print("SVBH is in " + x)
```

    MNNIT is in fantastic
    SVBH is in fantastic
    

### Data Type


```python
#You can get the data type of any object by using the type() function:
x = 5
print(type(x))
```

    <class 'int'>
    

#### Python Numbers
There are three numeric types in Python:
        - int(No range can be extended as much as memory available)
        - float
        - complex


```python
x = 1    # int
y = 2.8  # float
z = 1j   # complex
print(type(x))
print(type(y))
print(type(z))
```

    <class 'int'>
    <class 'float'>
    <class 'complex'>
    

You can convert from one type to another with the int(), float(), and complex() methods:

Note: You cannot convert complex numbers into another number type.


```python
y = 2.8  # float
z = 1j   # complex

#convert from int to float:
a = float(x)

#convert from float to int:
b = int(y)

#convert from int to complex:
c = complex(x)

print(a)
print(b)
print(c)

print(type(a))
print(type(b))
print(type(c))
```

    1.0
    2
    (1+0j)
    <class 'float'>
    <class 'int'>
    <class 'complex'>
    

##### Random Number
Python does not have a random() function to make a random number, but Python has a built-in module called random that can be used to make random numbers:


```python
#display a random number between 1 and 9:
import random

print(random.randrange(1, 10))
```

    5
    

#### String 
Strings in python are surrounded by either single quotation marks, or double quotation marks.

'hello' is the same as "hello".


```python
a ="Rajan"
print(a)
```

    Rajan
    

###### Multi-Line String


```python
a = """
I am an student of
Mnnit Allahabad. I 
study computer science
engineering."""
print(a)
```

    
    I am an student of
    Mnnit Allahabad. I 
    study computer science
    engineering.
    


```python
a = '''I am an student of
Mnnit Allahabad. I 
study computer science
engineering.'''
print(a)
```

    I am an student of
    Mnnit Allahabad. I 
    study computer science
    engineering.
    


```python
a = "Hello, World!"
print(a[1])
```

    e
    


```python
for x in "banana":
  print(x)
```

    b
    a
    n
    a
    n
    a
    

###### Length of String


```python
a = "Hello, World!"
print(len(a))
```

    13
    

##### To Check in String


```python
txt = "I study in MNNIT!"
print("MNNIT" in txt)
```

    True
    


```python
txt = "I study in MNNIT!"
if "MNNIT" in txt:
    print("Yes, you can enter")
```

    Yes, you can enter
    


```python
txt = "I study in DTU!"
if "MNNIT" not in txt:
    print("Yes, you can't enter")
```

    Yes, you can't enter
    

##### Slicing


```python
txt = "Trimme"
print(txt[2:5])
```

    imm
    


```python
txt = "Trimme"
print(txt[:5])
```

    Trimm
    


```python
txt = "Trimme"
print(txt[2:])
```

    imme
    

##### Modify Strings


```python
a ="hello"
print(a.upper())
print(a)
```

    HELLO
    hello
    


```python
a="HELLO"
print(a.lower())
print(a)
```

    hello
    HELLO
    


```python
a = " Hello, World! "
print(a.strip()) #Removes any whitespace from begining or end
```

    Hello, World!
    


```python
a = "Hello, World!"
print(a.replace("H", "J"))
```

    Jello, World!
    


```python
"""Split String
The split() method returns a list where the 
text between the specified separator becomes the list items.
""" 
a = "Hello, World!"
print(a.split(","))
```

    ['Hello', ' World!']
    

##### Escape Character


```python
txt = "To insert double quote we need to do this \"\""
print(txt)
```

    To insert double quote we need to do this ""
    

##### Python Booleans


```python
a = 100
b = 33

if b > a:
  print("b is greater than a")
else:
  print("b is not greater than a")
```

    b is not greater than a
    


```python
x = 200
print(isinstance(x, int))
```

    True
    


```python

```
