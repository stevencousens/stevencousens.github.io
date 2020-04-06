
# Introduction to the Monte Carlo method

Monte Carlo simulation is a way of using randomness to help solve problems by exploiting the large number of calculations that computers can perform each second.  Here is one example to illustrate the idea.

## Worked example: Monte Carlo simulation using two dice using a `for` loop

You roll two fair, six-sided dice (one is red and one is green). What is the likelihood that the number shown on the red die is greater than that shown on the green? In this case, you could calculate the probability directly (it works out as P(red>green) = 5/12 ≈ 0.4167.  However, you could also perform an experiment to try and empirically determine this probability.  This is especially useful whenever the problem does not have a simple solution that can be worked out mathematically. To do this, you might come up with the following procedure:

* Preparation:
    * Decide how many trials (rolls of the dice) you would like to perform and get a piece of paper ready to record a tally of your results
* Perform the experiment:
    * For the desired number of trials:
        * Roll the two dice
        * If the value of the red die is greater than the green, make a mark on your tally
* Calculate the result:
    * Obtain an estimate of the probability by dividing the number of marks on your tally by the total number of trials.

If you perform this experiment for a large number of trials, you could expect the observed ratio to tend towards the true probability.  However, this experiment would take a very long time to get a meaningful number of results.

Another approach is to use computers to simulate the problem.  This procedure can be implemented in Python as shown in the code below.  This code models the roll of a die by generating a random number between 1 and 6 by using the `np.random.randint()` function we have met previously.  This is an appropriate distribution to draw from as each integer is equally likely.

``` python
import numpy as np

# step 1: preparation
num_trials = 1000 # number of times the dice are rolled
num_success = 0 # number of times the red die value is greater than the green die value

# step 2: perform numerical experiment for the desired number of trials
for i in range(num_trials):
    red_value = np.random.randint(1, 7) # generates a single value for the red die
    green_value = np.random.randint(1, 7) # generates a single value for the green die
    if red_value > green_value:
        num_success += 1 # if the red value is greater than the green value, increase num_success by 1

# step 3: calculate the result
print("Simulated probability: ", num_success / num_trials) # calculates and prints the simulated probability
```
Try running the above code a few times and notice that you get a slightly different result each time, because of the randomness involved. Observe also that by increasing the number of trials, the simulated probability typically gets closer to the theoretically correct value of 5/12. It is therefore important when running Monte Carlo simulations to ensure that the number of trials you use is appropriate.  However, in the above example if you increase the `num_trials` variable too much then the code takes a long time to finish.  For example, if you set `num_trials = 10000000` then the code takes ~20 seconds to run on a QUB library computer (recall you can always stop a program in a long loop by pressing Ctrl+C). 

**Later in the notes this week we're also going to look at a much quicker way to perform this numerical simulation using NumPy arrays.**
