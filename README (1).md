
# Gradient Descent for Optimization

Gradient descent is an algorithm used to the find local minima of any differentiable function. More formally, given a differentiable function  f(x),  the gradient descent algorithms helps us compute  x∗  such that  f′(x∗)=0  and  x∗  is a minimum of  f(x).  A function can have many local minima  x∗1,x∗2,…,x∗k,  the gradient descent algorithm will converge to one of them depending on the its starting position and learning rate (discussed below).
The name "Gradient Descent" hints at how this algorithm works. The algorithms requires 1) knowing the  gradient  (partial derivatives) of the function and 2) using the gradient to determine the direction of steepest  descent.  The idea is that we will begin somewhere on the function, for example  f(x1) , and then climb down the function as quickly as possible towards the first valley (local minimum) where  f′(x∗)=0.  The gradient descent algorithm essentially describes the sequence of steps to take to go from  x1  to a local minimum  x∗. 
Gradient descent (or a variation) is very commonly used to train machine learning models by minimizing some objective function. Many of the objective functions in machine learning are hard to minimize analytically, but we can approximate the minimum using gradient descent.


## Algorithm intuition
Suppose we have a single variable function  f(x)  that has a single global minimum (for example a parabola that opens upwards) at  x∗.  Our goal is to approximate  x∗  through an iterative algorithm. The first step is to pick a starting point (initial value) for the algorithm,  x1.  We will randomly guess  x1  and note that either  x1<x∗ , or  x1>x∗  (we can get really lucky and have  x1=x∗,  but this is very unlikely). Since  x∗  is the global minimum, we know that  f(x∗)<f(x1),  that is our starting point is above the minimum. Starting at  x1  we want to take a sequence of steps to get down to  x∗.  The gradient descent algorithm characterizes the set of steps to take to get from  x1  down to  x∗. 
Without loss of generality assume our starting position  x1<x∗,  and let us discuss how to get down towards  x∗.  Recall that we can compute the gradient of  f(x)  since we assume the function is differentiable. Suppose we find  f′(x1)<0,  that indicates that if we take a step right to  x2>x1  then we will move down the function since  f(x2)<f(x1).  This is exactly what we want (moving down the function), so we want to take a step to the right of  x1.  But how large of a step should we take? Well it makes sense to say the step size will depend on the steepness of the descent. The steeper the descent at  x1 , the larger the step size should be as it indicates we have a long way to go before getting to the minimum. More formally the step size will be proportional to the gradient at  x1. 
Once we get from  x1  to  x2 , we repeat the same logic as above. Suppose  f′(x2)<0  again, so we need to take a step towards  x3>x2  to further go down the function. Again our step size will be proportional to  f′(x2).  Repeating this process will result in a sequence of steps  x1,x2,…,xT.  For large values of  T  we expect  xT≈x∗.  The diagram below more formally describes the intuition behind gradient descent.
    
## Screenshots

![App Screenshot](gD.png)

