# CS 391L: Machine Learning 

Summer 2024

## Homework 6 - Programming

Lecture: Prof. Qiang Liu

## 1. Kernel Regression

Given a training data $\left\{\boldsymbol{x}_{i}, y_{i}\right\}_{i=1}^{n}$, kernel regression approximates the unknown nonlinear relation between $\boldsymbol{x}$ and $y$ with a function of form

$$
y \approx f(\boldsymbol{x} ; \boldsymbol{w})=\sum_{i=1}^{n} w_{i} k\left(\boldsymbol{x}, \boldsymbol{x}_{i}\right)
$$

where $k\left(\boldsymbol{x}, \boldsymbol{x}^{\prime}\right)$ is a positive definite kernel specified by the users, and $\left\{\boldsymbol{w}_{i}\right\}$ is a set of weights, estimated by minimizing a regularized mean square error:

$$
\min _{\boldsymbol{w}}\left\{\sum_{i=1}^{n}\left(y_{i}-f(\boldsymbol{x} ; \boldsymbol{w})\right)^{2}+\beta \boldsymbol{w}^{\top} \boldsymbol{K} \boldsymbol{w}\right\}
$$

where $\boldsymbol{w}$ is the column vector formed by $\boldsymbol{w}=\left[w_{i}\right]_{i=1}^{n}$ and $\boldsymbol{K}$ the $n \times n$ matrix by $\boldsymbol{K}=$ $\left[k\left(\boldsymbol{x}_{i}, \boldsymbol{x}_{j}\right)\right]_{i j=1}^{n}$, and $\beta$ is a positive regularization parameter. We use a simple Gaussian radius basis function (RBF) kernel,

$$
k\left(\boldsymbol{x}, \boldsymbol{x}^{\prime}\right)=\exp \left(-\frac{\left\|\boldsymbol{x}-\boldsymbol{x}^{\prime}\right\|^{2}}{2 h^{2}}\right),
$$

where $h$ is a bandwith parameter. A common way to set $h$ in practice is the so called "median trick", which set $h$ to be the median of the pairwise distance on the training data, that is,

$$
\hat{h}_{\text {med }}=\operatorname{median}\left(\left\{\left\|\boldsymbol{x}_{i}-\boldsymbol{x}_{j}\right\|: i \neq j, i, j=1, \ldots, n\right\}\right)
$$

(1) [10 points] Complete the code of kernel regression following the instruction of the attached Python notebook. Specifically, you need to complete all the code necessary for function

kernel_regression_fit_and_predict to run.

(2) [10 points] Run the algorithm with $\beta=1$ and $h \in\left\{0.1 \hat{h}_{\text {med }}, \hat{h}_{\text {med }}, 10 \hat{h}_{\text {med }}\right\}$. Show the curve learned with different $h$ in the notebook and comment on how $h$ influences the smoothness of the curve.

(3) [10 points] Use 5-fold cross validation to find the optimal combination of $h$ and $\beta$ within $h \in\left\{0.1 \hat{h}_{\text {med }}, \quad \hat{h}_{\text {med }}, \quad 10 \hat{h}_{\text {med }}\right\}$ and $\beta \in\{0.1,1\}$.

