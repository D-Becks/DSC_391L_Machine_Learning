CS 391L: Machine Learning

# Homework 4 - Theory 

Lecture: Prof. Qiang Liu

Note: Please typeset your answer ( $\mathrm{LAT}_{\mathrm{E}} \mathrm{X}$ recommended) and upload it on edX.

1. Assume $X$ is a discrete random variable that takes values in $\{1,2,3\}$, with probability defined by

$$
\begin{aligned}
& \operatorname{Pr}(X=1)=\theta_{1} \\
& \operatorname{Pr}(X=2)=2 \theta_{1} \\
& \operatorname{Pr}(X=3)=\theta_{2}
\end{aligned}
$$

where $\theta=\left[\theta_{1}, \theta_{2}\right]$ is an unknown parameter to be estimated.

Now assume we observe a sequence $D:=\left\{x^{(1)}, x^{(2)}, \ldots, x^{(n)}\right\}$ that is independent and identically distributed (i.i.d.) from the distribution. We assume the number of observations of the values: $1,2,3$ in $D$ are $s_{1}, s_{2}, s_{3}$, respectively.

(a) [5 points] To ensure that $\operatorname{Pr}(X=i)$ is a valid probability mass function, what constraint should we put on $\theta=\left[\theta_{1}, \theta_{2}\right]$ ? Write your answers quantitatively as expressions that include $\theta_{1}$ and $\theta_{2}$.

(b) [5 points] Write down the joint probability of the data sequence

$$
\operatorname{Pr}(D \mid \theta)=\operatorname{Pr}\left(\left\{x^{(1)}, \ldots, x^{(n)}\right\} \mid \theta\right)
$$

and the $\log$ probability $\log \operatorname{Pr}(D \mid \theta)$.

(c) [5 points] Calculate the maximum likelihood estimation $\hat{\theta}$ of $\theta$ based on the sequence D.

2. [10 points] Let $\left\{x^{(1)}, \ldots, x^{(n)}\right\}$ be an i.i.d. sample from an exponential distribution, whose the density function is defined as

$$
f(x \mid \beta)=\frac{1}{\beta} \exp \left(-\frac{x}{\beta}\right), \quad \text { for } \quad 0 \leq x<\infty
$$

Please find the maximum likelihood estimator (MLE) of the parameter $\beta$. Show your work.

3. (a) [10 points] Assume that you want to investigate the proportion ( $\theta$ ) of defective items manufactured at a production line. You take a random sample of 30 items and found 5 of them were defective. Assume the prior of $\theta$ is a uniform distribution on $[0,1]$. Please compute the posterior of $\theta$. It is sufficient to write down the posterior density function upto a normalization constant that does not depend on $\theta$.

(b) $[10$ points $]$ Assume an observation $D:=\left\{x^{(1)}, \ldots, x^{(n)}\right\}$ is i.i.d. drawn from a Gaussian distribution $\mathcal{N}(\mu, 1)$, with an unknown mean $\mu$ and a variance of 1 . Assume the prior distribution of $\mu$ is $\mathcal{N}(0,1)$. Please derive the posterior distribution $p(\mu \mid D)$ of $\mu$ given data $D$.

