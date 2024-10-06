# A/B Testing
 
## What is A/B Testing?
The purpose of A/B testing is to compare different content and design samples in pairs. However, this purpose may differ depending on the system in which we perform the test. In addition to being used mostly on applications, websites and advertisements, it is a test that can be applied in almost all decisions that can be taken thanks to the digital competencies we have. AB Testing outputs help us make accurate predictions. In summary, it can be said that they are experiments in which only one of more than one variable is changed and which variant performs better under equal conditions.

## How to Do A/B Testing?
When doing A/B testing, there are some factors that you need to pay attention to in order to be able to do it in the most effective way.

**Period**: Both versions should be tested at the same time. If version A is tested in September and version B is tested in November, we won't know if the results are different because of timing and not because of different elements.

**Randomness**: Test groups should be randomly and equally divided so that the results are unbiased.

**Time**: If the test is only done for a short time, the results may not be enough to make a decision.

The correct test method must be selected. statistical hypotheses must be properly established and tested.

## Steps for the A/B Test
**Prepare the Data**:

Ensure your dataset is clean and separated by old_page and new_page.

**Choose a Metric**:

Decide which metric (Clicks, Purchases, Earnings, etc.) you will test.

**Set up Hypotheses**:

Based on the metric you choose:

- H0: There is no difference in [Clicks/Purchases/Earnings] between the old_page and the new_page.

- H1: There is a significant difference in [Clicks/Purchases/Earnings] between the old_page and the new_page.

**Check for Normality**:

Apply the Shapiro-Wilk test (shapiro()) to check if your data follows a normal distribution.

**Test for Variance**:

Use Levene's Test (levene()) to check if the variances between the two groups are equal.

**Select a Statistical Test**:

- **Parametric Test**: If the data is normally distributed and the variances are equal, use a t-test (ttest_ind()).

- **Non-Parametric Test**: If the data does not follow a normal distribution, use a non-parametric test like the Mann-Whitney U test (mannwhitneyu()).

**Interpret the Results**:

Based on the p-value, determine if you can reject the null hypothesis.

- If p-value < 0.05, reject H0 (there is a statistically significant difference).

- If p-value > 0.05, fail to reject H0 (no significant difference).

## Formulating a Hypothesis
1. Assumption is Normality

2. Assumption is Variance Homogenity

- If assumptions are provided then two independent sample t-tests (parametric testing) will be applied

- If assumptions are not provided than Mann-Whitney U test (non-parametric test) will be applied

### Normality Assumption
It is possible to use various normality tests in order to reveal whether the data are suitable for normal distribution. The most well-known of these tests are Chi-Square, Kolmogorow-Smirnov, Lilliefors and Shapiro-Wilk normality tests. Among these, we will use the SHAPIRO-WILK test.

#### Shapiro-Wilk Test
Shapiro-Wilk and Kolmogorov-Smirnov are the most commonly used tests for the normal distribution test, and their hypotheses are basically the same. In contrast to other comparison tests the Shapiro-Wilk test is only applicable to check for normality.

- H0: The variable has a normal distribution. p-value > 0.05

- H1: The variable does not have a normal distribution. p-value < 0.05

### Variance Homogenity Assumption
#### Levene's Test
Levene's test is used to test the homogeneity of group variances. It is run when groups are two or more. In other words, it is used in independent groups t test and Anova test. It is not used in the t test in dependent groups where the number of groups is odd.

- H0: Variances are Homogeneous.

- H1: Variances are not Homogeneous.

### Independent Samples T Test
The independent sample t-test is used to test whether there is a statistically significant difference between two independent groups by looking at the means. This test is a parametric test and some assumptions (pre-requisites) must be fulfilled in order to report the results of the test.

### Mann–Whitney U test
It is a non-parametric method used to compare the means of two independent groups in a distribution that does not show normal distribution. Since this test is a non-parametric test, no assumptions are necessary regarding the distribution of the scores obtained.

A few necessary prerequisites for this test can be listed as follows:

- The independent variable must be categorical.

- The dependent variable must be continuous or sequential.

- The sample selected from the population should be random.

- The scores obtained from the groups should not show normal distribution.

## Another Aspect - Conversion of Impression to Click
### Two Proportion Z-Test
The Two-Proportions Z-Test is used to compare two ratios. Whether, There is a statistically significant difference between the click rate averages of control and test groups or not.

## Conclusion
Running an A/B test that directly compares a variation to a current experience allows you to ask questions about changes to your website or app and then collect data on the impact of that change.

Based on the assumptions in website optimization, the test allows to make analyzes about business processes that can be called "we know" instead of "we think". By measuring the impact of changes on your metrics, you can get an idea of the consequences of each change.

To sum it up, let's review once again what you need to do the A/B test.

- Basic data should be collected

- Goals must be set

- Establish an assumption (estimate how a particular element might perform better)

- A variable must be created (a variable must be created to oppose the existing element based on the assumption)

- Run the test (must take into account time, means, etc.) Be sure to test both versions (control and test) simultaneously to ensure validity of results

- Analyze the results – review the results to make sure the desired effect is achieved. Then choose which version performs better.
