# Useful functions and methods for Monte Carlo simulations

We are going to use a few more useful functions and methods in particular types of Monte Carlo simulations.

## Shuffling the elements of a list or array

The `np.random.shuffle()` function modifies a list or array by shuffling its elements:

``` python
In [1]: import numpy as np

In [2]: fruit = ['apple', 'pear', 'orange', 'plum', 'lime', 'strawberry']

In [3]: np.random.shuffle(fruit) # shuffles the elements of fruit

In [4]: fruit
Out[4]: ['plum', 'orange', 'pear', 'strawberry', 'apple', 'lime']
```

## The `pop()` list method

In Python, you also have *'methods'* which are similar to functions, but are associated with a particular object.  We're going to use a couple of list methods.  The first is the `pop(index)` method which removes the item at a given index from a list and outputs the item.  Note that methods have a different syntax to regular functions.

``` python
In [5]: fruit.pop(2) # removes and outputs the element in fruit[2]
Out[5]: 'pear'

In [6]: fruit
Out[6]: ['plum', 'orange', 'strawberry', 'apple', 'lime']
```

## The `remove()` list method

The `remove(x)` method removes the first value of the list whose value is `x`.  If there is no `x` this will return an error.  For example.

``` python
In [7]: fruit.remove('apple') # removes the first 'apple' from the list of fruit

In [8]: fruit
Out[8]: ['plum', 'orange', 'strawberry', 'lime']
```