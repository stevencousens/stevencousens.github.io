# Forward Euler method

The [Euler method](https://en.wikipedia.org/wiki/Euler_method) is a numerical technique for solving first-order ordinary differential equations of the form *y'(x) = f(x,y)*, given an initial condition *y(x<sub>0</sub>) = y<sub>0</sub>*. Most of these differential equations cannot be solved analytically by simple means but the solution can be approximated numerically.

The diagram below illustrates the idea behind the Euler method. Here you start with your given point on the solution *(x<sub>0</sub>, y<sub>0</sub>)*.  From the form of the differential equation you know that the gradient of the solution at *x<sub>0</sub>* is *f(x<sub>0</sub>,y<sub>0</sub>)* and you can form the tangent line.  For a step size *h* you take a new point *x<sub>1</sub> = x<sub>0</sub> + h*.  The value for *y<sub>1</sub>* at *x<sub>1</sub>* can then be approximated by assuming it is on the tangent line via *y<sub>1</sub> = y<sub>0</sub> + hf(x<sub>0</sub>,y<sub>0</sub>)*, which is valid for small values of *h*.  This process can then be iterated starting at the new point *(x<sub>1</sub>, y<sub>1</sub>)*

![Schematic of forward Euler method](images/euler-method.png)

The Euler method can be written as difference equations as follows:

*x<sub>i+1</sub> = x<sub>i</sub> + h*

*y<sub>i+1</sub> = hf(x<sub>i</sub>, y<sub>i</sub>)*.