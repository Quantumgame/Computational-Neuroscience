Discrete Models and Combinatorics
=================================

Randomness is an excause for the lack of knowledge about the details of complex, deterministic systems. The interpretation of measurements in neuroanatomy, neurophysiology, psychophysics, and neuroethology is often based on this aspect.

Randomness is also a method to deal with variability and lack of control all lumped together by intentionally disregarding the details. This aspect introduces an important tool to model structure and fnction of the nervous system.

.. index:: Priori Probability

Priori probability and relative frequency
------------------------------------------------



When N is large enough, the relative probability of event A approaches the priori probability of occurence.

.. math::
   \frac{N(A)}{N}\approx P(A)


.. admonition:: Laplace experiments
   :class: note

   If there is only a finite number of observations, and all occur with the same probability. Then the priori probability could be calculated with:

	.. math::
	   P(A)=\frac{A}{\Omega}
	A is the number of matching observations, and :math:`\Omega` is the total number of obervations.



Combinations and Permutations
------------------------------------------------

ordered sample with repetition: :math:`n^k`

ordered sample without repetition: :math:`\frac{n!}{(n-k)!}`

unordered sample without repetition:  :math:`\frac{n!}{(n-k)!k!}`

unordered sample with repetition: :math:`\begin{pmatrix} n+k+1 \\ k \end{pmatrix}`



Binormial distribution
----------------------------

Bernoulli Experiment
   
.. math::
   X &\sim B(1,p)\\
   \mu & = E[X] = \sum_n X_n \times P(X_n)= p\\
   \sigma^2 & = E[(X-E[X])^2]\\
          & = E[X^2]-E[X]^2 \\
          & = \sum_n X_n^2 \times P(X_n) - p^2 \\
          & = p-p^2


Binomial Distribution


Consider now the n-fold independent repetition of a Bernoulli experiment, :math:`X = X_1 + X_2 + ... + X_n`, :math:`X \sim (n,p)`

.. math::
   P[X=k]= \begin{pmatrix} n \\ k \end{pmatrix} p^k (1-p)^{n-k}


.. math::
   \mu_n & = E[X] = E[X_1 + X_2 + X_3 +...+X_n]\\
         & = E[X_1] + E[X_2] + E[X_3]+... +E[X_n]\\
         & = p+p+p+...+p\\
         & = np\\
   \sigma_n^2 & = \sum_{k=1}^n \sigma^2 = np(1-p)


When n is very large and p is very tiny, Binomial distribution approaches Poisson distribution :math:`X \sim P(\lambda)` or :math:`X \sim \pi(\lambda)` [wait to be verified]


.. math::
   P[X=k] & =\frac{\lambda^k}{k!}e^{-\lambda}\\


Because 

.. math::
	e^x & = \sum_{n=0}^\infty \frac{x^n}{n!}\\
	\mu & = \sum_{k=0}^\infty k P(X=k)\\
       & = \sum_{k=0}^\infty k \frac{\lambda^k}{k!} e^{-\lambda}\\
       & = \sum_{k=1}^\infty \frac{\lambda^{k-1}}{(k-1)!} \lambda e^{-\lambda}\\
       & = \sum_{k=1}^\infty e^{\lambda} \lambda e^{-\lambda}\\
       & = \lambda\\
   \sigma^2 & = E[(X-E[X])^2]\\
   			& = E[X^2]-E[X]^2\\
   			& = \sum X^2 P(X)-E[X]^2\\
   			& = \sum_{K=0}^\infty k^2 \frac{\lambda^k}{k!}e^{-\lambda} -E[X]^2\\
   			& = \sum_{K=1}^\infty k \frac{\lambda^{k-1}}{{k-1}!}e^{-\lambda}\lambda -E[X]^2\\\
   			& = \lambda e^{-\lambda} \sum_{k=1}^\infty (k-1+1) \frac{\lambda^{k-1}}{(k-1)!} -E[X]^2\\
   			& =  -E[X]^2 + \lambda e^{-\lambda} \sum_{k=1}^\infty (k-1) \frac{\lambda^{k-1}}{(k-1)!} + \frac{\lambda^{k-1}}{(k-1)!}\\
   			& =  -E[X]^2 + \lambda e^{-\lambda} (\sum_{k=2}^\infty \frac{\lambda^{k-2}}{(k-2)!}\lambda + \sum_{k=1}^\infty (k-1) \frac{\lambda^{k-1}}{(k-1)!})\\
   			& = -E[X]^2 + \lambda e^{-\lambda} (\lambda e^\lambda + e^\lambda)\\
   			& = -\lambda^2 + (\lambda^2+\lambda)\\
   			& = \lambda


Geometric distribution
A Bernulli experiment is repeated for n times, until event A occours for the first time. The number of trials X needed unitl event A occurs for the first time has a geometric distribution.
:math:`X \sim G(p)`


