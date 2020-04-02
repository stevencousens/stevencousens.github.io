# Using Python as a basic calculator

## The Spyder IDE

### Opening the Spyder application

In this course, we're going to use the *'Spyder'* application which is especially useful for scientific programming.  Spyder is an acronym (sort of!) for '**S**cientific **PY**thon **D**evelopment **E**nvi**R**onment'.

To open this program, click the *'Search Windows'* icon on the bottom-left corner of your desktop, type *'Spyder'* and left-click the *'Spyder'* icon that appears. The application may take a few moments to open.

![How to open Spyder](https://stevencousens.github.io/qub/phy1003/week-1/images/how-to-open-spyder.png)

When the application is opened, have a look around the main window and you'll see that it consists of a variety of *'panes'*. The default layout is shown below. 

![Panes in Spyder](https://stevencousens.github.io/qub/phy1003/week-1/images/spyder-panes.png)

The two most important panes at this stage are the *'console'* (on the bottom-right) and the *'editor'* (on the left). 

* The **console** allows you to input Python commands one at a time and, if applicable, shows you the results immediately. The console is most useful when learning new concepts and trying out different ideas.  We will start off by using the console.
* The **editor** is used for grouping multiple Python commands together into programs. This acts similarly to text editors such as Notepad, in that you can type your code, save the file (which will have a .py extension) and make edits when required. When you run the .py file, the lines of code will be executed sequentially. Note that the results of calculations performed here will not be immediately shown in the console (but can be outputted using the `print()` function discussed later).

## Fundamental mathematical operations in Python

To begin, we're going to use the *'Console'* pane (which is in the bottom-right corner of the window) as a simple calculator. We can use the `+` , `-` , `*` , `/` operators in the usual way for addition, subtraction, multiplication and division, respectively. Exponentiation is performed using the `**` symbol, so you would write 3<sup>2</sup> as `3**2` in Python.  The order in which these operations are carried out is the same as that used in mathematics, but the use of parentheses `()` is recommended to avoid ambiguity.

Left-click on the console pane, beside the `In [1]:` prompt, type `1 + 1` and then press the 'enter' key on your keyboard. The console should now read `Out[1]: 2`. Congratulations, you have now issued your first Python command! After you input a command and press enter, new prompt is automatically generated in the console, `In [2]:` and you are free to type in further expressions. The integer number inside the square brackets only indicates the number of commands you have issued so far and doesn't affect how the code runs at all.
Syntax errors

If you make a typo in your input and the expression doesn't make sense to the interpreter (for example, try entering `1 + 1 +`) the console will return an error telling you where it occurred what went wrong.

```python
In [1]: 1 + 1 +

File "<ipython-input-1-fd659da33d23>", line 1

1 + 1 +

^

SyntaxError: invalid syntax
```

It's important to gain familiarity with many different types of error during this course (this particular one is a called a SyntaxError). When you're writing more complex programs, this automatic error reporting becomes a very useful feature if they do not run as expected!

 
## Exercise 1: 

Perform the following calculations in the Spyder console and verify that the answers are what you expect.

* 24 - 173
* 20 × 5
* 19 ÷ 4
* 3<sup>4</sup>
* 6 + 20 × 5
* (6 + 20) × 5


The answers to this and the following exercises may be found here.


## Variables in Python

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


## Python data types

You may have noticed that, unlike other languages such as C, you don't need to declare in advance what data type a variable is going to reference.  When you input `a = 1` into the console, the Python interpreter knows that `1` is an integer and so the variable `a` is automatically assigned that type. Python also has the floating point type which, as you may recall from C, is a representation of a number with a decimal point. Python also automatically handles mixed arithmetic between data types. For example, when we calculated the area of a circle, we used both `circle_radius`, which was stored an integer, and the `pi` variable, which was stored as a floating point number. The `circle_area` variable was automatically set to a float type to avoid loss of precision.

Although the Python interpreter handles a lot of the details behind the scenes, understanding data types is still important (especially as it influences function behaviour), as we will see throughout the course. We will also encounter a number of other data types, most notably:

* Strings, which are sequences of characters, defined between either single or double quotations, e.g. `my_string = 'hello'` or `my_string = "hello"`.
* Lists, which are sequences of Python objects of any data type. You can create a simple list by surrounding the objects in square brackets, e.g. `my_list = [ 3.14, 42, 'a coconut', [1,'2']]`.
* NumPy arrays, which are sequences of objects all of the same data type. Because of this specificity, there are lots of really useful, optimized functions that make data manipulation easier. This data type is defined in the 'NumPy' module, which is described in the next section.

You can check what data type a variable is by using the `type()` function, e.g. if you input `type(my_list)` into the console, the word `'list'` would be printed to the screen.

