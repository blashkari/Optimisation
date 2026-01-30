# Optimisation
This repository includes data science optimisation concepts

## Key Components
- 1- **Loss function:** Also known as the objective or cost function, it quantifies the disparity between predicted and actual values. We represent the loss function via $L(\hat{f},f)$. For most optimization algorithms, it is desirable to have a loss function that is globally continuous and differentiable. Two common loss functions are,
  
  - Mean absolute error, also known as the absolute loss ($\ell 1$ loss), i.e., $L(\hat{f},f) = \| \hat{f} - f\|$.
  -  Mean squared error, also known as the squared error loss ($\ell 2$ loss), i.e., $L(\hat{f},f) =  \Vert \hat{f} - f \Vert_2^2$.
Mean absolute error is not differentiable at the origin, while it is less sensitive to outliers

  Squarred error cost function, together with linear regression results, always ends up with a bowl shape 
- 2- **Optimization Algorithm:** A method or strategy to reduce the objective function.


 ## Gradient Descent (GD) Algorithm
 An optimisation algorithm to find the values of the parameters (or coefficients) $\theta$ of a function $f$ that minimizes the cost function. 
 Gradient descent is used when parameters cannot be calculated analytically (using linear algebra) and must be searched for by optimization algorithms. 

 $$ 
 \omega = \omega- \alpha \frac{\partial}{\partial \omega} L(\widehat{f},f)
 $$
 
 Here:
  - $\alpha$ is the learning rate that controls the  step size.
  - $\frac{\partial}{\partial \omega} L(\widehat{f},f)$ is the adjustment term.

You take the direction of the steepest descent.

When you are updating multiple coefficients, e.g., $\omega$ and $b$, the correct way is:

 $$ 
 tmp_\omega = \omega - \alpha \frac{\partial}{\partial \omega} L(\widehat{f},f) 
 $$
 $$
 tmp_b = b - \alpha \frac{\partial}{\partial b} L(\widehat{f},f) 
 $$
 $$
 \omega = tmp_\omega 
 $$
 $$
 b = tmp_b
 $$

If the learning rate $\alpha$ is too small, it means the gradient descent algorithm is taking very small baby steps. It ends up decreasing the cost function $J$ slowly. The GD algorithm works, but slowly.
If  $\alpha$ is too large, the GD algorithm may diverge and never reach its minimum. 

**Fixed learning rate**
Near a local minimum, derivatives become smaller, and the update steps become smaller. So the GD algorithm can reach the minimum without decreasing the learning rate, even with a fixed $\alpha$.
Also, GD with a fixed learning rate can be used for any cost function, not only the MSE.

**Batch gradient descent:**
A challenge is that it can 

