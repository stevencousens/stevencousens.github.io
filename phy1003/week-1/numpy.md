# The NumPy module

## Basic mathematical functions and constants

Most mathematical functions, even relatively simple trigonometic functions are not defined in basic Python.  For example, if you input `sin(0.5)`, the console returns a `NameError`,

``` python
In [1]: sin(0.5)

Traceback (most recent call last):
File "<ipython-input-1-242eb9389477>", line 1, in <module>

sin(0.5)

NameError: name 'sin' is not defined
```
The *'NumPy'* module greatly extends the capabilities of the Python language by defining many different functions, constants and data structures that are particularly useful for scientific programming. We can import the *'NumPy'* module by typing the following line into the console.

```python
In [2]: import numpy as np
```

This line of code imports the NumPy module and gives it the *'alias'* `np`. To access the functions defined by NumPy, simply type `np.` followed by the name of the function. For example,

```python
In [3]: np.sin(0.5)
Out[3]: 0.479425538604203

In [4]: np.sqrt(2)
Out[4]: 1.4142135623730951
```

Adding the `as np` to the import line to get an alias is optional, but if you exclude it you must type the full module name each time you wish to access its functions, for example `numpy.sqrt(2)`.  A list of the mathematical functions included in NumPy is given in the [official documentation](https://docs.scipy.org/doc/numpy-1.13.0/reference/routines.math.html).

The NumPy module also includes a number of mathematical constants, such as π (accessed by writing `np.pi`) and Euler's constant, (accessed by writing `np.e`). Try calling these constants in the console and see if they output what you expect.
 
## Exercise 2:

For small oscillation amplitudes, the period *T* of a simple pendulum can be approximated using the equation *T = 2πL/g*, where *L* is the length of the pendulum and *g* is the acceleration due to gravity.  Use this equation to calculate the period of a pendulum *25 cm* in length, with *g = 9.81* m/s<sup>2</sup>. Set and use variables for ** *L* and *g* and use the NumPy constant `np.pi` and the `np.sqrt()` function to make the calculation.

## NumPy arrays

The most important feature of the NumPy module is its array data type. An array is an ordered sequence of Python objects where each element is of the same data type, e.g. integers, floats or other arrays. In this course, we are going to be using arrays extensively to store and manipulate data. 

### Creating 1D arrays using the np.array() function

One way of creating an array is by using the `np.array()` function, which takes a `list` of objects as its argument. A Python `list` is a sequence of objects, (which can be numbers, strings, or any other data type) surrounded by square brackets.  For example, to create an integer array which holds the numbers [1, 2, 4, 9] we can use the following code:

``` python
In [5]: my_integer_array = np.array([1, 2, 4, 9])

In [6]: my_integer_array
Out[6]: array([1, 2, 4, 9])
```

### Accessing and modifying array elements

Individual elements from the array can be accessed and modified by using its index which is an integer. Python (like C) uses a zero-based indexing system, such that the first item in an array is referenced by the index `0`, the second by the index `1` and so on. Elements from the array can be accessed using square brackets as follows,

``` python
In [7]: my_integer_array[0]
Out[7]: 1

In [8]: my_integer_array[1]
Out[8]: 2

In [9]: my_integer_array[2]
Out[9]: 4

In [10]: my_integer_array[3]
Out[10]: 9
```

Note that if you try to access an element of the array that doesn't exist, you get an error:

``` python
In [11]: my_integer_array[4]

Traceback (most recent call last):

File "<ipython-input-11-101f99d32534>", line 1, in <module>

my_integer_array[4]

IndexError: index 4 is out of bounds for axis 0 with size 4
```

You can also change the values in the array simply by reassigning them:

``` python

In [12]: my_integer_array[2] = 12 

In [13]: my_integer_array
Out[13]: array([ 1, 2, 12, 9])
```
It's an important point that all elements of the array **must** be of the same data type, which is decided when the array is created. Since we created this array exclusively from integers, we cannot later add a float to it. If we try to change an element from `my_integer_array` to a float, the fractional part will be removed and the number will automatically be converted to an integer.

``` python
In [14]: my_integer_array[2] = 5.6

In [15]: my_integer_array
Out[15]: array([1, 2, 5, 9])
```

Therefore if you want the possibility of adding floats to the array, you must add at least one number with a decimal point to the list when the array is created.

``` python
In [16]: my_float_array = np.array([1.0, 2.0, 4.0, 9.0])

In [17]: my_float_array
Out[17]: array([1., 2., 4., 9.])

In [18]: my_float_array[2] = 5.6

In [19]: my_float_array
Out[19]: array([1. , 2. , 5.6, 9. ])
```

### Slicing arrays

In the same way that you can access and modify individual elements from an array using square bracket notation, you can select sub-arrays using 'slicing'. For an array called `my_array`, the simplest way to do this is to input `my_array[start: end]`, where `start` and `end` are integers. This returns an array which contains the elements of `my_array`, which have an index between `start` and `end - 1`.  For example:

``` python
In [20]: my_array = np.array([1, 9, 7, 3, 3, 10, 2])

In [21]: sub_array = my_array[2:6]

In [22]: sub_array
Out[22]: array([ 7, 3, 3, 10])
```

## Element-wise operations and functions on arrays

A really useful feature of NumPy arrays is that the arithmetic operations (i.e. `+` , `-` , `*` , `/` and `**`) act 'element-wise'.  For example, if you have an array `a`, you can add `1` to each element simply by entering `a+1`, or square each element using `a**2`. Similarly, you can add the corresponding elements of two arrays, `a` and `b`, simply by typing `a + b`. NumPy functions, such as `np.sin()`, `np.cos()`, `np.log()`, `np.exp()`, `np.sqrt()` etc. can also be used element-wise on arrays.

There are a few other very useful functions which we will use for arrays in this course.

* The `len()` function returns the number of elements in the array.
* The `np.sum()` function returns the result of adding all the elements of the array together.
* The `np.abs()` returns an array whose elements are the absolute values of those in the target array.

## Exercise 3
* Create two arrays called `a` and `b` from the lists `[1.5, 3.0, 2.5, 0.0]` and `[5.0, 2.0, 6.5, 0.5]`.
* Perform the following operations in the console and verify that they output what you expect
    * a + b
    * a × (2 × b)
    * a<sup>2</sup>
    * sin(a)
    * exp(b)
    * log(b)

* Calculate the mean (average) of all the elements of the array `a`.
* Create two lists, `list_a = [1.5, 3.0, 2.5, 0.0]` and `list_b = [5.0, 2.0, 6.5, 0.5]`. Verify that the operation `list_a + list_b` does **not** output produce an element-wise sum.  This is one reason why we will be using arrays and not lists to manipulate our data

## Creating 1D arrays using `np.linspace()`, `np.zeros()` and `np.ones()`

A very useful way of creating arrays is using the `np.linspace()` function, which ususally takes three arguments, e.g. `np.linspace(start, stop, num)`, generating an array of `num` equally spaced floating point numbers, between `start` and `stop`, inclusive.  For example, to create an array of `11` equally spaced numbers between `0` and `1`, i.e. `0`, `0.1`, `0.2`,... you could enter the following code.

``` python
In [20]: x = np.linspace(0, 1, 11)

In [21]: x
Out[21]: array([0. , 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1. ])
```

Arrays of zeros and ones can be generated using the `np.zeros()` and `np.ones()` functions, which take the number of elements as its argument.

``` python
In [22]: x = np.zeros(5)

In [23]: x
Out[23]: array([0., 0., 0., 0., 0.])

In [24]: x = np.ones(3)

In [25]: x
Out[25]: array([1., 1., 1.])
```
