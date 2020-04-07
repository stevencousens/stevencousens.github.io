
# Defining more complex functions

Functions can be a lot more complex than the simple mathematical type we have defined so far. In the general case, the syntax for defining a function is as follows:

``` python
def <function_name>(<parameters>):
    """ docstring """
    <body>
    return <return_value>
```
* The permissible function names, i.e. `<function_name>` follow the same rules as for variables, i.e. they can contain letters, digits and underscores, but they must begin with a letter or underscore and it can't be one of the Python keywords.
* The optional `""" docstring """` is included just below the `def` statement and is enclosed in three double quotation marks.  This typically provides a description of the function and its input parameters.
* The `<body>` of the function can consist of multiple lines. The level of indentation marks out the block of code which belongs to the function definition, similar to e.g. if statements and for loops.
* The `return` keyword specifies what value the function evaluates to after it has been called.  This is also an optional statement.

 
## Example:

A simple example of a function definition that adds input numbers together and returns the sum is given below:

``` python
def add_nums(num_1, num_2):
    """ returns the sum of two numbers num_1 and num_2 """
    total = num_1 + num_2
    return total
```
Once defined, this function can be called, e.g.

``` python
In [2]: add_nums(2,3)
Out[2]: 5
``` 

The docstring for the function can be printed by typing `help()`, with the function name inside the parentheses. This can be useful if you want more information on how to use a function. Try doing this for some of the Python functions you already know.

``` python
In [3]: help(add_nums)

Help on function add_nums in module __main__:

add_nums(num_1, num_2)

returns the sum of two numbers num_1 and num_2
```

## Multiple return values

Technically speaking, functions in Python can only return one value.  However, this value can be a compound data type (such as an array or list) so can in practice return multiple values.  This can be achieved for example by separating the return values by a comma, as in the below function definition:

``` python
def add_and_multiply_nums(num_1, num_2):
    """ returns both the sum and product of two numbers num_1 and num_2 """
    total = num_1 + num_2
    product = num_1 * num_2
    return total, product
```

When this function is called, it returns a *'tuple'*, which is a sequence of objects surrounded by parentheses. We aren't going to be using tuples very much in this course, except in the context of returning multiple values from functions.

``` python
In [5]: add_and_multiply_nums(4, 9)
Out[5]: (13, 36)
```

A simple way of *'unpacking'* a tuple is by simply using the following syntax:

``` python
In [6]: added_value, multiplied_value = add_and_multiply_nums(4, 9)

In [7]: added_value
Out[7]: 13

In [8]: multiplied_value
Out[8]: 36
```

## Exercise 2:

The two solutions to the quadratic equation of the form: ax<sup>2</sup>+bx+c = 0, where a, b, c are constants (a is non-zero), are given by the quadratic formula:

![Quadratic equation solutions](images/eqn-quadratic.svg)

* Define a function called `quadratic_roots()` that takes three parameters (`a`, `b`, `c`) and returns the two solutions, `x1` and `x2`.
* Call your function and print to the console the two solutions the quadratic equation x<sup>2</sup>+2x-3 = 0

