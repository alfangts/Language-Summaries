# Python 3
This document follows the content flow of the Sololearn Python 3 module, summarised into a single document.

## Basics
1. Arithmetic Operations
    * `+,-,*,/` work as usual in all  programming languages
        - `*` and `/` convert int to float
    * Floor division and modulo given by ` // ` and ` % `
    * In-place operators such as `+=` and `-=` can be used
        ```python
        >>>x = 3
        >>>x += 1
        >>>print(x)
        4
        ```
    * Order of operations follows mathematics; Parenthesis first then multiply/divide
     and finally addition/subtraction
    
2. Strings
    * Strings can be manipulated in the following way: 
        ```python
        >>>print('str'*3)
        strstrstr
        >>>print('method'+' X')
        method X
        ```
        Note: it only works with multiplication and addition
    * String formatting with `.format()`
        ```python
        >>>apples = 10
        >>>oranges = 5
        >>>print('Alice has {} apples and {} oranges'.format(apples,oranges))
        Alice has 10 apples and 5 oranges
        ```
        Can also name arguments:
        ```python
        >>>print('Bob has {x} melons and {y} bananas'.format(x=2,y=10))
        Bob has 2 melons and 10 bananas
        ```
    * Strings can also be indexed
        ```python
        >>>'python'[3]
        h
        ```
3. Boolean
    * Boolean values in Python given by `True` and `False` (Case sensitive)
    * Comparison operators
        ```
        Equality: ==
        Not Equals: !=
        Greater than or equals to: >=
        Less than or equals to: <=
        
        Example:
        >>>x = 1
        >>>1 == x
        True
        ```
    
4. Control Structures
    * `if, else, elif, while` blocks require `:`, statements need to be indented by 4 
    spaces (applies to nested control structures as well)
        ```python
        if expression:
           statement
        ```
    * Boolean operators `not, and, or` (in order of precedence) can be used to make more complicated conditions
        ```python
        if requirement1 and requirement2:
          statement
        ```
    * `break` ends a while loop prematurely, and `continue` skips the current iteration
    
    * `any` and `all` take a list as an argument and return `True` if conditions are met, very useful for control statements
    ```python
    >>>nums = [6,10,21,44,50]
    >>> if all([i > 5 for i in nums]):
    >>>    statement
 
    >>> if any([i%2 == 0 for i in nums]):
    >>>    statement
    ```
    * `enumerate` function can be used to iterate through all the values in a list
    ```python
    >>>for v in enumerate(nums)
    >>>    print(v)
    ```
## Objects
Note: Python indexing begins with 0
####Lists
1) List Basics
    * Initialise lists using square brackets and commas to separate items
        ```python
        >>>foo = ['Hello','World','!']
        >>>print(foo[0])
        Hello
        ```    
        Can utilise type-conversion with `list(obj)` constructor
    * Lists can contain items of different types, including other lists
        ```python
        bar = ['List', 3, [0,1,2], 4.57]
        ```
    * Replacing items in a list
        ```python
        >>>bar = ['0','@','2','D']
        >>>bar[1] = bar[3]
        >>>print(bar)
        ['0','D','2','D']
        ```
    * Checking if item is in a list
        ```python
        >>>foo = ['spam','eggs']
        >>>print('spam' in foo)
        True
        ```
        Likewise, can use `not` operator similarly
        ```python
        >>>print('bacon' not in foo)
        True
        >>>print(not 'bacon' in foo)
        True
        ```
2) List Functions and Methods
    * `len(list)` function returns the number of items in a list
    * `max(list)` function returns list item with max value
    * `min(list)` function returns list item with min value
    * `list.append(obj)` method adds an item to the end of a list 
    * `list.insert(index,obj)` method inserts an item in the given index
    * `list.index(obj)` method finds the first occurence of an item in a list and returns it.
        If item is not in list, returns `ValueError`
        ```python
        >>>[1,2,3].index(5)
        ValueError: 5 is not in list
        ```
    * `list.count(obj)` method returns count of object occurrence in list
    * `list.remove(obj)` method removes first occurrence of an object in list
    * `list.pop(index)` method removes object in index and returns object
    * `list.reverse()` method reverses order of objects in list
    
    For more functions and methods, check Python 3 Documentation.

3) List slicing
    * Can create new list from existing one using list slicing
    ```python
    >>>numbers = [1,3,5,2,6,7,2,3]
    >>>mylist = numbers[0:3]
    >>>print(mylist)
    [1,3,5]
    ```
    
    * `list[start:stop:step]` takes every index with `step` from `start`, ending at `stop - 1` or earlier.
    
4) List Comprehensions
    * Quick way to create lists with elements that obey a simple rule
    ```python
    >>>newList = [i*3 for i in range(5)]
    >>>print(newList)
    [0,3,6,9,12]
    ```
    Can also use conditions
    ```python
    >>>newList = [i for i in range(15) if i%3==0]
    [0,3,6,9,12]
    ```
    
#### Dictionaries
1) Dictionary basics
    * Dictionaries contain values mapped to keys, indexed similarly to lists
    ```python
    >>>myDict = {'Dave':12, 'Sally':29}
    >>>print(myDict['Dave'])
    12
    ```
    Indexing a key that is not in a dictionary returns `KeyError`
    * Assign new keys to a dictionary using `myDict[key]=value`
    * Dictionaries keys must be immutable objects
    * Like lists, can check if key exists in dictionary using `in` and `not in`
    
2) Dictionary methods
    * `mydict.get(key,object)` returns corresponding value if `key` in `mydict`, else returns object (`None` by default)
    
    For more functions and methods, check Python 3 Documentation
    
