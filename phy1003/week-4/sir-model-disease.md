# Exercise: SIR model for spread of disease

Differential equations are often used to analyze the spread of infectious diseases. One approach (called the SIR model) divides a population (assumed to be constant) into three groups:

* *S(t)* is the number of people that are susceptible to the disease (i.e. those that are currently healthy, have never had the disease and therefore have not become immune).
* *I(t)* is the number of infective people who have the disease.  They can pass the disease on to susceptible people.
* *R(t)* is the number of people who have recovered (these people are immune to the disease and are no longer infective).

In this model, the rate at which new infections occur is *aSI* for a positive constant *a* and people recover from the disease at a rate of *bI* for a positive constant *b*. This can be modeled by the following system of differential equations:

*Ṡ = -aSI*

*İ = aSI - bI*

*Ṙ = bI*

* Use the forward Euler method to numerically solve this system of equations and plot *S*, *I* and *R* versus time.  Use the following initial conditions:

*a = 0.002*

*b = 0.4*

*Δt = 0.25* (days)

*S<sub>0</sub> = 999*

*I<sub>0</sub> = 1*

*R<sub>0</sub> = 0*
