# Lesson Python and Text Analysis

[Intro to Python](https://www.w3schools.com/python/gloss_python_indentation.asp#:~:text=Indentation%20refers%20to%20the%20spaces,indicate%20a%20block%20of%20code.)

First published in 1991, Python is a versatile programming language that can be used for many different programming projects. It is easy to set up and is written in a relatively straightforward style with immediate feedback on errors. Python is a great choice for beginners and experienced developers alike. Python 3 is the most current version of the language and is considered to be the future of Python.

Python is called a language, but it is more of a translator between you and your computer. It is not smart or stupid, it just really likes rules.

Python reads from the top down and from left to right. That goes for inside of a cell, but also inside of a program or notebook. This order of operations matters! You cannot create a variable after you use it.

Indentation matters! Lines indented below other lines are 'inside' that code, unindented lines are 'outside' that code.

If Python cannot read something it will give you an error. Sometimes these are easy to fix (a missing comma or colon) and sometimes it is more complex.

## Local Python Installation

In order to run Python code, you need a computing environment with an installed version of Python and, usually, installed code 'libraries', which are collections of pre-written code and functions that extend the capabilities of the Python programming language.

In Step One of this lesson, we will install Python on our machines and work through the command line. In Step Two, we will introduce Jupyter Notebooks and work in that environment.

Open a terminal window and type `python`.

If Python is installed locally, you should see a message like this:

```python
Python 3.11.1 (tags/v3.11.1:a7a450f, Dec  6 2022, 19:58:39) [MSC v.1934 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> print("Hello World")
Hello World
>>>
```

NB: '>>>' is the python command prompt. 'Hello World' does not have the prompt because it is not an input; it is an output of the previous `print("Hello World")` command.

If you don't see this, Windows users will likely be sent to the Windows Store where you will be given the option to `get` (download) a version of Python. If so, `get` it!

If you do not get the message, your can [go to the python.org site](python.org) where you can download python. It should take 15 - 30 seconds. Afterwards, in terminal, again type `python` and enter, which should now produce the automatic message shown above.

You could try to `print()` a different message in the terminal:

```python
>>> print("I Love DH")
```

## Python Extension Pack

Now, we will want to install the 'Python Extension Pack' in VSCode extensions, which will add Python language support, Intellicode, Django, Jinga, Python Indent, autoDocstring, and the Python Environment Manager.

You should now see an icon with two coiled snakes which reveals the Python Environment settings. Open it up. It might say that there is 'No Active Environment'. We need to set up an environment to use Python within the text editor. In that case, you can click the '+' sign beside 'Venv' (Virtual Environment).

It will show that the 'pip' package is installed. Pip is the CLI python downloader for libraries. You can use the 'pip' command to install libraries.

## Install and Import a Library (e.g NumPy)

In python terminal, type `pip install numpy`. This will download and install a library called numpy, the documentation for which can be found at numpy.org. If you refresh your python environment, you should now see numpy in the list of packages. Congrats, you have installed your first library, one of the most essential of all libraries.

Use numpy to generate a random integer between 1 and 6. [Read about the 'numpy.random' module](https://numpy.org/doc/stable/reference/random/index.html). The documentation tells us that the basic method is np.random.default_rng(). If you entered that in the terminal, it would print out the generator name. To do more, we need to add a method. The documentation tells us that we can add use 'random()' to generate a random float between 0 and 1:

```python
import numpy as np
np.random.default_rng().random()
```

NB-1: Once in your script, you will need to 'import' any libraries that you use.

- For an overview of [all packages and modules in Python's standard library](https://docs.python.org/3/library/)
- For an overview of [the various built-in functions](https://docs.python.org/3/library/functions.html)

NB-2: default_rng() tells numpy to use the default random number generator.

To generate an integer, we can use the '.integers()' method which has various parameters (low, high, size=, etc.). Let's set the parameters of low = 1, high = 6; and roll two dice (i.e. size=2):

```python
np.random.default_rng().integers(1,6,size=2)
```

This will give you two random integers between 1 and 6 formatted as an array([1,2]).

## Basic Python Syntax

Python is case-sensitive. This means that the keywords, variable names, and function names must be written in the correct case.

Indentation refers to the spaces at the beginning of a code line. Where in other programming languages the indentation in code is for readability only, the indentation in Python is very important. Python uses indentation to indicate a block of code. [An example of indentation](https://www.w3schools.com/python/gloss_python_indentation.asp#:~:text=Indentation%20refers%20to%20the%20spaces,indicate%20a%20block%20of%20code.)

### Variables

Variables are defined using the assignment operator `=`. For example, to define the variable `x` and assign the value `100` to it, we write:

```python
x = 100
```

### Numbers and Strings

Numbers, such as `1`, `5`, and `100` are called integers and are of type `int` in Python. Numbers with a fractional part (e.g., `9.33`) are of the type `float`. The string data type (`str`) is commonly used to represent text. Strings can be expressed in multiple ways: they can be enclosed with single or double quotes. For example:

```python
mystring = "A lesson in basic python for Digital History"
```

### Indexing

Python strings are sequences of characters, where characters are strings of length one. Sequences such as strings can be indexed to retrieve any component character in the string. Like many other programming languages, Python starts counting from zero, which explains why the first character of a string is indexed using the number 0. For example, to retrieve the first character of the string defined above, we write the following:

```python
print(mystring[0])
```

To print a range of indexed values, use the ':':

```python
print(mystring[0:10])
```

### Looping

Looping involves a sequence of Python instructions, which is repeated until a particular condition is met. For example, we might loop (or iterate as it's sometimes called) over the characters in a string and print each character to our screen:

```python
for character in mystring:
    print(character)
```

### Lists

Strings are sequences of characters. Python provides a number of other sequence types, allowing us to store different data types. One of the most commonly used sequence types is the `list`. A list has similar properties as strings, but allows us to store any kind of data type inside:

```python
numbers = [1, 1, 2, 3, 5, 8]
words = ["This", "is", "a", "list", "of", "strings"]
```

We can index and slice lists using the same syntax as with strings:

```python
print(numbers[0])
print(numbers[-1])  # use -1 to retrieve the last item in a sequence
print(words[3:])  # use slice syntax to retrieve a subsequence
```

### Dictionaries and sets

Dictionaries (`dict`) and sets (`set`) are unordered data types in Python. Dictionaries consist of entries, or "keys", that hold a value:

```python
packages = {'matplotlib': 'Matplotlib is a Python 2D plotting library',
            'pandas': 'Pandas is a Python library for data analysis',
            'scikit-learn': 'Scikit-learn helps with Machine Learning in Python'}
```

The keys in a dictionary are unique and unmutable. To look up the value of a given key, we "index" the dictionary using that key, e.g.:

```python
print(packages['pandas'])
```

Sets represent unordered collections of unique, unmutable objects. For example, the following code block defines a set of strings:

```python
packages = {"matplotlib", "pandas", "scikit-learn"}
```

### Conditional expressions

Python provides the statements `if`, `elif`, and `else`, which are used for conditional execution of certain lines of code. For instance, say we want to print all strings in a list that contain the letter *i*. The `if` statement in the following code block executes the print function *on the condition* that the current string in the loop contains the string *i*:

```python
words = ["move", "slowly", "and", "fix", "things"]
for word in words:
    if "i" in word:
        print(word)
```

### Defining functions

In addition to using built-in functions and functions imported from modules, you can define your own functions (or at least recognize function definitions). For example, the following function takes a list of strings as argument and returns the number of strings that end with the substring *ing*:

```python
def count_ing(strings):
    count = 0
    for string in strings:
        if string.endswith("ing"):
            count += 1
    return count

words = [
    "coding", "is", "about", "developing", "logical", "event", "sequences"
]
print(count_ing(words))
```

### Reading and writing files

An example is given below, where we read the file `data/aesop-wolf-dog.txt` and print its contents to our screen:

```python
f = open("data/aesop-wolf-dog.txt")  # open a file
text = f.read()  # read the contents of a file
f.close()  # close the connection to the file
print(text)  # print the contents of the file
```

## Python in Jupyter Notebooks

Jupyter Notebooks (formerly known as IPython Notebook) is a method to combine code (often Python but not exclusively) and markdown text. It uses the `.ipynb` file extension. These files will own with Google Colab Notebook application, JupyterLab, or your favorite editor such as VSCode.

In VSCode, create a file called 'm07-playground.ipynb'.

When this file is open

- 'Select Kernel' (either the global or the .venv that we set up)
- Install support for ipynb (approx. 10 seconds)
- type `print("Hello World") in code cell.
- Run cell -> install ipykernel package (approx. 60 - 90 seconds)

![Basic Jupyter Notebook features](/modules/07-python-text-analysis/data/jupyter01.png)

We can run this cell of code by:

- Running all (top)
- Running just this cell (left)
- Running everything above this cell (first play button to right)
- Running this cell and everything below (second play button to right).

We can add new Markdown or Code cells above or below this one.

We can move this cell up or down.

A Markdown cell will have a slightly different look:

![Markdown cell in Jupyter Notebooks](/modules/07-python-text-analysis/data/jupyter02.png)

A Markdown cell has a raw and unformatted version, which can be toggled by the 'checkmark' or 'pencil' icons to the right.

`ctrl + alt + enter` will run or format the cell.

`alt + enter` will run or format the cell and then add another cell below it.

Anything that has been run above will remain valid below. So when we can then add a 'method' to this variable (such as .capitalize or .split) it will pull in the variable from the preceding code block. For example:

```python
cap_msg = msg.capitalize().split()
print(cap_msg)
```

## Python integration with Postgresql

You might need to install pandas using `pip install pandas`

Import packages:

```python
import pandas
```

You might need to `pip install ipython-sql`

And also `pip install psycopg2`

Now, to load ipython-sql, use the following magic command:

```python
%load_ext sql
```

You might need to  `pip install sqlalchemy` before preceding.

Next, we will only need the create_engine() function from sqlalchemy so let’s import that with the following line:

```python
from sqlalchemy import create_engine
```

### Connecting to a PostgreSQL database

To connect ipython-sql to your database, use the following format:

```python
%sql dialect+driver://username:password@host:port/database
```

For instance:

```python
%sql postgresql://postgres:PASSWORD@localhost/SES
```

- 'dialect+driver' in this case would just be postgresql , but feel free to use a different database software here
- 'username:password' is where you will substitute your username and password.
- 'host' is usually just localhost unless you are connecting to a remote server
- 'port' does not need to be specified unless you are using something other than the default which is '5432'
- 'database' is the name of the database to connect to.

To connect sqlalchemy to the database, the format will largely be the same, but we will create a new object called engine using the create_engine() function, using this format:

`engine = create_engine('dialect+driver://username:password@host:port/database')`

For the most part, you can just copy & paste what you wrote after the %sql magic command when connecting to ipython-sql and encapsulate it in quotes as a parameter in the create_engine() function.

### Writing SQL Commands in Jupyter Notebook

To enable database querying and other commands, call the magic command %%sql and add your SQL code after. The SQL code should be in its own block, separate from Python code (Thanks Daniel Upton for pointing that out!). Here’s sample code that queries the first three rows and all of the columns in the inventory table:

```python
%sql SELECT DISTINCT(firstname),surname FROM events ORDER BY surname, firstname LIMIT 5
```

### Dataframes

If you’d like to store your query in a pandas DataFrame, this is where sqlalchemy comes in. Create a dataframe object using the command

```python
pd.read_sql('[sql statement]',engine)
```

It takes two arguments:

1. Your SQL query encapsulated in quotes.
2. The 'engine' object you created earlier using the create_engine() function.

For example:

```python
df = pandas.read_sql('SELECT firstname,surname,event_source_info FROM eventinfo ORDER BY surname, firstname LIMIT 5',engine)
df
```

## Resources

[Penn Libraries - Python Text Analysis](https://guides.library.upenn.edu/penntdm/python)

[Humanities Data Analysis: Case Studies with Python](https://www.humanitiesdataanalysis.org/index.html)

[YouTube Python Tutorials for Digital Humanities](https://www.youtube.com/c/pythontutorialsfordigitalhumanities)

[Binghamton University Graduate Academic Coding and Statistical Consultants](https://www.binghamton.edu/grad-school/academic-support/graduate-academic-consultants/coding-consult.html#:~:text=We%20can%20help%20with%20learning,project%20and%20skills%20are%20going.)