#### Tuples
1) Tuples basics
    * Tuples are immutable lists and cannot be assigned new values once initialised
    ```python
    myTuple = ('spam','eggs','bacon')
    myTuple[1] = 'cheese'
    >>> TypeError: 'tuple' object does not support item assignment
    ```
    
    
#### Range
1) `range(start,stop,step)` creates a range object(not a a list) with `start` as the first element,
    with `step` in between elements and (`stop`-1) as the upper limit.
    
    Note: a range object does not actually contain the sequential elements, merely the information required to form them
    
## Creating Functions
Define functions using the `def` command:
```python
def myfunc(arg1,arg2):
    """ (float, float) -> float
    description
    
    example entry
    >>>example result
    """
    return arg1+arg2
```
If `return` is not used to explicitly return an object, function returns `None`, which is the lack of a value, by default.
The text bounded by `"""` is known as the docstring. It is used to explain what the function does and how to use it.

### Lambda Functions
Lambda functions are anonymous functions. Anonymous functions not stored in seperate program file, and can only execute 
1 statement. Define lamda functions using parentheses and `lambda:`
```python
>>>Add = (lambda x,y: x+y) 
>>>Add(3,4)
7
>>> print((lambda x: x**x)(2))
4
```

## Modules
Import modules using the `import` command at the beginning of the code
```python
>>>import random as rand
>>>print(rand.randint(1,6))
3
```

Can also import specific functions using `from`
```python
>>>from math import sqrt,pi
>>>sqrt(pi**2)
3.141592653589793
```

## Exception Handling
Exceptions occur when something goes wrong, either due to incorrect code or input.
Can use `try/except` to handle exceptions
```python
try:
    num1 = 7
    num2 = 0
    print(num1/num2)
except ZeroDivisionError
    print('Error: Division by zero not allowed') 
except (ValueError,TypeError):
    print('Error: Invalid input')
finally:
    print('This will always print, even if an uncaught error occurs')
```
Refer to Standard Library for types of errors, or module documentation for module-specific ones.
Try not to use a general `except` statement, it does not give useful information for debugging.

Also, `finally` can be used to ensure a block of code runs no matter what error occurs.

Errors can be raised using the `raise` function
```python
>>>print('1')
>>>raise ValueError('Invalid value!')
>>>print('2')
1
ValueError: Invalid value!
```

Can also use `raise` to re-raise any errors that occur.
```python
>>>try:
>>>    7/0
>>>except:
>>>    print('Error')
>>>    raise
Error
ZeroDivisionError: division by zero
```

## File Handling
#### Opening and Closing
For straightforward text files, use `open` function to create a file object containing data required
```python
myfile = open('file.txt','rb')
filetext = myfile.read(bytes)
print(filetext)
finally:
    myfile.close()
```
The second argument is a modifier to the function specifying what mode the file is opened in:
* `r` is read mode
* `w` is write mode
* `a` is append mode
* `b` is binary mode

Can also use `with open('file.txt','rb') as myfile:`, file will automatically close at end of `with` block.
Note: `myfile` is only accessible within `with` block using this method

#### File methods
- `.read(bytes)` method reads the file object to a specified number of bytes. (0 == entire file)
- `.readlines()` method returns a list of strings with each element being a line in the text file
- `.write(string)` method writes a string to the text file, and returns the number of bytes if successful
    ```python
    >>>msgbytes = file.write('Hello World!)
    >>>print(msgbytes)
    12
    ```
- `.close()` method closes the file object to free up memory.

## Functional Programming 
### Map
`map` takes input of a function and an iterable object, and applies the function to every element before returning 
the a map object. Basically, an iterable mapping. Use conversions to transform the map object.
```python
>>>map((lambda x: x+2),[0,1,2,3])
<map object at 0x05E1B170>
>>>tuple(map((lambda x: x+2),[0,1,2,3]))
(2,3,4,5)
```

### Filter
`filter` takes input of a predicate(function that returns boolean) and an iterable, and removes elements that do not satisfy
the predicate.
```python
>>>filter((lambda x: x>3),[0,3,4,5])
<filter object at 0x05E1B170>
>>>list(filter((lambda x: x>3),[0,3,4,5]))
[4,5]
``` 

### Yield
`yield` can be used in named functions for "lazy"(on demand) generation of several values without stopping the function and destroying the function's 
local variables. The generated values can be used as iterables, and has no limit since no memory is used to store 
them. Generated values can be type-converted as well. 
```python
def downskiptwo():
    i = 10
    while i > 0:
        yield i
        i -= 2

>>>print(list(downskiptwo()))
[10, 8, 6, 4, 2]
```

### Decorators
To decorate a function is to alter an already defined function(that you do not wish to modify), through the definition
 of a seperate function.
```python
>>>def decorate(func):
>>>    def wrap():
>>>        print('~~~~~~')
>>>        func()
>>>        print('~~~~~~')
>>>    return wrap
>>>
>>>def foo():
>>>    print('I like eggs')
>>>
>>>fancy = decorate(foo)
>>>fancy()
~~~~~~
I like eggs
~~~~~
```
Notice that `foo` instead of `foo()` is passed into `decorate`. This changes the argument, and `wrap()` will call `foo` 
instead of `func`.<br><br>
Can also use `@` to decorate:
```python
>>>def decorate(func):
>>>    def wrap():
>>>        print('~~~~~~')
>>>        func()
>>>        print('~~~~~~')
>>>    return wrap
>>>
>>>@decorate
>>>def foo():
>>>    print('I like eggs')
>>>
>>>foo()
~~~~~~
I like eggs
~~~~~
```
