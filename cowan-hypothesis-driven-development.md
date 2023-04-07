# Hypothesis Driven Development
## by Alex Cowan

### **Ch 5 - From Release to Experimentation**
+ John Lind - British navy surgeon, 1740s, likely carried out the first document controlled trial. He discovered a correlation between citrus consumption and reduced incidence of scurvy. However, he hypothesized the cause was acidity, not vitamin C, and issued sailors a boiled tincture of citrus. Had he followed up after this implementation, he would have noticed that the treatment was not having the intended result. Instead, it took much longer to discover the correct causal link and successfully treat scurvy in the navy.

Some study designs:
1. *Retrospective Case Control:* look at past data to find association between DV and IV. +: observational, cheap, use existing data. -: highly susceptible to unknown confounders
> Ronald Fisher - namesake of Fisher exact test - supported a theory that lung cancer was caused by a gene which happened to make smoking more attractive, not that smoking caused lung cancer
2. *Prospective Cohort Study:* define cohort, track exposure to IV, and observe effects on DV. +: more control over confounders, -: needs to be run intentionally.
3. *Randomized control experiment*: define representative cohort, randomize into control/treatment. Allows reasonably measurement of causality.

A business example: A/B tests are almost always RCE's (choose population of interest, define subjects, randomize into A/B groups, measure outcome)

**Some stats** to enable actionable inference [20]:

Frequentist =
+ Null: there is no relationship between DV and IV
+ Alt.: there is a relationship between DV and IV
+ t-test: two-sided when hypothesis does not specify direction of effect
+ consider that the relative weights of alpha and beta may be reversed, vs. their classical values, in many business/data scenarios
+ effect size and determining statistical power are very important - can waste a lot of money or goodwill with an inappropriately-sized study 

Bayesian =
+ "What is the probability that our search function improves order conversation by 10 or more pp.?"
+ conditional probabilities allow inclusion of multiple relevant IVs (for DV = % of people that carry an umbrella: is it rainy?) by which you can segment scenarios/users (eg. by location, device type, visit type, etc.)
	+ related keywords: multi-armed bandit, Thompson sampling
+ Bradford Hill criteria: for casual inference from RCCs and PCSs when RCEs are not available. Comes from smoking<>cancer.


**Two key questions** for actionability in HDD:
1. How do we make sure this design is testable [in Continuous Design]?
2. What should we prioritize now, given what we observed? [at sprint transition]

Micro-level, make user stories testable. User stories present scenarios that should be tested with Analytical Questions. AQ's can be answered with Metrics that tell you something about the prevalence or consequences of a particular situation. Metrics are assessed through Experiments. [230]

Where experiments can't be accomplished in a single sprint, tie them to other Agile "rituals." Make sure that the long-term arc of your intended design is supported by smaller, testable chunks.

### **Ch 6 - from Inference to Product Priorities**