# Variables and Data types in Python

## Variables

In Python you can create variables to store numbers (or other forms of data, as we will see later) simply by inputting its name and assigning it to a value by using the = operator. These numbers can then be later recalled simply by typing the name of the variable.

There are a couple of restrictions as to which names you can use for your variables:
* They can contain uppercase or lowercase letters (`A`-`Z`, `a`-`z`), numbers (`0`-`9`) or the underscore (`_`) character.  However, the first character of the variable name cannot be a number.
* They can't be one of the Python *'keywords'* that are reserved for other uses, such as `if`, `True` or `for`. To find out a complete list of keywords, enter `help("keywords")` into the console.

By convention, variables are usually lower-case only, with words separated by underscores for readability, e.g. `my_variable`.

 
### Worked example:

For example, if we wanted to calculate the area of a circle of radius 10 meters using the equation A = πr<sup>2</sup>, we could use the code below, typed into the console. 
```python
In [1]: pi = 3.14

In [2]: circle_radius = 10

In [3]: circle_area = pi * circle_radius ** 2

In [4]: circle_area
Out[4]: 314.0
```

Notice that if you input only the name of one of your variables into the console, its value will be outputted automatically (e.g. when the `circle_area` variable name was entered above).

Variables can be reassigned to other values, after which the old value is forgotten.

```python
In [5]: circle_radius = 5

In [6]: circle_radius
Out[6]: 5
```

However, although we have changed the value of the `circle_radius` variable, the value of the `circle_area` variable has not updated automatically. Since we have not reassigned it, it still has the value that was calculated when the `circle_radius` was `10`. We must therefore recalculate `circle_area`. You can quickly access previous commands by clicking beside the input prompt and using the up and down arrow keys on your keyboard.

```python
In [7]: circle_area
Out[7]: 314.0

In [8]: circle_area = pi * circle_radius ** 2

In [9]: circle_area
Out[9]: 78.5
```

A very common form of reassignment is where the new value assigned to a variable depends on the old.

```python
In [10]: circle_radius = circle_radius + 1

In [11]: circle_radius
Out[11]: 6
```

This is such a common occurrence that, for simple data types (e.g. numbers), `a = a + b` can be abbreviated to `a += b`. The operators `-=` , `*=` and `/=` work in a similar manner.


## Data types

You may have noticed that, unlike other languages such as C, you don't need to declare in advance what data type a variable is going to reference.  When you input `a = 1` into the console, the Python interpreter knows that `1` is an integer and so the variable `a` is automatically assigned that type. Python also has the floating point type which, as you may recall from C, is a representation of a number with a decimal point. Python also automatically handles mixed arithmetic between data types. For example, when we calculated the area of a circle, we used both `circle_radius`, which was stored an integer, and the `pi` variable, which was stored as a floating point number. The `circle_area` variable was automatically set to a float type to avoid loss of precision.

Although the Python interpreter handles a lot of the details behind the scenes, understanding data types is still important (especially as it influences function behaviour), as we will see throughout the course. We will also encounter a number of other data types, most notably:

* Strings, which are sequences of characters, defined between either single or double quotations, e.g. `my_string = 'hello'` or `my_string = "hello"`.
* Lists, which are sequences of Python objects of any data type. You can create a simple list by surrounding the objects in square brackets, e.g. `my_list = [ 3.14, 42, 'a coconut', [1,'2']]`.
* NumPy arrays, which are sequences of objects all of the same data type. Because of this specificity, there are lots of really useful, optimized functions that make data manipulation easier. This data type is defined in the 'NumPy' module, which is described in the next section.

You can check what data type a variable is by using the `type()` function, e.g. if you input `type(my_list)` into the console, the word `'list'` would be printed to the screen.