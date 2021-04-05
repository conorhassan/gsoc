
#  GARCH models in BRMS.

## Abstract

We will implement a number of General Autoregressive Conditional Heteroskedasticity (GARCH) models into the brms package. The family of GARCH model is appropriate for time series data where the variance exhibited by the error term follows an autoregressive moving average process. BRMS is an R package which interfaces with Stan to fit a wide range of models. We will begin by implementing a number of the family of GARCH models within Stan. The calibration of these models will be tested using simulation based calibration. This will test whether the posterior of the data generation process specified by the model(s) can be accurately sampled by the sampling algorithm implemented by Stan. We will then provide documentation describing the models and what other pre-existing modeling options within BRMS can be combined with these GARCH models. Lastly, I would like to provide specific “Bayesian workflow-esqe” tutorials/articles, explaining their usage.

## Technical Details

The student will implement common General Autoregressive Conditional Heteroskedasticity (GARCH) style models for users in the brms R package. The R package brms is a frontend for Stan that allows R users to write R formula syntax for models that is translated and compiled into a Stan model. Currently brms allows for arma style models on the mean, but does not support GARCH style models on the variance. The student will code up several of these models in Stan, testing with simulation based calibration that the models are well calibrated, write a technical document describing the GARCH model form and how it can be incorporated into brms, then implement these models directly into brms. Challenges from brms side will be to determine which of all the other modeling options can be combined with GARCH models. For example, how to combine GARCH models on sigma with distributional regression in sigma. Other difficulties will be to implement all the post-processing such as posterior predictions etc. The existing ARMA terms already pave the way for all of this but we will have to figure out if the current structure is satisfactory for autoregressive terms to be applied to distributional parameters other than the mean. There are also other minor difficulties such as if/how GARCH models can be combined with a covariance formulation of ARMA models on the mean arma(..., cov = TRUE). These are all details we have to figure out in the process.


### **Loosely think what do I want to achieve in this project:**

- implement basic GARCH(p, q) model in BRMS in form consistent with brms models
- give some statement on the possible priors one might use for the model
- simulation-based calibration (what is this exactly?)
- implement in syntax agnostic to that already within existence of the BRMS package
- implement assymmetric GARCH model with Student-t innovations
- provide a "Bayesian Workflow-esque" tutorial where we work through at least one problem, exhibiting different choices that could be made along the way including priors and the different models.
- I’m interested in participating although I’m not sure how much time I’ll have this summer. I was looking at contributing/putting in an application to the BRMS topic because it was how I got into Stan. I have been reading some of the literature on GARCH models and tested few versions of the basic GARCH(1,1) model on simulated data and have some questions. A lot of the literature notes that normally distributed noise is insufficient to fully capture the tails of real data, and suggests a students-t model or even various mixture-type models in newer literature. From testing simulated data and the S&P500 data most textbooks use, the fit was generally much better with the t-noise model unless I was generating data using normal noise. The github page only mentioned gaussian noise models but I would assume we could be flexible on this in our implementation? These models can also be kind of finicky to fit with any kind of weak prior… basically all of the literature uses a uniform prior. I know the end goal would be to implement all of the models listed but testing prior distributions and model specifications seems like a difficult task in it of itself. Will the project be more so focused on implementing all the models and then going back in to test things like priors or will it be more focused on doing a thorough implementation+write-up for each model? Lastly, are there any decent papers/texts that I might be missing for Bayesian Time Series? I’ve mostly been referencing this text by Ruey Tsay but it’s focused mostly on ML.
  -  Supporting more distributions is always awesome, but getting the first steps done of a normal ol’ garch(p, q) should be a nice amount of work on it’s own. As we work out the standard garch(p, q) it should become pretty evident which pieces of the code generation would need to change to support different types of conditional heteroskedasticity and distributions etc. And if we have enough time to do these then that’s super rad!
  -  Yes so we broke it up into milestones so that we would have flexibility in what the GSoC student wanted to do as well. Just doing SBC on a bunch of those models would be worthwhile in itself as a case study! But if the student wants to jump to the BRMS stuff we can just do SBC for the simpler garch models as an exercise and then jump straight to the design process for BRMS.
  -  comment on 4 references involving Bayesian time series.
  -  I agree with @stevebronder applying a GARCH structure to other distributions might be tricky, for example, the t-student innovation GARCH model is a mixture of a normal and gamma distribution, such that the marginal likelihood follows a student-t, or models such as Poisson ARMA models actually are integer GARCH models.
  -  another three references of Bayesian time series tings.

## Schedule of Deliverables

### **Community Bonding Period**

By this stage, I will have already completed some beginner-level PR's to Stan. During this community bonding period, I will:

- contribute to issues being raised on the Stan Discourse regarding time series modelling within BRMS.
- gain a thorough understanding of the structure of Stan code being generated under the hood by the pre-existing time series models.
  - discuss with mentors choices made within the Stan code under the BRMS function calls to ensure I implement optimised Stan code.
- make sure the blog is set up, and promote the beginning of the project, and inform people of what the expected results of the project will be.

### **Phase 1**

#### Week 1 (7th June - 13th June)

#### Week 2 (14th June - 21st June)

#### Week 3 (22nd June - 28th June)

#### Week 4 (29th June - 4th July)

#### Week 5 (5th July - 11th July)

#### Week 6 (12th July - 18th July)

### **Phase 2**

#### Week 7 (19th July - 25th July)

#### Week 8 (26th July - 1st August)

#### Week 9 (2nd August - 9th August)

#### Week 10 (10th August - 16th August)


### **Final Week**

Loololjkkgukiuluiu

## Development Experience

Do you have code on github? Can you show previous contributions to other projects?
Did you do other code related projects or university courses?

## Other Experiences

I have gained exposure to Stan and BRMS during a research internship, where we built multi-level hierachical models for the parasitic resistance shown on New Zealand farm(s). My Honours dissertation focused vaguely on Bayesian-type methods (though looking back it looks rather cringeworthy). I have completed coursework involving Bayesian inference and time series modelling to a high level (A+'s), and have used volatility models in an internship with a high frequency trading firm. Currently, I am about to begin my PhD studies focusing on Bayesian Federated Learning at the Queensland University of Technology.

## Why this project?

I love the BRMS package, and think tooling like this is an awesome step in building pieces of software that help improve Bayesian workflow immensely. I think that the ability to implement time series models that allow for auto-regressive terms to be with both the mean and variance parameters will expose the BRMS package to a much wider audience.

The Stan community has contributed greatly to my knowledge and enjoyment of Bayesian Inference. Although I have only recently registered an account on the Stan forums, lurking in the forums, including finding the helpful responses of a few of the potential mentors for this project, have helped me greatly with the modelling I have done in Stan and BRMS to date. I honestly could not consider continuing my studies in Statistics in an area that was not Bayesian. 

I have a strong interest in producing open source software during my research studies. All of the mentors proposed for this project have been champions of developing open source software for the wider community for a number of years, and I would love to learn from them best practices on how to develop software that is useable and beneficial to the wider community that may access this software. 

## Appendix

Please find attached below my CV and academic transcript:

[CV_Transcript_Conor_Hassan.pdf](https://github.com/conorhassan/gsoc/files/6253976/CV_Transcript_Conor_Hassan.pdf)
