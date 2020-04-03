# Writing more complex programs using control flow

The Python programs we have encountered so far have all systematically executed from the top of the file downwards. Flow control is a way of getting blocks of code to repeat, or to be executed only if certain conditions are met.

## Comparison and logical operators and the Boolean data type


Python has six common comparison operators and three logical operators which are used to compare two values, and determine whether the statement is `True` or `False`. `True` and `False` are called *'Boolean'* data types.

The comparison operators `==` and `!=` test whether the two values are equal or not equal, respectively. For example, the statement `a == b` checks if `a` is equal to `b` and returns `True` if they are and `False` if they aren't. A common mistake to watch out for here is mixing up the `=` operator (used for variable assignment) and the `==` operator (used for testing equality). The other four comparison operators; `>` (greater than), `<` (less than), `>=` (greater than or equal to) and `<=` (less than or equal to) act as expected.

The logical operator `and` is used to test whether two conditions are **both** `True`, and the operator or is used to test whether **either** (or both) of the conditions are `True`. The final logical operator, `not` is used to invert the Boolean value, so `True` becomes `False` and vice versa.

## Exercise 5:

Create a variable `a = 3` in the console

Think about whether Python will return `True` or `False` to the following statements.  Then type these into the Python console and check your answer.

* `a == 2`
* `a != 2`
* `(a > 2) and (a < 2.5)`
* `(a > 2) or (a < 2.5)`
* `not((a > 2) or (a < 2.5))`

# Conditional programming using `if`, `elif` and `else` statements

An `if` statement in Python allows us to give the instruction (when written in plain English) "If this condition is true, then execute this block of code". A template for an `if` statement is as follows:

``` python
if <condition>:
    <block 1>
<block 2>
```
Here, `<block 1>` is a collection of statements that all have the same *'indentation'* (typically four spaces from the left). If the `<condition>` returns `True`, then `< block 1>` will be executed, followed by `<block 2>` and the rest of the program. If the `<condition>` returns `False`, then `<block 1>` will not be executed, but `<block 2>` will still be executed along with the rest of the program. Note that the colon after the condition and the indentation is essential. Returning to having no indentation marks the end of the `if` statement.

For example, try running the following code from the editor and see what happens when you change the value of `x` from `2` to `1`. If you are copy and pasting this code to the editor, be careful to ensure that the indentation is correct before running the program.

```python
x = 2
if x == 1:
    print ("This line only executes if x == 1")
print ("This line of code always executes ")
```
`if` statements can also be chained together using the `elif` (else-if) and `else` statements, for example:

``` python
if <condition 1>:
    <block 1>
elif <condition 2>:
    <block 2>
else:
    <block 3>
<block 4>
```

With this structure, the following outcomes are possible:

* If `<condition 1>` is `True`, then `<block 1>` and `< block 4>` will be executed.
* If `<condition 1>` is `False` and `<condition 2>` is `True`, then `<block 2>` and `<block 4>` will be executed.
* If `<condition 1>` and `<condition 2>` are both `False`, then `<block 3>` and `<block 4>` will be executed.

`if`, `elif`, and `else` statements can also be nested inside another, taking care to indent another four spaces.  For example try running the following code and changing the `num` variable through the different possibilities:

```python
num = -5 #try changing this value
if(num >= 0):
    if num == 0:
        print("num is zero")
    else:
        print("num is positive")
else:
    print("num is negative")
```

## Loops in Python

## `while` loops

A `while` loop is used to repeatedly execute a block of code as long as a given condition is `True`. A template for a `while` loop is as follows:

``` python
while <condition>:
    <block 1>
<block 2>
```

Here, the `<condition>` is tested and if it returns True then `<block 1>` will execute. The testing of the `<condition>` and execution of `<block 1>` will repeat until the `<condition>` becomes `False`, after which `<block 2>` is executed along with the rest of the program.

As a simple example, by running the following code, you get the output below.

``` python
num = 1
while (num < 10):
    print ('This loop has run ', num , 'time(s).')
    num = num + 1 # increase num by 1. Eventually , we will get num >= 10 and the condition becomes False
print ('The loop has now ended.')
```
```python
This loop has run 1 time(s).
This loop has run 2 time(s).
This loop has run 3 time(s).
This loop has run 4 time(s).
This loop has run 5 time(s).
This loop has run 6 time(s).
This loop has run 7 time(s).
This loop has run 8 time(s).
This loop has run 9 time(s).
The loop has now ended.
```

### Accidentally started an infinite loop?

If you've accidentally started an infinite loop and the condition is `True` forever (for example by not including the `num = num + 1` line in the above example) you can stop the program by pressing Ctrl+C on your keyboard.

## `for` loops

`for` loops are typically used when you want the program to repeat a block of code a fixed number of times. Typically, you use the `range()` function to generate a sequence which Python then iterates over as follows:

``` python
for <variable> in range(start , stop , step):
    <block 1>
<block 2>
```

The `range(start, stop, step)` function generates a sequence of numbers from `start`, up to but not including `stop`, in increments of `step`. If the `start` parameter is not included then the sequence starts from `0`, and if the `step` parameter is not included then the sequence goes up in steps of `1`. Note that the name you have chosen for the variable does not matter.

For example, try running the following four code examples:
```python
for x in range(5): # iterates the loop 5 times , from x = 0 to x = 4
    print(x)

for y in range(2,6): # iterates the loop from y = 2 to y = 5
    print(y)

for z in range(1,10,2): # iterates the loop from z = 1 to z = 9 in steps of 2
    print(z)

for i in range(1,-10,-2): # iterates the loop from i = 1 to i = -9 in steps of -2
    print(i)
```

You can also iterate over arrays. For example, the following code gives the output below:

```python
import numpy as np

my_array = np.linspace(0,1,5) # creates an array containing the values [0, 0.25, 0.5, 0.75, 1]
for i in my_array:
    print(i)
```
```
0.0
0.25
0.5
0.75
1.0
```

## Exercise 6:

Write a program that adds together the integers between 1 and 100 (inclusive) using

* a while loop
* a for loop
* a NumPy array and the `np.sum()` function

 
## Exercise 7: The Collatz Sequence

The modulo operator `%`, acting on two variables, i.e. `a % b` gives the remainder when `a` is divided by `b`. As such, we can say that `a` is an even number if `(a % 2) == 0` and odd if `(a % 2) == 1`. We're going to use this operator to help write a program that prints the [Collatz sequence](https://en.wikipedia.org/wiki/Collatz_conjecture) starting with any given integer. To do so, create a new file in the editor and follow these steps:

* Create a variable called `number` and assign it any integer value.
* Create an `if` statement and an `else` statement such that:
    * If `number` is even, redefine `number` as `number/2`. Then print `number` to the console.
    * Otherwise redefine `number` as `3 * number + 1`. Then print `number` to the console.
* Enclose the `if` / `else` pair in a `while` loop, which has the condition that `number` does not equal `1`. (Remember to fix the indenting of the code block - you can highlight the code you wish to indent in the editor and press the *'Tab'* key)
* Run the program, for a few different integer values of number and see how the sequence always returns to `1`. (If there's a mistake in your program and you get an infinite loop, press Ctrl+C on your keyboard to stop it running!)

[Next: Exercise solutions](solutions.md)