.. math::
	P[X=k]& =p(1-p)^{k-1}\\
	\mu & = E[x]\\
		 & = \sum_{k=0}^\infty X P(X)\\
		 & = \sum_{k=0}^\infty k p(1-p)^{k-1}\\
		 & ...\\
		 & = \frac{1}{p}\\
	\sigma^2 = \frac{1-p}{p^2}


[wait to be verified]


Hyper-geometric distribution

.. math::
	X \sim H(n,K,N)\\
	P[X=k] & = \frac{\begin{pmatrix}K\\ k\end{pmatrix} \begin{pmatrix} N-K\\ n-k \end{pmatrix}}{\begin{pmatrix} N\\ n \end{pmatrix}}\\
	\mu & = n\frac{K}{N}\\
	\sigma^2 & = n\frac{K(N-K)(N-n)}{N^2(N-1)}



Continious Distributions
===================================


Uniform Distribution
---------------------
.. math::
	f(x) = \frac{1}{l(A)} 1_A(x)\\


:math:`1_A(x)` is a 1 or 0 classification, and :math:`l(A)` is the length of ones. This makes the total size of the square equal to 1.


Normal (Gaussian) Distribution
--------------------------------
.. math::
	f(x) = \frac{1}{\sigma \sqrt{2\pi}}e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^2}\\


[verify the function of variance in the probability density function]


Cauchy Distribution
---------------------
.. math::
	f(x) = \frac{\alpha}{\pi}\frac{1}{\alpha^2+x^2}



Exponential Distribution
-------------------------
.. math::
	f(x) = \lambda e^{-\lambda x}

:math:`\lambda` is rate parameter



Beta distribution
-------------------
.. math::
	f(x) = \frac{v\mu}{v-\mu} (e^{-\mu x}-e^{-v x})


Gamma Distribution
-----------------------
.. math::
	f(x)=\frac{(\mu x)^{\alpha-1}}{(\alpha-1)!}\mu e^{-\mu x}


Piecewise uniform Distribution
-------------------------------
.. math::
	f(x) = r \frac{1}{l(A)}1_A(X) +(1-r) \frac{1}{l(B)}1_B(X)


Mixture of Gaussian distribution
---------------------------------
.. math::
	f(x) = r \frac{1}{\sigma_1 \sqrt{2 \pi}} e^{-\frac{1}{2}(\frac{x-\mu_1}{\sigma_1})^2}+ (1-r) \frac{1}{\sigma_2 \sqrt{2 \pi}} e^{-\frac{1}{2}(\frac{x-\mu_2}{\sigma_2})^2}


Mixture of discrete and continous distributions
-------------------------------------------------
.. math::
	f(x) = rp_1(X) +(1-r)p_2(X)


PDF and CDF
-------------------------------------------------
All functions listed above are probability density functions (PDF), generated by forming the histogram of each process, with infinite small bins.

So the probability of event A, for which A =(a,b) could be denoted as :math:`P[A] = P[a<X<b] = \int_a^b f(x) dx`. However, for a specific value, :math:`x_0`, :math:`P[X=x_0] = \int_{x_0}^{x_0} f(x)dx =0`

To quickly calculate the probability of an event A, cumulative distribution function (CDF) is necessary.


.. math::
	F(x) = P[X<=x] = \int_{-\infty}^x f(y) dy

Then the probability density function could be recovered by forming the derivative

.. math::
	f(x) = \frac{\mathrm{d}}{\mathrm{d}x}F(x)

Additivity of probability is applied, so :math:`P[a<X<=b]=F(b)-F(a)`

And the mean and variance of a PDF is defined the same way as discrete variables.


.. math::
	\mu & = E[X]= \int_{-\infty}^{+\infty} x f(x) dx\\
	\sigma^2 = \mathrm{Var}[X] = \int_{-\infty}^{+\infty} (x-\mu)^2 f(x) dx


Sum of independent random variables
------------------------------------
.. math::
	P[X+Y=Z] & = \sum_{x+y=z} P[X=x,Y=y]\\
				& = \sum_{x+y=z} P[X=x] \times P[Y=y]\\
				& = \sum_y P[X=z-y] \times P[Y=y]\\


Let x and Y have probability density functions :math:`f(x)` and :math:`g(y)` respectively, then the sum z has density:

.. math::
	h(z) = (f \star g)(z) \dot= \int_{-\infty}^{+\infty} f(z-y)g(y)dy


Sum of independent Gaussian variables
--------------------------------------
If :math:`X_1`, :math:`X_2`...:math:`X_n` are independently normally distributed random variables with individual mean :math:`\mu_i` and variance :math:`\sigma_i^2`

.. math::
	X_i \sim N(\mu_i, \sigma_i^2)

(i = 1,2,...,n)

