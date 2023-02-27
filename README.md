# Bayesian Modeling 

## Definition & Background:
Def: 

**Bayesian Statistics**

![This is an image of Bayes Theorem](images/bayes_formula.PNG)
![This is an image of intuition of Bayesian Statistics](images/bayes_distro_graph_2.PNG)


## Intuition Behind Method:
The background knowledge is expressed as a prior distribution.  The observational data is expressed in the form of a likelihood function. These are combined to determine the standardized posterior distribution, which can be used for making predictions about future events.

## Use Cases of Bayesian:
- **Small sample sizes**
- **Models are too complex for traditional methods** to handle 
- **Researcher wants to include background information** into the estimation process
- **Desire for complete distributions of credible values** rather than single value estimation

## Steps:
### Key Terms ###

**Prior Distribution** = previous beliefs or information about the parameters in a statistical model before seeing the data; probability distributions for the function parameters

**Likelihood** = the conditional probability distribution of the given parameters of the data, defined up to a constant

**Posterior Distribution** = a way to summarize one’s updated knowledge, balancing prior knowledge with observed data

**Hyper-parameters** = parameters that define the prior distribution, such as mean and variance for a normal distribution

**Prior Predictive Distribution** = the distribution for the joint distribution (e.g. the product of the likelihood and prior); a distribution of all possible samples that could occur if the model is true

**Hyper prior** = a prior distribution on a parameter of a prior distribution; allows one to express uncertainty around what the values of the prior distribution parameters should be

**Marginalization** =

**Joint Probability** = the product of the likelihood and prior; the probability of two events happening together

**Conditional Distribution** =




**1. Collect, Clean and Prepare Data**

Having a good understanding of the context of the problem and data is often key in determining a prior.

**2. Determine Likelihood Function**

Determine the likelihood function (probability density function) using the observational data. The PDF will contain parameters which will be what you are trying to estimate. Prior distributions of possible parameter values will be choosen in the next step.

**3. Define, construct, or select the parameter Priors (also called Prior Elicitation)**

Priors allow you to capture available knowledge about a given parameter in a statistical model. This step is one of the more important choices made when implementing a Bayesian model since it can have a substantial impact on the final results. The informativeness of the posterior depends on the informativeness of the prior.

Methods of obtaining priors:
- ask a subjectmatter expert
- results of a previous publication or analysis
- derived from sample data using MLE (!! Note: be careful of using the same data for crafting priors and as the observational data)

Types of Priors:
- Informative: a high amount of certainty in the estimated parameters; low variance
- Weakly Informative: middle-of-the-road certainty; moderate amount of variance; has less of an impact on the posterior distribution; similar to defining plausible ranges for parameter space
- Diffuse: a high amount of uncertainty; large variance; the observational data will have most of the impact on the posterior


**4. Conduct Prior Predictive Checking**

This is the process of checking whether the choosen parameter priors make sense by generating sample data according to the priors and the likelihood function, and seeing if the results represent any data set that could plausibly be observed. This step is used to improve the understanding of the implications of the specified priors. 

The generation of these samples creates the prior predictive distribution, which is the distribution of observations over all possible values of the parameter. It is important that this prior predictive distribution has some mass around extreme but plausible observations, and no mass on impossible observations. 

Implementation:

a. Simulate parameter value(s) based on the specified prior distribution(s)

b. Use those parameter values to generate a data sample using the likelihood function (this is the same as simulating data from the joint distribution, which is the product of the likelihood and prior)

c. Repeat many times to see what kind of data sets we might expect given the priors (e.g. generate 1000 samples)

d. Create a series of visualizations to scroll through the sample datasets to investigate the variability and multivariate structure of the distribution (e.g. scatterplot of sample data against observational data; empirical cumulative distribution plot of f(x) of each sample)

d. Asses the simulated sample to determine if the data obeys physical constraints and matches your intuition. If it doesn't, consider more appropriate priors

Example:

The below graphs shows the plots of samples generated from a diffuse prior (a) and weakly informative prior (b). Each prior produces very different sample data. The sample data generated by (a) are completely impossible for the context of the example. Inspecting the graphs within the context of the problem (inspecting the y-axis range and what values are feasible), we conclude the diffuse priors do not actually respect the contextual knowledge.

![This is an image of an example prior predictive check](images/bayesian_prior_pred_check.PNG)


