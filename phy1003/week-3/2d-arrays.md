# Creating and manipulating 2D arrays

In Week 1, we looked at how to plot functions that have one variable, e.g. f(x) = sin(x).  To do this, we first created a 1D array of the variable, e.g. `x = np.linspace(0, 1, 11)`.  We then created a new 1D array by defining the function we wished to plot e.g. `y = np.sin(x)`.  As such, when we plotted this function using the code `plt.plot(x,y)`.

Using Python, we can also visualize functions of two variables, e.g. LaTeX: z(x,y) = x<sup>2</sup> + 2y<sup>2</sup>, using e.g. the `plt.contourf(x,y,z)` (filled contour) function, as we will see in the next few pages. For these plots, the data is plotted on top of a 2D grid, i.e. the Cartesian xy-plane.  As such, the parameters `x`, `y`, and `z` used in these functions are 2D arrays.

## Creating 2D Arrays using `np.array()` function

In Python, a 2D array is stored as a 1D array, where each element is itself a 1D array.  One simple way of creating a 2D array is by creating a 'list of lists' then converting to an array using the `np.array()` function as follows:

``` python
In [1]: list_2d = [[1,2,3], [4,5,6], [7,8,9]] # creates list of lists

In [2]: import numpy as np

In [3]: array_2d = np.array(list_2d) # converts 2d list to array

In [4]: array_2d
Out[4]:
array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])
```

## Accessing and modifying 2D arrays

The element in the ith row and jth column can be accessed or modified by using (zero-based) indexing of the form:  `array_2d[i][j]`, or `array_2d[i, j]`. This may be visualized as the below table

 
|           | Col. 0 | Col. 1 | Col. 2 | Col. 3 |
|-----------|--------|--------|--------|--------|
| **Row 0** | [0][0] | [0][1] | [0][2] | [0][3] |
| **Row 1** | [1][0] | [1][1] | [1][2] | [1][3] |
| **Row 2** | [2][0] | [2][1] | [2][2] | [2][3] |
| **Row 3** | [3][0] | [3][1] | [3][2] | [3][3] |


For example:

``` python
In [5]: array_2d[0][0] # accesses element in row index 0, column index 0
Out[5]: 1

In [6]: array_2d[2][1] # accesses element in row index 2, column index 1
Out[6]:8

In [7]: array_2d[2,1] # accesses element in row index 2, column index 1 (alternative notation)
Out[7]: 8

In [8]: array_2d[1,1] = 20 # changes the element in row index 1, column index 1 to 20

In [9]: array_2d
Out[9]:
array([[ 1, 2, 3],
       [ 4, 20, 6],
       [ 7, 8, 9]])
```

## Creating 2D arrays using the np.zeros() function

Another useful way of creating a 2D array is using the `np.zeros()` function that you are already familiar with.  You can do this by passing it a list which contains the number of rows and columns, i.e. `np.zeros([rows,cols])`.  For example:

``` python
In [10]: np.zeros([2,3])
Out[10]:
array([[0., 0., 0.],
       [0., 0., 0.]])

In [11]: np.zeros([5,2])
Out[11]:
array([[0., 0.],
       [0., 0.],
       [0., 0.],
       [0., 0.],
       [0., 0.]])
```
