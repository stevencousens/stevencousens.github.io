# Vectorizing calculations using NumPy arrays

Earlier this week we wrote a program which used a `for` loop to answer the following question: *"You roll two fair, six-sided dice (one is red and one is green). What is the likelihood that the number shown on the red die is greater than that shown on the green?"*

In Python there is another way of solving these kinds of problems using whats known as *'vectorization'*.  Here all the random numbers are drawn at once, rather than one at a time during a loop.  This turns out to be a very computationally efficient approach, so the code will run more quickly and larger-scale simulations can be performed.

We can then use our Boolean index masking techniques to calculate the probability directly from the arrays, as shown in the example below. Note that for 10000000 trials, this code takes approximately 0.2 seconds to run on a QUB library computer i.e. this is 100 times quicker than the loop version.

``` python
import numpy as np

num_trials = 10000000

red_values = np.random.randint(1, 7, num_trials) # generates an array of all trial values for the red die
green_values = np.random.randint (1, 7, num_trials) # generates an array of all trial values for the green die

num_success = np.sum(red_values > green_values) # uses a mask to find the number of True values

print("Simulated probability: ", num_success/num_trials) # prints the simulated probability
```

