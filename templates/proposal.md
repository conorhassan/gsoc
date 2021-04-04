#  Title 

GARCH models in BRMS.

## Abstract

The student will implement common General Autoregressive Conditional Heteroskedasticity (GARCH) style models for users in the brms R package. The R package brms is a frontend for Stan that allows R users to write R formula syntax for models that is translated and compiled into a Stan model. Currently brms allows for arma style models on the mean, but does not support GARCH style models on the variance. The student will code up several of these models in Stan, testing with simulation based calibration that the models are well calibrated, write a technical document describing the GARCH model form and how it can be incorporated into brms, then implement these models directly into brms. Challenges from brms side will be to determine which of all the other modeling options can be combined with GARCH models. For example, how to combine GARCH models on sigma with distributional regression in sigma. Other difficulties will be to implement all the post-processing such as posterior predictions etc. The existing ARMA terms already pave the way for all of this but we will have to figure out if the current structure is satisfactory for autoregressive terms to be applied to distributional parameters other than the mean. There are also other minor difficulties such as if/how GARCH models can be combined with a covariance formulation of ARMA models on the mean arma(..., cov = TRUE). These are all details we have to figure out in the process.

## Technical Details

Long description of the project. **Must** include all technical details of the
projects like libraries involved.

Here it is important to show if you had previous conversations with your
mentors. You can show relevant pieces of code that you want to change. You can
link to literature you used during the research.

## Schedule of Deliverables

Here should come a list of your milestones. This list is a start based on the
difference phases of GSoC. Use it as a start. You can/should add more details
for each phase by breaking it down into weeks or set specific targets for each
phase. Each target should be split into sub task with a time estimate, [work
breakdown structures][wbs] are helpful here.

### **Community Bonding Period**

This phase is to get to know the community better. Check that your build
environment is setup. This time should also be used to discuss your project in
more detail with the community and in general introduce it. 

*Note:* We require you to write regular blog posts. Now is a good time to make
sure your blog works and send us the link.

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

At this stage you should finish up your project. At this stage you should make
sure that you have code submitted to your organization. Our criteria to mark
your project as a success is to submit code before the end of GSoC.

## Development Experience

Do you have code on github? Can you show previous contributions to other projects?
Did you do other code related projects or university courses?

## Other Experiences

I have exposure to Stan and BRMS during a research internship, where we built multi-level hierachical models for the parasitic resistance shown on New Zealand farm(s). My Honours dissertation focused vaguely on Bayesian-type methods (though looking back it looks rather cringeworthy). I have completed coursework involving Bayesian inference and time series modelling to a high level (A+'s), and have used volatility models in an internship with a high frequency trading firm. Currently, I am about to begin my PhD studies focusing on Bayesian Federated Learning at Queensland University of Technology.

## Why this project?

I have a strong interest in producing open source software during my research studies. Although I have only recently registered an account on the Stan forums, lurking in the forums, including finding the helpful responses of a few of the potential mentors for this project, have helped me greatly with the modelling I have done in Stan and BRMS to date. 

## Appendix

Extra content

[wbs]: https://en.wikipedia.org/wiki/Work_breakdown_structure
