# Exercise Solutions

## Exercise 1:

``` python
In [1]: 24 - 173
Out[1]: -149

In [2]: 20 * 5
Out[2]: 100

In [3]: 19 / 4
Out[3]: 4.75

In [4]: 3 ** 4
Out[4]: 81

In [5]: 6 + 20 * 5
Out[5]: 106

In [6]: (6 + 20) * 5
Out[6]: 130
```

## Exercise 2

``` python
In [1]: import numpy as np

In [2]: L = 0.25

In [3]: g = 9.81

In [4]: T = 2 * np.pi * np.sqrt(L/g)

In [5]: T
Out[5]: 1.0030333403553238
```
## Exercise 3:

``` python
In [1]: import numpy as np

In [2]: a = np.array([1.5, 3.0, 2.5, 0.0])

In [3]: b = np.array([5.0, 2.0, 6.5, 0.5])

In [4]: a + b
Out[4]: array([6.5, 5. , 9. , 0.5])

In [5]: a * (2 * b)
Out[5]: array([15. , 12. , 32.5, 0. ])

In [6]: a**2
Out[6]: array([2.25, 9. , 6.25, 0. ])

In [7]: np.sin(a)
Out[7]: array([0.99749499, 0.14112001, 0.59847214, 0. ])

In [8]: np.exp(b)
Out[8]: array([148.4131591 , 7.3890561 , 665.14163304, 1.64872127])

In [9]: np.log(b)
Out[9]: array([ 1.60943791, 0.69314718, 1.87180218, -0.69314718])

In [10]: np.sum(a) / len(a)
Out[10]: 1.75

In [11]: list_a = [1.5, 3.0, 2.5, 0.0]

In [12]: list_b = [5.0, 2.0, 6.5, 0.5]

In [13]: list_a + list_b
Out[13]: [1.5, 3.0, 2.5, 0.0, 5.0, 2.0, 6.5, 0.5]
```

## Exercise 4

``` python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(-10, 10, 1000)

a = 10 #amplitude of Gaussian
b = 0 #position of Gaussian peak
fwhm = 3 # FWHM width of Gaussian
c = fwhm / (2*np.sqrt(2*np.log(2))) # width of Gaussian

y = a*np.exp(-(x - b)**2 / (2*c**2))

plt.plot(x,y)
plt.xlabel("x")
plt.ylabel("y")
```

## Exercise 5

``` python
In [1]: a = 3

In [2]: a == 2
Out[2]: False

In [3]: a != 2
Out[3]: True

In [4]: (a > 2) and (a < 2.5)
Out[4]: False

In [5]: (a > 2) or (a < 2.5)
Out[5]: True

In [6]: not((a > 2) or (a < 2.5))
Out[6]: False
```

## Exercise 6

``` python
n = 1
while_loop_sum = 0

while (n <= 100):
    while_loop_sum += n
    n += 1
print("The sum of first 100 integers (using while loop) is", while_loop_sum)
```
 
``` python
for_loop_sum = 0
for n in range(1, 101):
    for_loop_sum += n
print("The sum of first 100 integers (using for loop) is", for_loop_sum)
```
 
``` python
import numpy as np
nums = np.linspace(1, 100, 100)
array_sum = np.sum(nums)
print("The sum of first 100 integers (using arrays) is", array_sum)
```

## Exercise 7

``` python
number = 493 # chosen starting integer

while(number != 1): # code runs until sequence reaches 1
    if (number % 2) == 0: # checks if number is even
        number = number / 2 # modifies the number variable if even
        print(number)
    else:
        number = 3 * number + 1 # modifies the number variable if odd
        print(number)
```