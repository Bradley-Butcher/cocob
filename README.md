# COCOB
TensorFlow implementation of COCOB from the paper

**[Backprop without Learning Rates Through Coin Betting](https://arxiv.org/abs/1705.07795)**  
Francesco Orabona and Tatiana Tommasi  
https://arxiv.org/abs/1705.07795  

### Description

COntinuous COin Betting (COCOB) is a novel algorithm for stochastic subgradient descent (SGD) that does not require 
any learning rate setting. Contrary to previous methods, we do not adapt the learning rates, nor we make use of the 
assumed curvature of the objective function. Instead, we reduce the optimization process to a game of betting on a 
coin and obtain a learning rate free procedure for deep networks.

*How do we reduce SGD to coin betting?*  
Betting on a coin works in this way: start with $1 and bet some money **w<sub>t</sub>** on the outcome of a coin toss 
**g<sub>t</sub>**, that can be +1 or -1. Similarly, in the optimization world, we want to minimize a 1D convex function 
**f(w)**, and the gradients **g<sub>t</sub>** that we can receive are only +1 and -1. Thus, we can treat the gradients 
**g<sub>t</sub>** as the outcomes of the coin toss, and the value of the parameter **w<sub>t</sub>** as the money bet in 
each round.  
If we make a lot of money with the betting it means that we are very good at predicting the gradients, and in optimization 
terms it means that we converge quickly to the minimum of our function. More in details, the average of our bets will converge 
to the minimizer at a rate that depends on the dual of the growth rate of our money.

*Why using this reduction?*  
Because algorithms to bet on coins are already known, they are optimal, parameter-free, and very intuitive. So, in the 
reduction we get an optimal parameter-free algorithm, almost for free. Our paper extends a known betting strategy to 
a data-dependent one.

*Is this magical?*  
No, you could get the same results just running in parallel copies of SGD with different learning rates and then combining them
with an algorithm on top. This would lead exactly to the same convergence rate we get with COCOB, but the advantage here is that 
you just need to run one algorithm!


### Usage



