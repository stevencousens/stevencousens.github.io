# Scope in Python

One thing to keep in mind is that parameters and variables created inside a function exist only in that function's *'local scope'*. The scope refers to the places that you can see or access a variable.

If you define a variable **outside** any function then it is a *'global'* variable and can be accessed anywhere in your code.  In the following example, the `global_variable` is created outside of a function. Run this and the following examples in the Spyder editor and check the output in the console to get a feel for how scope works in Python.

``` python
global_variable = "This variable can be accessed anywhere in the code."

def function():
    print(global_variable)

function()
```

However, if you define a variable **inside** a function, then it can only be accessed inside that function. After the function has finished running, the local variable is cleared from memory.  In the next example, `local_variable` is created inside a function, which is then called.  Whenever we try to access this variable outside the function, we get an error because `local_variable` no longer exists.

``` python
def function2():
    local_variable = "This variable can only be accessed inside this function"

function2()
print(local_variable)
```

Arrays with global scope can be modified inside arrays, e.g.

``` python
def function3():
    x_array[1] = 2 # sets the second element of the global x_array variable to 2

x_array = np.array([0,0,0]) # creates a global variable x_array

function3()
print(x_array)
```

However, care has to be taken when trying to reassign variables inside functions.  In the below example, a global variable called `x` is created.  If we try to change this value inside the function, it does not work because the assignment operator `=` inside `function4()` creates a new local variable also called `x`.  As such, the value of `1` from the global variable is printed to the console.

``` python
def function4():
    x = 2 # a new local variable called x is created in this scope, i.e. the global variable is not modified

x = 1 # defines a global variable called x
function4()

print(x) # this will print the global variable x
```

 
