CS 391L: Machine Learning

Summer 2024

# Homework 5 - Theory 

Lecture: Prof. Qiang Liu

## 1. Gaussian Multivariate

Assume we have a multivariate normal random variable $X=\left[X_{1}, X_{2}, X_{3}, X_{4}\right]^{\top}$, whose covariance matrix $\Sigma$ and inverse covariance matrix $Q$ are

$$
\Sigma=\left[\begin{array}{cccc}
0.71 & -0.43 & 0.43 & 0 \\
-0.43 & 0.46 & -0.26 & 0 \\
0.43 & -0.26 & 0.46 & 0 \\
0 & 0 & 0 & 0.2
\end{array}\right] \quad Q=\left[\begin{array}{cccc}
5 & 3 & -3 & 0 \\
3 & 5 & 0 & 0 \\
-3 & 0 & 5 & 0 \\
0 & 0 & 0 & 5
\end{array}\right]
$$

Note that $Q$ is simply the inverse of $\Sigma$, i.e., $Q=\Sigma^{-1}$.

(a) [5 points] Are $X_{3}$ and $X_{4}$ correlated?

(b) [5 points] Are $X_{3}$ and $X_{4}$ conditionally correlated given the other variables? That is, does $\operatorname{cov}\left(X_{3}, X_{4} \mid X_{1}, X_{2}\right)$ equal to zero?

(c) [5 points] Please find the Markov blanket of $X_{2}$. Recall that the Markov blanket of $X_{i}$ is the set of variables (denoted by $X_{M_{i}}$ ), such that

$$
X_{i} \perp X_{\neg\{i\} \cup M_{i}} \mid X_{M_{i}}
$$

where $\neg\{i\} \cup M_{i}$ denotes all the variables outside of $\{i\} \cup M_{i}$.

(d) $\left[5\right.$ points] Assume that $Y=\left[Y_{1}, Y_{2}\right]^{\top}$ is defined by

$$
\begin{aligned}
& Y_{1}=X_{1}+X_{4} \\
& Y_{2}=X_{2}-X_{4}
\end{aligned}
$$

Please calculate the covariance matrix of $Y$.

## 2. Expectation Maximization (EM)

Assume we have a dataset of two points $\left\{x^{(1)}, x^{(2)}\right\}$ :

$$
x^{(1)}=-1, \quad x^{(2)}=1
$$

Assume $x^{(i)}$ is drawn i.i.d. from a simple mixture distribution of two Gaussian components:

$$
f\left(x \mid \mu_{1}, \mu_{2}\right)=\frac{1}{2} \phi\left(x \mid \mu_{1}, 1\right)+\frac{1}{2} \phi\left(x \mid \mu_{2}, 1\right)
$$

where $\phi\left(\cdot \mid \mu_{i}, 1\right)$ denotes the probability density function of Gaussian distribution $\mathcal{N}\left(\mu_{i}, 1\right)$ with mean $\mu_{i}$ and unit variance. We want to estimate the unknown parameters $\mu_{1}$ and $\mu_{2}$.
(a) [5 points] Assume we run EM starting from an initialization of $\mu_{1}=-2$ and $\mu_{2}=2$. Please decide the value of $\mu_{1}$ and $\mu_{2}$ at the next iteration of EM algorithm. (You may find it handy to know that $1 /(1+\exp (-4)) \approx 0.98)$.

(b) [5 points] Do you think EM (when initialized with $\mu_{1}=-2$ and $\mu_{2}=2$ ) will eventually converge to $\mu_{1}=-1$ and $\mu_{2}=1$ (i.e., coinciding with the two data points). Please justify your answer using either your theoretical understanding or the result of an empirical simulation.

(c) [5 points] Please decide the fixed point of EM when we initialize it from $\mu_{1}=\mu_{2}=2$.

(d) [5 points] Please decide the fixed point of $\mathbf{K}$-means when we initialize it from $\mu_{1}=-2$ and $\mu_{2}=2$.

