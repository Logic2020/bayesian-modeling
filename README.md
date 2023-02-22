# Bayesian Hierarchical Modeling 
(also called multilevel modeling)

## Definition & Background:
Def: a statistical model used on data with a nested or hierarchy structure that estimates the parameters of the posterior distribution using the Bayesian method

**Bayesian Statistics**

![This is an image of Bayes Theorem](images/bayes_formula.PNG)
![This is an image of intuition of Bayesian Statistics](images/bayes_distro_graph_2.PNG)


## Intuition Behind Method:
The background knowledge is expressed as a prior distribution.  The observational data is expressed in the form of a likelihood function. These are combined to determine the standardized posterior distribution, which can be used for making predictions about future events.

## Use Cases of Bayesian:
- **Small sample sizes**

## Steps:
### Key Terms ###

**Prior Distribution** = previous beliefs or information about the parameters in a statistical model before seeing the data; probability distributions for the function parameters

**Likelihood** = the conditional probability distribution of the given parameters of the data, defined up to a constant

**Posterior Distribution** = a way to summarize one’s updated knowledge, balancing prior knowledge with observed data

**Hyper-parameters** = parameters that define the prior distribution, such as mean and variance for a normal distribution

**Prior Predictive Distribution** = the distribution for the joint distribution (e.g. the product of the likelihood and prior)

**Hyper prior** =

**Marginalization** =

**Joint Probability** = the product of the likelihood and prior; the probability of two events happening together

**Conditional Distribution** =


### _Stage I: Prior Distribution_ ###

**1. Define, construct, or select the Priors (also called Prior Elicitation)**

Capture available knowledge about a given parameter in a statistical model via the prior distribution. This is typically determined before data collection. This step is one of the more important choices made when implementing a Bayesian model since it can have a substantial impact on the final results. The informativeness of the posterior depends on the informativeness of the prior.

Methods of obtaining priors:
- ask a subjectmatter expert
- results of a previous publication or analysis
- derived from sample data using MLE (!! Note: be careful of using the same data for crafting priors and as the observational data)

Types of Priors:
- Informative: a high amount of certainty in the estimated parameters; low variance
- Weakly Informative: middle-of-the-road certainty; moderate amount of variance; has less of an impact on the posterior distribution; similar to defining plausible ranges for parameter space
- Diffuse: a high amount of uncertainty; large variance; the observational data will have most of the impact on the posterior


### _Stage II: Likelihood Function_ ###

**2. Collect Data and Check Assumptions**

Determine the likelihood function (probability density function) using the observational data.

**3. Clean and Prepare Data**

**4. Determine Likelihood Function**



**5. Conduct a Prior Predictive Check**
The process of checking whether the priors make sense by generating data according to the prior in order to assess whether the results are within the plausible parameter space. This step is used to improve the understanding of the implications of the specified priors, not a method for changing the prior.

The prior predictive distribution is the distribution of observations "averaged" over all possible values of the parameter.

Steps:

a. Simulate parameters based on the specified prior distribution

b. Simulate sample data based on the likelihood function using the simulated parameters (this is the same as simulating data from the joint distribution, which is the product of the likelihood and prior)

c. Asses the simulated sample to determine if the data obeys physical constraints and matches your intuition


**6. Conduct a Prior Sensitivity Analysis**
To fully understand the influence that the prior has on posterior estimates.


**7.**




**8. Conduct Likelihood Sensitivity Analysis**


### _Stage III: Posterior Distribution_ ###
Combine both the prior distribution and the likelihood function using Bayes’ theorem to output the posterior distribution. The posterior distribution reflects one’s updated knowledge, balancing prior knowledge with observed data, and is used to conduct probabilistic inferences. 


**9. Conduct Posterior Predictive Check***

This is a way to validate a model. The idea is to generate data from the model using parameters from draws from the posterior. It analyzes the degree to which data generated from the model deviate from data generated from the true distribution.





## Resources:
Bayesian Models
- https://osf.io/wdtmc
- https://bayesball.github.io/BOOK/bayesian-hierarchical-modeling.html
- https://www.astro.umd.edu/~miller/teaching/astr288a/lecture08.pdf
- https://www.r-bloggers.com/2019/05/bayesian-models-in-r-2/ (R)
- https://statswithr.github.io/book/the-basics-of-bayesian-statistics.html
- https://github.com/markdregan/Bayesian-Modelling-in-Python
- http://modernstatisticalworkflow.blogspot.com/2017/05/model-checking-with-log-posterior.html
- http://www.stat.columbia.edu/~gelman/book/BDA3.pdf


Prior Elicitation

- https://etd.ohiolink.edu/apexprod/rws_etd/send_file/send?accession=osu1306344172&disposition=inline
- https://www.geos.ed.ac.uk/~acurtis/assets/Runge_etal_BSSA_2013.pdf

Prior Checking and Sensitivity Analysis
- http://bebi103.caltech.edu.s3-website-us-east-1.amazonaws.com/2018/tutorials/t6a_model_generation_and_prior_predictive_checks.html
- https://pablobernabeu.github.io/2022/bayesian-workflow-prior-determination-predictive-checks-and-sensitivity-analyses/
- http://www.stat.columbia.edu/~gelman/bayescomputation/bdachapter6.pdf
- https://www.frontiersin.org/articles/10.3389/fpsyg.2020.608045/full