Then the sum :math:`S = \sum_{i=1}^n Xi` is again normally distributed.

.. math::
	S = \sum_{i=1}^n Xi \sim N(\sum_{i=1}^n \mu_i, \sum_{i=1}^n \sigma_i^2)


Let's imagine :math:`X_1`, :math:`X_2`...:math:`X_n` are independently but arbitrary random variables:

.. math::
	X_i \sim D_i (\mu_i, \sigma_i^2)

(i = 1,2,...,n)

Then, for large n, the sum s approximately normally distributed,

.. math::
	S = \sum_{i=1}^n Xi \sim N(\sum_{i=1}^n \mu_i, \sum_{i=1}^n \sigma_i^2)


This is called central limit theorem.

[Does CLT also applied to binomial distribution??]


CLT and biology
----------------
In reality, many results are the sum of many different factors. To get a good approximattion, we assume that these factors are additive. Although the distributions of :math:`X_i` are unkonwn, as long as they are independent, the results :math:`S` is approximately normally distributed.


Transfrom uniform distribution to other random distribution
============================================================

.. math::
	F(U)^{-1} = X


Estimating Distribution from Sampled data
==========================================

Normalized histogram

Kernel Estimator

Empirical distribution function

maximum-likelihood estimation of parameters


Moments
========
First moment:

.. math::
	\mu = \int_{-\infty}^{+\infty}xf(x)dx


second moment:

.. math::
	\sigma^2 = \int_{-\infty}^{+\infty} (x-\mu)^2 f(x)dx

third moment:

.. math::
	\kappa = \int_{-\infty}^{+\infty} (\frac{x-\mu}{\sigma})^3f(x)dx


Linearity of Expectation
-------------------------
.. math::
	E[\alpha X+\beta Y]= E[\alpha X] + E[\beta Y] = \alpha E[X] + \beta E[Y]


functions of a random variable

Let X be a numerical random variable, and :math:`\phi(x)` be a measurable function, so the expectation of :math:`\phi(x)` is:

.. math::
	E[Y] = E[\phi (x)] = \int_{-\infty}^{+\infty} \phi(x) f(x) dx


Centering and standard normal distribution:
--------------------------------------------

Based on the rule proved above, when centering a variable, :math:`\bar X = X-E[X]`, the mean is changed.

.. math::
	E[\bar X] = E[X-E[X]] = E[X] -E[X] = 0


Same, to standarize a normal distribution, the new variable is :math:`\tilde X = \frac{X-E[X]}{\sigma}`, so:


.. math::
	E[\tilde X] & = E[\frac{X-E[X]}{\sigma}] = \frac{E[X-E[X]]}{\sigma} = 0\\



.. math::
	Var[\tilde X] & = E[(\tilde X - E[\tilde X])^2]\\
					  & = E[(\tilde X)^2]\\ 
					  & = E[(\frac{X-E[X]}{\sigma})^2]\\
					  & = \frac{1}{\sigma^2} E[(X-E[X])^2]\\
					  & = \frac{1}{\sigma^2} Var[X]\\
					  & = 1\\


Covariance
===============

.. math::
	\sigma_{XY} \dot = \mathrm{Cov}[X,Y] & = E[(X-E[X])(Y-E[Y])] = E[\bar X \bar Y]\\
												    & = E[XY]-E[X]E[Y]


Boundary of Variance
---------------------

Let :math:`Z = \alpha X +Y`, So the variance of :math:`Z` is:

.. math::
	Var[Z] & = Var[\alpha X+Y]\\
			 & = E[(\alpha X+Y - E[\alpha X+Y])^2]\\
			 & = E[(\alpha (X-E[X]) + (Y-E[Y]))^2]\\
			 & = E[(\alpha \bar X + \bar Y)^2]\\
			 & = E[\alpha ^2 \bar X^2 + \bar Y^2 +2 \alpha \bar X \bar Y]\\
			 & = \alpha ^2 E[\bar X^2] + 2 \alpha E[\bar X \bar Y] + E[\bar Y^2]\\


Because :math:`Var[Z]>=0`, thus:


:math:`\alpha ^2 E[\bar X^2] + 2 \alpha E[\bar X \bar Y] + E[\bar Y^2] >= 0`

For this quatratic polynomial to have true roots, :math:`b^2-4ac>=0`. So:


.. math::
	(2E[\bar X \bar Y])^2 - 4E[\bar X^2] E[\bar Y^2] >= 0\\
	E[\bar X \bar Y]^2 >= E[\bar X^2] E[\bar Y^2]\\
	Cov[X,Y] >= Var[X] Var[Y]



Let :math:`\rho = \frac{Cov[X,Y]}{\sqrt{Var[X]Var[Y]}}`, so :math:`\rho` is located in [-1,1].

:math:`\rho` is called correlation coefficiant