**5. Calculate Posertior Distribution, or Joint Distribution**

the product of the likelihood and prior. We use the joint distribution to generate parameter sets and data sets and then check if the results make sense


Combine both the prior distribution and the likelihood function using Bayes’ theorem to output the posterior distribution. The posterior distribution reflects one’s updated knowledge, balancing prior knowledge with observed data, and is used to conduct probabilistic inferences. 


**6. Conduct Posterior Predictive Check**
The idea behind posterior predictive checking is simple: if a model is a good fit then we should be able to use it to generate data that looks a lot like the data we observed

posterior predictive checks are vital for model evaluation

This is a way to validate a model. The idea is to generate data from the model using parameters from draws from the posterior. It analyzes the degree to which data generated from the model deviate from data generated from the true distribution.

If the model fits, then replicated data generated under the model should look similar to observed data. draw simulated values from the posterior predictive distribution of replicated data and compare these samples to the observed data



**7. Conduct a Sensitivity Analysis on Priors**

To fully understand the influence that the prior has on posterior estimates. thoroughly examining the impact of priors through a sensitivity analysis

examine how robust the original results are when the priors are altered, and the model is re-estimated.1 It can also be a method used to identify priors that would serve as a poor choice for the model or likelihood—an issue we expand on more in the discussion.

a. After posterior model is estimated and convergence is obtained for all model parameters, come up with a set of “competing” priors (for one or all parameters) to examine.

b. Obtain posterior model for the “competing” priors (check for parameter convergence) and compare with the original model. If choosing competeing priors for only one of your parameters, while the biggest change in posterior will probably be in that parameter, be sure to also look at the posteriors of the other parameters to see how they are affected. 

_Example of comparing the posterior distributions from competing priors:_

![This is an image of an example of prior sensitvity analysis](images/ex_sens_anlaysis_comparison.PNG)

c. Evaluate how different or similar the posterior distributions are when different priors are formed, and whether the difference is substantively important. One way to evaluate this is to compute the percentage change in the average posterior estimate between models with different prior distributions. This bias estimate is displayed in the last column of the table. A high percentage of bias implies that the posterior estimate is sensitive to the prior distribution used.

![This is an image of an example of prior sensitvity analysis](images/sens_analysis_post_estim.PNG)

d. Include sensitivity analysis results to comment on how robust (or not) the final model results are to different prior settings.







## Resources:
Bayesian Models
- https://osf.io/wdtmc
- http://bebi103.caltech.edu.s3-website-us-east-1.amazonaws.com/2018/tutorials/t6a_model_generation_and_prior_predictive_checks.html
- https://bayesball.github.io/BOOK/bayesian-hierarchical-modeling.html
- https://www.astro.umd.edu/~miller/teaching/astr288a/lecture08.pdf
- https://www.r-bloggers.com/2019/05/bayesian-models-in-r-2/ (R)
- https://statswithr.github.io/book/the-basics-of-bayesian-statistics.html
- https://github.com/markdregan/Bayesian-Modelling-in-Python (Python)
- http://modernstatisticalworkflow.blogspot.com/2017/05/model-checking-with-log-posterior.html
- http://www.stat.columbia.edu/~gelman/book/BDA3.pdf
- https://nyu-cdsc.github.io/learningr/assets/kruschke_bayesian_in_R.pdf (R)


Prior Elicitation

- https://etd.ohiolink.edu/apexprod/rws_etd/send_file/send?accession=osu1306344172&disposition=inline
- https://www.geos.ed.ac.uk/~acurtis/assets/Runge_etal_BSSA_2013.pdf

Prior Predictive Check

- https://rss.onlinelibrary.wiley.com/doi/full/10.1111/rssa.12378 (R)
- http://bebi103.caltech.edu.s3-website-us-east-1.amazonaws.com/2018/tutorials/t6a_model_generation_and_prior_predictive_checks.html
- https://pablobernabeu.github.io/2022/bayesian-workflow-prior-determination-predictive-checks-and-sensitivity-analyses/


Posterior Predicitive Check & Sensitivity Analysis

- https://rss.onlinelibrary.wiley.com/doi/full/10.1111/rssa.12378 (R)
- http://www.stat.columbia.edu/~gelman/bayescomputation/bdachapter6.pdf
- https://www.frontiersin.org/articles/10.3389/fpsyg.2020.608045/full
