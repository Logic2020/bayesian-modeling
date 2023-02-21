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

## Steps:
### Key Terms ###
**Prior Distribution** = Beliefs held by researchers about the parameters in a statistical model before seeing the data, expressed as probability distributions
**Likelihood** = The conditional probability distribution of the given parameters of the data, defined up to a constant
**Posterior Distribution** = A way to summarize one’s updated knowledge, balancing prior knowledge with observed data
**Hyper-parameters** = Parameters that define the prior distribution, such as mean and variance for a normal distribution
**Hyper prior** =
**Marginalization** =
**Joint Probability** =
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

**2. Prior Predictive Check**
The process of checking whether the priors make sense by generating data according to the prior in order to assess whether the results are within the plausible parameter space.

**3. **

### _Stage II: Likelihood Function_ ###
Determine the likelihood function (probability density function) using the information about the parameters available in the observed data.

**3. Collect Data and Check Assumptions**
**3. Clean and Prepare Data**
**3. Determine Likelihood Function**

### _Stage III: Posterior Distribution_ ###
Combine both the prior distribution and the likelihood function using Bayes’ theorem to output the posterior distribution. The posterior distribution reflects one’s updated knowledge, balancing prior knowledge with observed data, and is used to conduct probabilistic inferences. 

## Resources:
- https://bayesball.github.io/BOOK/bayesian-hierarchical-modeling.html
- https://www.astro.umd.edu/~miller/teaching/astr288a/lecture08.pdf
- https://www.r-bloggers.com/2019/05/bayesian-models-in-r-2/ (R)
- https://statswithr.github.io/book/the-basics-of-bayesian-statistics.html
- https://github.com/markdregan/Bayesian-Modelling-in-Python
- http://modernstatisticalworkflow.blogspot.com/2017/05/model-checking-with-log-posterior.html
- https://osf.io/wdtmc

- https://etd.ohiolink.edu/apexprod/rws_etd/send_file/send?accession=osu1306344172&disposition=inline
- https://www.geos.ed.ac.uk/~acurtis/assets/Runge_etal_BSSA_2013.pdf



