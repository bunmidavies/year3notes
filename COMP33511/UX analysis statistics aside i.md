[[COMP33511]]

# descriptive statistics + inferential statistics
- descriptive statistics is mainly concerned with analysing data concerning to the standard normal distribution - patterns you could expect an entire population to exhibit
- descriptive statistics often exists as a platform to understand what inferential statistics you'll actually require, in order to make accurate analyses - you often perform tests known as measures of central tendency, graphing data to understand any skew or bias

- inferential statistics are used to support your samples characteristics in the context of the general population - the key aspect is the t-test
- parametric tests are tests applied to data that exhibit a standard normal distribution
- non-parametric tests are typically applied to data that is not normally distributed
- in the case of UX you're typically only collecting data from say, 15-40 participants, so since your sample size isn't huge you probably won't have a normal distribution, so you're typically more concerned with non-parametric testing

# sampling
- participants are the most important aspect of an evaluation plan, since by not choosing a ==representative sample== you're setting yourself up for failure, since you cannot validate your work accurately
- a bunch of sampling methods, both probabilistic and non-probabilistic exist ([[UX.pdf#page=279]]):
	- ==probabilistic==
	- simple random sampling
	- systematic sampling
	- stratified sampling
	- multistage sampling
	- ==non-probabilistic==
	- quota sampling - fill up a quota of some desired demographic
	- snowball sampling - ask participants to nominate another person within the same required demographic
	- convenience sampling - ask whoever is easiest to ask!
	- judgemental sampling - specifically selecting participants that can bring more accurate results/relevant info (like quota but without the initial categorisation performed by quota)
- for typical UX evaluation, quota and judgemental are used, but also snowball and convenience

# 'evaluation++'
- below are a list of experimental designs which vary in the method of participant sampling, as well as when evaluation is carried out:
	- single group, post-test - evaluation only occurs after the artefact to be tested, has been created - there is only one group of participants for user testing
	- single group, pre-test + post-test - evaluation occurs before and after the artefact has been produced (so before would be when you have some sort of low fidelity design to present?), so in some sense you can determine whether there has been an improvement in interaction
	- natural control group, pre-test + post-test - natural control group = a naturally occurring group perhaps sampled through convenience methods - variance between sample groups in this case can be detected
	- randomised control group, pre-test + post-test - like above, but wih the added validity of a randomised sample, perhaps strengthening external validity
- additionally, there's also the concept of ==within-subjects== design - all participants are exposed to different conditions of the independent variable (i.e. your interface)
- realistically, what you end up selecting here probably ends up being more of a pragmatic choice than anything

# A/B testing
- a/b testing involves you developing two separate versions of the same interface, typically with some minor changes in order to investigate the effects of such changes
- interface users are randomly split (i.e. 50/50) such that one group sees one version, while the other group sees the other version
- objective data-driven insights can be extracted from this, but some ethics concerns need be addressed
- pre-test and post-test takes similar ideas, but pre-test and post-test is more concerned about effects over time, meanwhile you will have two separate sets of results at what would assumed to be the same time