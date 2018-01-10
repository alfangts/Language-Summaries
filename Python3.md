# Python 3
## Basics
1. Arithmetic Operations
    * `+,-,*,/` work as usual in all  programming languages
        - `*` and `/` convert int to float
    * Floor division and modulo given by ` // ` and ` % `
    * In-place operators such as `+=` and `-=` can be used
        ```python
        x = 3
        x += 1
        print(x)
        >>> 4
        ```
    
2. Strings
    * Strings can be manipulated in the following way: 
        ```python
        print('str'*3)
        >>>strstrstr
        print('str'+' X')
        >>>str X
        ```
        Note: it only works with multiplication and addition
    * String formatting with `.format()`
        ```python
        apples = 10
        oranges = 5
        print('Alice has {} apples and {} oranges'.format(apples,oranges)
        >>>Alice has 10 apples and 5 oranges
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
        x = 1
        1 == x
        >>>True
        ```
    
4. Control Structures
    * `if, else, elif, while` blocks require `:`, statements need to be indented by 4 
    spaces (applies to nested control structures as well)
        ```python
        if expression:
           statement
        ```
    * Boolean operators `and, or, not` can be used to make more complicated conditions
        ```python
        if requirement1 and requirement2:
          statement
        ```
    * Order of operations follows mathematics; Parenthesis first then multiply/divide
     and finally addition/subtraction
     

