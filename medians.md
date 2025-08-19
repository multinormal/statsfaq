# The misuse of nonparametric methods in randomized trials

## Introduction

Randomized trials are designed to estimate treatment effects—how outcomes differ, on average, between groups receiving different interventions. Yet trial reports sometimes present medians with quartiles instead of proper treatment effect estimates. While this may seem like a minor issue, it changes the scientific question being answered, risks misleading interpretation, and makes meta-analysis difficult.

This article explains why nonparametric methods are often misapplied in trials, how misunderstandings about distributions contribute to this problem, and what researchers should do instead.

## What Treatment Effects Really Mean

A treatment effect is defined as the difference in expected outcomes between treatment groups. “Expected outcome” refers to the mean outcome in the population of interest. For example:

* For continuous outcomes (e.g., blood pressure, birth weight), the expected outcome is the arithmetic mean.
* For binary outcomes, it could be the mean of log risks or log odds.

This definition is powerful because it provides a direct and intuitive interpretation:

> If everyone received treatment A instead of treatment B, the expected outcome would differ by X units.

Now consider birth weight. Birth weight cannot be negative, so a distribution of birth weight may appear skewed rather than bell-shaped. Despite this skewness, the mean difference remains a sensible choice of treatment effect.

## The Temptation to Publish Medians

Instead of estimating treatment effects with the interpretation above, some trials publish medians and quartiles by treatment arm. This practice is problematic because a difference in medians does not correspond to an expected difference. Readers may draw false conclusions about treatment effects.

It may be tempting to lool at the median when data are skewed, but the median only tells you about the individual whose outcome is at the 50-th percentile, not any other individual, and not those with particularly poor or good outcomes.

There are situations where reporting medians is reasonable—for example, if this was prespecified in the protocol with solid justification. But too often, medians are presented reactively because the data “look non-normal” and trialists believe that nonparametric methods are the only option. This belief reflects a deeper misunderstanding.

## A Common Misunderstanding: Normality Assumptions

A widely held misconception is that outcomes themselves must be normally distributed in order to apply linear regression or related methods.

In truth, it is the residuals—the differences between model predictions and observed outcomes—that should be approximately normal. The outcome variable can follow almost any distribution, provided the regression model is suitable.

This means that skewed outcomes such as birth weight do not automatically justify abandoning regression in favor of medians or other nonparametric methods.

## Why Outcome Distributions Often Look “Strange”

Many outcomes in clinical trials have distributions that appear skewed or irregular. These distributions can often be explained in terms of baseline covariates ("risk factors"):

* Categorical covariates: For birth weight, twins are about 10 times more likely to have very low weight compared to singletons (Centers for Disease Control and Prevention 2024). Mixtures of risk groups create distributions with multiple modes.
* Continuous covariates: Outcome distributions with a mix of continuous covariates (e.g., maternal age and blood pressure) that predict outcome "blur" the outcome distribution, resulting in skewness.
* Sample size limitations: In small samples (fewer than ~1,000 participants), these patterns can be hard to see in a histogram, making distributions look simply “skewed.”

Introductory statistics courses often teach that “skewed data require nonparametric methods” without connecting this skewness to its underlying causes. As a result, many trialists use nonparametric methods when a regression-based approach would be both valid and provide an easily-interpreted treatment effect estimate.

## The Special Case of Time-to-Event Outcomes

Time-to-event outcomes, such as survival time, require particular care. Treating them as continuous outcomes is problematic for two reasons:

1.  Strong skewness: Survival times are usually highly skewed, violating assumptions of unadjusted linear regression.
2.  Censoring: Some participants are event-free at the end of follow-up. Their exact event time is unknown, and standard continuous-data methods cannot handle this censoring properly.

Specialized survival analysis methods (e.g., Kaplan–Meier, Cox regression) were developed precisely to address these issues and should be used instead of median-based analyses. Difference in median survival time is a perfectly reasonable treatment effect to estimate, but requires methods that address the issues above.

## A Better Approach: Covariate Adjustment

In general, trials should handle "non-normal" outcome data using regression-based methods with covariate adjustment (or reasonable alternatives). This generally means:

* Including baseline covariates that are known to predict the outcome (e.g., baseline age and blood pressure).
* Following guidance from regulatory agencies such as the European Medicines Agency (2015) and the U.S. Food and Drug Administration (2023), both of which emphasize covariate adjustment.

Why this matters:

* Interpretability: Results are reported as differences in expected outcomes (means), which align with the treatment effect definition.
* Precision: Adjusted analyses generally yield narrower confidence intervals.
* Regulatory alignment: Both EMA and FDA encourage this approach for primary analyses in randomized trials.

## How to Evaluate Published Trials:

When reviewing a trial that reports only medians, critical questions to ask include:

1.  Was the nonparametric method prespecified in the protocol or analysis plan?
2.  Did the authors provide a sound statistical justification for using medians instead of means?
3.  Do the authors explain the observed distribution and consider whether covariate adjustment might address it?

If the answer to these is “no,” it is plausible that medians were chosen reactively after seeing skewed data—an approach that substantially weakens the trial conclusions.

One should be very skeptical of a trial result based on an analysis that was not prespecified and was likely chosen based on a limited understanding of analytical options due to the high risk of bias in selection of the reported result.

## Conclusion

Randomized trials are designed to estimate treatment effects, not describe group distributions. Reporting medians instead of proper treatment effect estimates risks obscuring the very question that trials are built to answer.

Skewed or “non-normal” data should not automatically push researchers toward nonparametric methods. Instead, trialists should understand the reasons behind outcome distributions and apply appropriate methods such as regression with covariate adjustment.

This approach provides estimates that are interpretable, precise, and aligned with regulatory guidance—ensuring that randomized trials fulfill their purpose of answering questions about treatment effects.

## References

* Centers for Disease Control and Prevention. 2024. Births: Final Data for 2022. National Vital Statistics Reports, Vol. 74, No. 1. Available at: https://www.cdc.gov/nchs/data/nvsr/nvsr74/nvsr74-1.pdf
* European Medicines Agency. 2015. Guideline on adjustment for baseline covariates in clinical trials. Available at: https://www.ema.europa.eu/en/adjustment-baseline-covariates-clinical-trials-scientific-guideline
* Food and Drug Administration. 2023. Adjusting for Covariates in Randomized Clinical Trials for Drugs and Biological Products. Available at: https://www.fda.gov/regulatory-information/search-fda-guidance-documents/adjusting-covariates-randomized-clinical-trials-drugs-and-biological-products