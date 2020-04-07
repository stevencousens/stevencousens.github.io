
# Defining and calling basic mathematical functions in Python

You have already encountered and used many functions in Python such as `print()`, `np.sum()` and `plt.plot()`. In this section, we're going to look at how you can define your own functions. This can be very useful for organizing your code when the programs you write become more complex.

## Comparison with the mathematical concept of functions

In mathematics, you can use notation like f(x) = x<sup>2</sup>-2x-3 or g(x,y)=x<sup>2</sup> + 2y<sup>2</sup> to describe functions.  By specifying values of the 'input' variables x and y you can calculate the 'output' values according to the rule defined in the functions, i.e. for x = 1 we have f(1) = (1)<sup>2</sup> - 2(1) - 3 = -4.  Similarly, for x = 3 and y = 2 we have g(3,2) = (3)<sup>2</sup> + 2(2)<sup>2</sup> = 17.

In Python, these functions can be defined as follows. (Try typing these examples into your Spyder console.  You will have to press the enter key twice after you type the second line for each function).
``` python
def f(x):
    return x**2 - 2*x - 3
```
```python
def g(x, y):
    return x**2 + 2*y**2
```
The first example creates a function called `f` which has one input object (or *'parameter'*) which is referenced by the variable `x` inside the function. `x` is then used to perform the specified calculation which is returned as the output of the function. The second example creates a function `g` which instead has two parameters, which are referenced by `x` and `y` inside the function. Similarly, the calculation is then performed using these parameters and the result is returned as the output.

Simply defining a function does not cause it to run. To do that, you need to *'call'* the function. To call the function you type its name, followed by the input values in parentheses. 

``` python
In [3]: f(1) # calls the function f, passing 1 as the input parameter
Out[3]: -4

In [4]: g(3,2) # calls the function g, passing 3 as the first input parameter (called x inside the function) and passing 2 as the second input parameter (called y inside the function)
Out[4]: 17

In [5]: f(3) # calls the function f, passing 3 as the input parameter
Out[5]: 0

In [6]: a = 2

In [7]: f(a) # variables can also be passed to functions
Out[7]: -3

In [8]: b = f(a) # the return value of functions can be assigned to variables
```

Note that unlike C, you do not have to declare the data type of either the input parameters or of the return value. For this function to correctly run however, you need to ensure that the input parameters are of a data type for which the mathematical operations used in the function make sense. The numbers used above are of course fine to use, but if you accidentally input a string instead, e.g. `f("1")`, then you will get an error. 

You can also pass NumPy arrays to functions to calculate many different values of the function at once, because they are acted upon element-wise by typical mathematical operators and NumPy functions.

``` python
In [9]: import numpy as np

In [10]: x = np.linspace(0,1,11) # creates an array of x values

In [11]: f(x) # calculates values of f for all values in array x
Out[11]:
array([-3. , -3.19, -3.36, -3.51, -3.64, -3.75, -3.84, -3.91, -3.96, -3.99, -4.])
```

## Passing parameters by position or by name
 

The parameters can be passed to a function either implicitly by position (in the order given in the function denition) or explicitly by name, for example:

``` python
In [12]: g(2,3) # by default, parameters are passed by position (e.g. here x = 2 and y = 3, because of their order in the function definition)
Out[12]: 22

In [13]: g(y=2, x=3) # parameters can be passed by name instead of position
Out[13]: 17
```

## Exercise 1:

Create a function called `f` that takes four parameters (called `x`, `a`, `b`, `c`) and returns a Gaussian function defined by the following:

![Equation for Gaussian function](images/eqn-gaussian.svg)

Using the parameters `a = 2`, `b = 1` and `c = 4`:
* Calculate the value of `f` at `x = 4` and print your result.
* Create an array `x_array` which contains 1000 equally spaced elements between -15 and 15. Make a plot of `f(x_array)` versus `x_array`.

Note that the x parameter passed to the function can be either an individual value (like 4) or an array (like `x_array`) and the function works either way.  This is one advantage of not having to declare data types in advance in Python!
