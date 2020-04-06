# Boolean arrays and masking

Last week, we looked at using the conditional operators (`==`, `!=`, `>`, `<`, `>=` and `<=`) which return the Boolean values `True` or `False` for a given condition. If you use these operators on an array, the condition is tested element-wise and a 'Boolean array' is returned, as illustrated in the code below.

``` python
In [1]: import numpy as np

In [2]: my_array = np.array([1, 3, 9, 2, 3, 5, 6])

In [3]: my_array > 3
Out[3]: array([False, False, True, False, False, True, True])
```

This leads to a very useful feature of NumPy arrays known as *'Boolean masking'* which is a way of manipulating  elements of an array based on a particular condition.

For example, if you place the condition (i.e. the *'mask'*) as the index to `my_array`, you will extract those values that returned True as shown below.

``` python
In [4]: my_mask = my_array > 3 # stores the Boolean array

In [5]: my_array[my_mask] # outputs only values of my_array that are greater than 3
Out[5]: array([9, 5, 6])
```

For Monte Carlo simulations, it is really useful to be able to output how many `True` values there are in the Boolean array.  There are at least two easy ways of doing this.  First you can extract the elements as illustrated `In [5]:` above, then count how many elements are in the new array using the `len()` function.  The second approach, which saves creating a new array is to use the `np.sum()` function on the mask itself.  This exploits the fact that for arithmetic operations in Python, `True` is treated as `1` and `False` is treated as `0`.  Both these methods are illustrated in the code below:

``` python
In [6]: len(my_array[my_mask]) # creates a masked array then calculates its length
Out[6]: 3

In [7]: np.sum(my_mask) # adds up all the True values in the Boolean array
Out[7]: 3
```

## Element-wise operations & and | on arrays

An important point is that the logical operators `and` and `or` do **not** act element-wise on arrays. Instead, we use `&` for element-wise and, and `|` for element-wise or as shown in the below example. Note that using `and` or `or` here will return an error.

``` python
In [8]: (my_array > 1) & (my_array < 6)
Out[8]: array([False, True, False, True, True, True, False])

In [9]: (my_array < 1) | (my_array > 5)
Out[9]: array([False, False, True, False, False, False, True])
```
