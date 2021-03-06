Measurements and Models
++++++++++++++++++++++++++++++++


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
	Cov[X,Y]^2 >= Var[X] Var[Y]



Let :math:`\rho = \frac{Cov[X,Y]}{\sqrt{Var[X]Var[Y]}}`, so :math:`\rho` is located in [-1,1].

:math:`\rho` is called correlation coefficiant


Principal Component Analysis
=============================


Mixture of orthogonal variables
--------------------------------

Let :math:`U` and :math:`V` be uncorrelated variables, :math:`Var[U] = 1`, :math:`Var[V] = 1`, and :math:`Cov[U,V]=0`.

Then variables :math:`X` and :math:`Y` are mixtures of :math:`U` and :math:`V`.

.. math::
	X = \alpha U+ \beta V\\
	Y = \gamma U + \delta V\\
	\mathrm{Cov}[X,Y] & = E[XY]-E[X]E[Y]\\
							& = E[(\alpha U+ \beta V)(\gamma U+\delta V)] - E[\alpha U+ \beta V]E[\gamma U+\delta V]\\
							& = \alpha \gamma (E[U^2]-E[U]^2) +(\alpha \delta+ \gamma \beta)(E[UV]-E[U]E[V]) + \beta \delta (E[V^2]-E[V]^2)\\
							& = \alpha \gamma \mathrm{Var}[U] +(\alpha \delta+ \gamma \beta)\mathrm{Cov}[U,V] + \beta \delta \mathrm{Var}[V]\\
							& = \alpha \gamma + \beta \delta\\




Conditional Probability
=====================================


For events A and B, with :math:`P(B) \neq 0`, one defines

.. math::
	P(A|B) = \frac{P(A \cap B)}{P(B)}


A and B are stochastically independent, if:

.. math::
	P(A \cap B) = P(A)P(B)\\
	P(A|B) = P(A)\\



Assume that two events are neither impossible nor sure. If one is the becassary consequence of the other one, or if they are incompatible, they cannot be independent.

So A and B are stochastically dependent, if:

.. math::
	P(A \cap B) \ neq P(A) P(B)\\
	P(A|B) \neq P(A)


Bayes' Rule
--------------------------------------


.. math::
	P(A|B) & = \frac{P(A \cap B)}{P(B)}\\
	P(B|A) & = \frac{P(B \cap A)}{P(A)}\\


so,

.. math::
	P(A|B)P(B) = P(A \cap B) = P(B \cap A) = P(B|A) P(A)\\



More generally, let :math:`B_1`, :math:`B_2`,...,:math:`B_n` be a disjoint cover of the space :math:`\Omega`:

.. math::
	\Omega = B_1 \cup B_2 \cup ... \cup B_n

with :math:`B_i \cap B_j = \emptyset` for all :math:`i \neq j`. so :math:`P(\Omega)=1`


One can write the probability :math:`P(A)`:


.. math::
	P(A|\Omega) & = \frac{P(A \cap \Omega)}{P(\Omega)}\\
	P(A) & = \frac{P(A \cap \Omega)}{1}\\
		  & = \sum_{i=1}^{n} P(A \cap B_i)\\
		  & = \sum_{i=1}^{n} P(A|B_i) P(B_i)\\


so,

.. math::
	P(B_j|A) & = \frac{P(B_j \cap A)}{P(A)}\\
				& = \frac{P(B_j \cap A)}{\sum_{i=1}^{n} P(A|B_i) P(B_i)}\\
				& = \frac{P(B_j)P(A|B_j)}{\sum_{i=1}^{n} P(A|B_i) P(B_i)}\\



Smoothing and Averaging
========================================

We seek a model that describes a noisy system with one input and one output variable, and within the system, noise are added.


First Step: Visulization
---------------------------

Graphical representation of the simutaneous measurements of input X and output Y.


Basic Hypothesis
------------------

The concept of additive noise is frequently employed to model stochastic system.

Output = Signal(Input)+Noise

The signal has a deterministic part that only depends on the input and a stochastic part that is independent of the input.

The additional silent assumption is that the noise term is normally distributed, with zero mean and constant variance. (According to central limit theorem)

Averaging, smoothing, and Fitting
---------------------------------
To separate the signal from noise, or supress noise partially. The most frequently used methods are:

