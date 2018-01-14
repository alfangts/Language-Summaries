# Python 3
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
        >>>print('Alice has {} apples and {} oranges'.format(apples,oranges)
        Alice has 10 apples and 5 oranges
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
The text bounded by `"""` is known as the docstring. It is used to explain what the function does and how to use it.

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

## Assertions
