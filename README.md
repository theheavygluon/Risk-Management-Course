# Risk-Management-Course

<p align="center">
<img src="https://media.istockphoto.com/photos/financial-data-on-a-monitorstock-market-data-on-led-picture-id523155194?b=1&k=20&m=523155194&s=170667a&w=0&h=PZDTM5x6ElXw5aSgzKtc8F4-cZ2nT6g33mN-8VAUCvM=">
 </p>

**WARNING:** In case a reader plans on using these notebooks as a reference to learning about QRM, I highly advise taking everything said with a grain of salt, as this is not my field of expertise and these notebooks are simply my notes on [this course](https://www.youtube.com/watch?v=KUdZFqY4sxs&list=PL4i4aZbplv9KLOA0T4Vw_6PW_eYEYGSXR) by Prof. Gregor Weiss from University of Leipzig. 

## Introduction

Very often in finance, a decision maker must consider the risk of every action. For example, an insurance business must price their premiums in accordance to the risk of various events, an asset manager must take into consideration their clients' risk tolerance, and a bank must have a model to determine (and ideally quantify) creditworthiness of potential debtors.  This course is aimed at introducing the concept of quantitative risk, mostly in a market/banking context. Topics such as Stochastic Processes, Volatiltiy Forecasting, Mapping Risk Factors to Risk Measures are covered and implemented in Python. After this course, you will ideally be able to tackle questions such as "How do we define risk?", "How do we manage several non-deterministic factors?", "How can I build and backtest a volatility forecasting model?". Note that this course, at least in its current state, does not offer any advanced implementations to the methods described. Rather, all implementations act as proof-of-concepts that one could build sophisticated (sometimes industry level) models on top of. For this reason  I have included a further reading folder filled with research papers, problem sets and advanced sources that one could look through if they find a specific topic particularly interesting/necessary. 

## Who is this for?

These notebooks are designed for someone who has a background in statistics 101 and ideally knows a bit about stochastic processes. Furthermore, knowledge of several financial terms and concepts are assumed, although they're usually basic and could be learned by a quick google search. So, as you can see, there are very little pre-requisites and even those could be learned on the go (notebook 1 covers statistics 101, for example). The only thing I'd really insist on one knowing before reading this is Python. I try to make the code as simple as possible and comment on every line, but if you really want to build on top of this course I suggest having at least intermediate level skills. 


## Dependencies

The dependencies of the Python Implementations are:

 - `pandas 1.5.0`
 - `numpy 1.22.0`
 - `matplotlib 3.6.0`
 - `scipy 1.6.0`
 - `arch 5.3.1`
 - `seaborn 0.12.0`

## Table Of Content

This course consists of 8 lectures:

### [Lecture 1: Introduction to Financial Statistics](https://github.com/theheavygluon/Risk-Management-Course/blob/main/Lecture%201%20-%20Introduction%20to%20Statistics%20.ipynb)

The title of this lecture might be misleading because whilst the content of this notebook shares a lot of content with intro stats courses, the manner and pace in which the content will be delivered assumes basic knowledge of the topic. A more appropriate title is "A Quick Brush up on Statistics In the Context of Finance". 

The main topics of discussion are the following:

 1. Financial Data
 2. Financial Returns
 3. Statistical Variables
 4. Sample Statistics
 5. Two Dimensional Frequency Distributions
 6. Measures of Association 
 
which should hopefully be a good start to the course.

### [Lecture 2: Statistical Distributions and Stochastic Processes](https://github.com/theheavygluon/Risk-Management-Course/blob/main/Lecture%202%20-%20Statistical%20Distributions%20and%20Stochastic%20Processes.ipynb)

The last lecture was focused on "introducing" the core concepts of inferential and descriptive statistics and overall how statistics could be used in finance. In the case of Risk Management, one is often concerned with modeling profit/loss data with various distributions and stochastic processes. This lecture will go through the most common families of statistical distributions and processes that one would encounter in Quantitative Risk Management.

The main topics of discussion are the following:

 1. Probability Distributions in $\mathbb{R}^+$ and $\mathbb{R}^+_0$
 2. Multivariate Distributions
 3. Copulas
 
 ### [Lecture 3: Monte Carlo Simulations](https://github.com/theheavygluon/Risk-Management-Course/blob/main/Lecture%203%20-%20Monte%20Carlo%20Simulations.ipynb)

The previous section was concerned with probability distributions and stochastic processes. When introducing stochastic processes, I proposed a "coin game", which is a game where your friend goes on a 1D random walk according to a coin flip. If by the end of the walk they end up to the right of their initial position, they give you 5 dollars and if they end up to the left, you give them 5 dollars. Us being opportunist finance enthusiasts, we wanted to see if this game could be a valid investment by calculating the expected return (mean) and risk (standard deviation). The problem is that we did not have a formula for this stochastic process and therefore could not derive an expression for $\mu$ and $\sigma$. The way we went around this is by simulating the game hundreds of times and getting an estimation for $\mu$ and $\sigma$, in other words, we ran a Monte Carlo simulation. This section will be concerned with the details of how Monte Carlo simulations work and how we can use them in risk management. 

The notebook will be divided into three parts:

 1. Motivation
 2. Inverse Transform Sampling 
 3. Applications

### [Lecture 4: Time Series Analysis](https://github.com/theheavygluon/Risk-Management-Course/blob/main/Lecture%204%20-%20Time%20Series%20Analysis.ipynb)

Time series analysis is a very useful tool in financial engineering, especially when trying to extract a trend out of a stochastic process, calculate a smooth series (such as those "indicators" eg. SMA, EMA, etc), and forecast future developements of a time series. This notebook should hopefully cover all of these tasks and beyond. 

The main topics of discussion are:

 1. Introduction to TSA
 2. Characteristics of time series
 3. Selected time series models
 4. Model Diagnostics
 5. Practical Example: Volatility Forecasting
 
### [Lecture 5: Sources of Risk](https://github.com/theheavygluon/Risk-Management-Course/blob/main/Lecture%205%20-%20Sources%20of%20Risk.ipynb)

Previously we covered time series analysis and how it can be used to perform techniques like volatility forecasting and modeling stocks prices. We will now shift towards describing the sources of risk, which is heavily dependent on the notion of a probability space. 

The main topics of discussion are:

 1. Probability Spaces
 2. Fundamental Risk Factors
 3. Risk Mapping

### [Lecture 6: Risk Measures](https://github.com/theheavygluon/Risk-Management-Course/blob/main/Lecture%206%20-%20Risk%20Measures.ipynb)

The previous lecture covered risk mapping, which should output a loss distribution $L_{t+1}$. This lecture will be conerned with how to make such a distribution useful by introducing several methods for measuring risk. Such methods are used in financial institutions to perform tasks such as pricing insurance premiums, managing assets and determining how much capital one can afford to deploy on an investment given its risk. 

The main topics of discussion are:

 1. Basics of risk measurement
 2. Axiomization of risk measure theory
 3. Important risk measures
 4. Standard techniques for calculating VaR

### [Lecture 7: Risk Backtesting and Forecasting](https://github.com/theheavygluon/Risk-Management-Course/blob/main/Lecture%207%20-%20Risk%20Backtesting%20and%20Forecasting.ipynb)

So far, we have learned how to take a series of risk factors, map them to a loss distribution and use that distribution to define various risk measures (most notably, VaR and CVaR). This lecture will cover how to control, that is to review and assess the quality of a risk models you are using by backtesting or stress testing. This is done with the goal of overall improvement. 

The main topics of discussion are the following:

 1. Forecasting
 2. Backtesting
 3. VaR estimation: a practical example

### [Lecture 8: Extreme Value Theory](https://github.com/theheavygluon/Risk-Management-Course/blob/main/Lecture%208%20-%20Extreme%20Value%20Theory.ipynb)

Say you run an insurance business for high end vehicles. When pricing insurance premiums, you must not only take into account scratches and dents, but rather also one of your client's superyachts setting on fire. Here we will introduce extreme value theory (EVT), which is concerned with modeling events that are far from the mean of a probability distribution (e.g one of your client's superyachts setting on fire).

The main topics of discussion are the following:

 1. Introduction
 2. Block Maxima Method
 3. Threshold Exceedances
 4. Estimation of Risk based on Extreme Value Theory




## References

This course is heavily based on the following resources:

[1] _Weiss, Gregor_. “Quantitative Risk Management", Leipzig University (Fall, 2021)

[2] _McNeil, Alexander & Frey, Rüdiger & Embrechts, P.._ (2015). Quantitative risk management: Concepts, techniques and tools: Revised edition. Quantitative Risk Management: Concepts, Techniques and Tools: Revised Edition. 1-699. 

[3] _Olofsson, Andersson_. Probability, Statistics, and Stochastic Processes: Revised edition. 


<hr>

Unfinished Business:
 
 - MLE + Regression + ML
 - Finish Copula section
 - Implement Univariate distribution fitting in some insurance math context
 - ~~Implement ARCH and GARCH (and maybe even ARMA or GARCH-ARMA)~~ 
 - Do Bond Portfolio and Credit Portfolio + Python Implementation
 - Monte Carlo Simulation to Calculate VaR
