# Gradient descent minimization

Gradient descent is an extremely popular iterative optimization algorithm, used to find the local minimum of a function. For a function of one variable *f(x)* , you start with an initial value *x<sub>0</sub>*, and the iteration goes like

*x<sub>n+1</sub> = x<sub>n</sub> - γf'(x<sub>n</sub>)*

Here *γ* is the *'learning rate'* and *f'(x<sub>n</sub>)* is the value of the gradient of the function you wish to minimize *df/dx* evaluated at *x<sub>n</sub>*.  Gradient descent in 1D is quite intuitive

* if *df/dx* at *x<sub>n</sub>* is **positive**, then you want to take a step to the **negative** direction
* if *df/dx* at *x<sub>n</sub>* is **negative**, then you want to take a step to the **positive** direction
* The greater the gradient, the larger step you want to take in that direction

This is illustrated in the figure below.  Here we always want our iterations to move towards lower values for the function.

![Intuitive picture of the gradient descent algorithm](images/grad-descent-intuition.png)

If you change the negative sign in the above equation to a positive sign, you would get the iteration for the gradient ascent algorithm which finds the local maximum of a function. For simplicity however we're just going to focus on gradient descent. 

To illustrate this algorithm, we will again look at the function *f(x) = (x−5)<sup>2</sup>* , which has a gradient *f'(x) = 2x−10* , and perform a few iterations 'by hand'. Here we'll start with an initial value  *x<sub>0</sub> = 1* and a learning rate *γ = 0.9* If we have chosen *x<sub>0</sub>* and *γ* appropriately, this process should tend towards the minimum value of *x=5* after a large number of iterations.

|i|x|
|---|---|
|0|*x<sub>0</sub> = 1*|
|1|*x<sub>1</sub> = x<sub>0</sub> - γf'(x<sub>0</sub>) = 8.2*|
|2|*x<sub>2</sub> = x<sub>1</sub> - γf'(x<sub>1</sub>) = 2.44*|
|3|*x<sub>3</sub> = x<sub>2</sub> - γf'(x<sub>2</sub>) ≈ 7.05*|
|4|*x<sub>4</sub> = x<sub>3</sub> - γf'(x<sub>3</sub>) = 3.36*|
|5|*x<sub>5</sub> = x<sub>4</sub> - γf'(x<sub>4</sub>) ≈ 6.31*|


Here you see successive iterations are getting closer and closer to the expected value of *x = 5*. The figure below shows a visualization of the values of *x* we have iteratively calculated.

![Visualization of gradient descent](images/gd-visualisation-p9.png)

Here you see that wherever the gradient is negative (i.e. for *x < 5* in this case), the value of *x* is increases (i.e. moves to the right) in the next iteration. Conversely, wherever the gradient is positive (i.e. for *x > 5* in this case), the value of *x* is decreased (i.e. moves to the left) in the next iteration. Note also that the greater the gradient, the larger the adjustments will be made to *x<sub>n</sub>*. Whenever we approach the minimum value, the gradient tends towards zero and the adjustment becomes progressively smaller.

The adjustment can also be adjusted by modifying the learning rate, *γ* but care must be taken when choosing its value. if you choose too small a value, then it can take a large number of iterations for gradient descent to converge. If you choose too large a value however, gradient descent can overshoot the minimum, fail to converge or diverge.  Three different learning rates for our example are shown below.

![Visualization of gradient descent for learning rate 0.1](images/gd-visualisation-p1.png)

![Visualization of gradient descent for learning rate 0.9](images/gd-visualisation-p9.png)

![Visualization of gradient descent for learning rate 1.03](images/gd-visualisation-1p03.png)