(1) averaging over repeated and uncorrelated observations.

(2) smoothing (filtering) by leveling out neighboring data points.

(3) fitting a parametric model



(In the case of correlation of noise components, or if noise is added in a non-linear way, avaraging, smoothing, and fitting should be operate with care.)



Noise Reduction by Averaging
----------------------------


Consider a numeric random variable :math:`X` with:

.. math::
	\mathrm{E}[X] =\mu
	\mathrm{Var}[X] = \sigma^2

An example is :math:`X=S+N`, where :math:`S=\mu` is the signal, and :math:`N` is the normally distributed nosie with zero mean and variance :math:`\sigma^2`. For an ensemble :math:`X_1`, :math:`X_2`,...,:math:`X_n` of uncorrelated observations of :math:`X` the arithmetic mean is:

.. math::
	Y & = \frac{1}{n}\sum_{i=1}^{n}X_i\\
	E[Y] & = E[\frac{1}{n}\sum_{i=1}^{n}X_i]\\
		  & = \frac{1}{n} E[\sum_{i=1}^{n}X_i]]\\
		  & = \frac{1}{n} n E[X]\\
		  & = E[X]\\
	Var[Y] & = Var[\frac{1}{n}\sum_{i=1}^{n}X_i]\\
		  & = \frac{1}{n^2} Var[\sum_{i=1}^{n}X_i]\\
		  & = \frac{1}{n^2}nVar[X]\\
		  & = \frac{1}{n}\sigma^2\\


So, :math:`\sqrt{Var[Y]} = \frac{\sigma}{\sqrt{n}}`, this is called Standard Error of the Mean (SEM).

If :math:`X_1`,:math:`X_2`,...,:math:`X_n` are correlated ensembles,

.. math::
	Var[Y] = Var[\frac{1}{n}\sum_{i=1}^{n}X_i] = \frac{1}{n^2}Cov[X_i,X_j]<=\frac{1}{n}\sigma^2



Regression
-----------------------


To fit a model, :math:`y(x)=y_a(x)`, in which :math:`a =(a_1,a_2,...,a_m)`, is to determine the parameters :math:`a`.

Maximum likelihood and least squares are used (they are the same thing).

.. math::
   L = \prod_{i=1}^{n} \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{1}{2}[\frac{y_i-y_a(x_i)}{\sigma}]^2}


.. math::
   \chi^2 = \sum_{i=1}^{n}[\frac{y_i-y_a(x_i)}{\sigma}]^2

To determine the proper parameter :math:`a`s, :math:`\chi^2` should be minimal. So,

.. math::
   \frac{\partial}{\partial a_i} \chi^2 = 0

for all :math:`i`.


How to use matrix to solve linear model
-----------------------------------------

Let :math:`f_1(x)`, :math:`f_2(x)`,...,:math:`f_m(x)` be arbitrary fixed funxtions, the basis functions. A linear combination:

.. math::
   y_a(x) = a_1f_1(x)+...+a_mf_m(x)

serves as a model with parameters :math:`a=(a_1, a_2,..., a_m)` to be determined from empirical data. So for any empirical data :math:`(x_i,y_i)`:

.. math::
   y_i \sim a_1f_1(x_i)+...+a_mf_m(x_i)

should hold approximately for all sample points.


.. math::
   \begin{pmatrix} y_1\\...\\y_n \end{pmatrix} \sim \begin{pmatrix} f_1(x_1) ... f_m(x_1)\\... ...\\f_1(x_n) ... f_m(x_n) \end{pmatrix} \begin{pmatrix} a_1 \\ ... \\ a_m \end{pmatrix}\\


   \begin{pmatrix} a_1 \\ ... \\ a_m \end{pmatrix} \sim \begin{pmatrix} f_1(x_1) ... f_m(x_1)\\... ...\\f_1(x_n) ... f_m(x_n) \end{pmatrix} ^{-1} \begin{pmatrix} y_1\\...\\y_n \end{pmatrix}



When judging whether a model is proper, maximum likelihood (or least square) is not enough. Another index is probability to encounter the measured value of :math:`\chi^2`, it is :math:`Q`.

Values of :math:`Q` above 0.1 is a good approximation. If :math:`Q` is below 0.001, it is overfitting, so this model is not properly describing the data, or the noise of data is too high or not normally distributed. For values in between, if it is known that noise is not normally distributed, this model could be accepted.



information theory
===============================

Information is expressed by code: using words composed of letters from a given alphabet to represent a set of objections for the purpose of communication.

Two major properties of code: injectivity and prefix property.

And code could be divided into different types: coarse or sparse? distributed or local? redundant or non-redundant? balanced or unbalanced?


Entropy
-------------

Entropy quantifies the observer's uncertainty about the outcome of an experiment. To the degree to which the uncertainty is decreased through observations made, the amount of available information increases.

So the entropy of an event A corresponds to the information which is gained through its observation. Entropy should depend only on the probability :math:`P(A)` of observing A:
.. math::
   H(A) = h[P(A)]\\
   H(A) := -log_2 P(A)


The base of the logarithm can be arbitrarily chosen. Commonly, the unit of entropy/information is fixed such that tossing a fair coin yields the information 1 bit (binary digit)

From the observations of a discrete random variable X, which assumes that a value x with probability P(x), we can on average expect the information

.. math::
   H(X) ：= E[H(x)] = -\sum_x P(x) log_2 P(x)

Joint Entropy
----------------------

X and Y are independent variables, the joint distribution is the product of two distributions:

P(x,y)=P(x)P(y)

so,

.. math::
   H(X,Y) & = -\sum_x \sum_y P(y)P(x) log_2 P(x) - \sum_y \sum_x P(x)P(y) log_2 P(y)\\
          & = H(X) +H(Y)


Mutual information
--------------------

Let X and Y are discrete random variables with joint distribution P(x,y) and marginal distribution P(x) and P(y).

The Mutual information is the relative entropy between the joint distribution P(x,y) and th product distribution P(x)P(y)

.. math::
   I(X;Y) := E[H(x)+H(y)-H(x,y)] = H(X)+H(Y)-H(X,Y)


One always has :math:`0<=I(X;Y)<=min{H(X),H(Y)}`. If X and Y are stochastically independent; and observation of X contans no information about Y, yielding :math:`I(X;Y)=0`


Stochastic Process
========================

white noise (wind)
-------------------

all frequencies are represented with uniform power but random phase. (simulation: amplitude is from a Gaussian distribution)

point process
-------------------

Point process is a widely used model for random process, finite and measurable in a state space.

A point or a pulse is a short event, amplitude and duration are ignored. And point process is used to describe system of pulse trains for signaling. And only **finitely** many points are generated in finite observation intervals.

shotnoise (rain)
----------------------

Considering each individual random event triggers a stereotyped deterministic response. So the continuous shotnoise process is the linear superposition of the response to many such random events.

Such shotnoise serves as a good model of post-synaptic membrane potential.


stochastic process
------------------------

stochastic processes are mathematical models for the temporal evolution of system, which are either subject to non-deterministic input, or which exhibit intrinsic random behavior.

Such models are typically specified by:

1.state space
2.initial conditions
3.transition probability


Random walk
-----------------

The particle performs random 'jumps' of size S1, S2, S3, ... at discrete points in time :math:`\tau`, :math:`2\tau`, :math:`3\tau`...

The jumps are all independent and from the same distribution, which is assumed to be isotropic.

If the particle starts its reajectory at position :math:`x_0`, and its position :math:`X_t` at time :math:`t=k \tau` is random, given by

.. math::
   X_t = x_0+ S_1 +...+S_k


so,

.. math::
   E[X_t] = x_0+E[S_1]+...+E[S_k] = x_0\\
   \mathrm{Var}[X_t] & = \mathrm{Var}[S_1]+...+\mathrm{Var}[S_k]\\
                     & =k\mathrm{Var}[S]\\
                     & = \frac{t}{\tau} \mathrm{Var}[S]\\


Chapman-Kolmogorov equation
---------------------------------

.. math::
   f(x,t+\tau)=\int_{-\infty}^{\infty}f(x-s,t)\phi(s)ds


:math:`f(x,t)` is particle density at time :math:`t` for position :math:`x`

:math:`\phi(s)` is probability density for individual jumps

:math:`\int_{-\infty}^{\infty}` is integral (sum) over all possible jumps



Markov Process
=======================
