# AP Statistics Capstone: AI Tutoring, Compliance, and Evidence

This is a synthetic AP Statistics investigation. The scenario is realistic, but the data are invented so the statistical reasoning can be evaluated cleanly.

## Scenario

A district is debating whether AI tutoring should be allowed during the learning phase of AP Statistics. Some teachers argue that AI mainly enables cheating. Others argue that AI works like a private tutor: useful during practice, but not a substitute for independent reasoning on assessments.

The district runs a six-week study with 240 AP Statistics students from 8 schools. Within each school, students are randomly assigned to one of two instructional conditions:

- **AI-access condition:** Students may use an AI tutor during practice, homework, and review. They must still show handwritten work and complete in-class checks without AI.
- **standard-resource condition:** Students use AP Classroom videos, teacher notes, textbook examples, and ordinary peer discussion. They may not use AI during the study period.

Researchers measure each student's pretest score, posttest score, daily AI-tutor minutes, phone-policy environment, engagement rating, and whether the student passes a later AP-style practice exam.

Use a significance level of `alpha = 0.05` unless otherwise stated.

## Data

### Table A: One-Variable Data

For 20 randomly selected students in the AI-access condition, the recorded average daily AI-tutor minutes were:

`0, 0, 5, 8, 10, 12, 15, 18, 22, 25, 30, 32, 35, 40, 45, 50, 55, 60, 75, 95`

### Table B: Randomized Study Summary

| Condition | n | Mean pretest | SD pretest | Mean posttest | SD posttest | Mean gain | SD gain | Passed AP-style practice exam |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| AI-access | 120 | 48.2 | 13.8 | 66.8 | 15.6 | 18.6 | 12.4 | 69 |
| Standard-resource | 120 | 48.9 | 14.1 | 58.7 | 16.2 | 9.8 | 11.7 | 47 |

### Table C: Actual AI Use Within the AI-Access Condition

| Actual behavior | n | Mean gain | SD gain | Passed AP-style practice exam |
|---|---:|---:|---:|---:|
| Regular AI tutor use, at least 20 min/day | 76 | 23.4 | 11.6 | 55 |
| Little or no AI tutor use, under 20 min/day | 44 | 10.3 | 10.9 | 14 |

### Table D: School Culture and AI Use

Researchers classify schools by observed technology culture during the study.

| School culture | Regular AI use | Occasional AI use | No AI use | Total |
|---|---:|---:|---:|---:|
| Restrictive phone/AI culture | 21 | 39 | 60 | 120 |
| Open AI-tutor culture | 66 | 34 | 20 | 120 |
| Total | 87 | 73 | 80 | 240 |

### Table E: Regression Summary

For 80 students with complete usage logs, researchers fit a least-squares regression model predicting gain score from average daily AI-tutor minutes.

`gain = 6.2 + 0.085(minutes)`

Additional information:

- `n = 80`
- `r = 0.62`
- `s = 9.8`
- `SE_b = 0.013`, where `SE_b` is the standard error of the slope
- A residual plot shows random scatter with roughly constant vertical spread.
- A histogram of residuals is roughly unimodal and approximately symmetric.

### Table F: Probability Model

Based on a larger district survey, suppose an AP Statistics student independently has probability `p = 0.32` of becoming a regular AI-tutor user when AI access is allowed but not required.

## Questions

### Unit 1: Exploring One-Variable Data

1. Classify each variable as categorical or quantitative: instructional condition, school culture, average daily AI-tutor minutes, gain score, passed AP-style practice exam.
2. Use Table A to make an appropriate graph of AI-tutor minutes. Describe shape, center, spread, and unusual features in context.
3. Find the median, Q1, Q3, IQR, and range of Table A.
4. Use the `1.5 * IQR` rule to determine whether 95 minutes is an outlier.
5. Explain why the mean AI-tutor minutes would be larger than the median for Table A.

### Unit 2: Exploring Two-Variable Data

6. Use Table D to compute the conditional relative frequency of regular AI use within each school culture.
7. Does Table D suggest an association between school culture and actual AI use? Explain using conditional relative frequencies.
8. Interpret the slope `0.085` in Table E in context.
9. Interpret `r = 0.62` in context.
10. Find and interpret `r^2`.
11. Predict the gain score for a student who uses the AI tutor for 40 minutes per day.
12. Explain why it would be risky to use the regression line to predict the gain score for a student who uses AI for 180 minutes per day.

### Unit 3: Collecting Data

13. Identify the experimental units, treatments, and response variables in the six-week study.
14. Explain why random assignment within each school improves the study.
15. Explain why blocking by school would be sensible in this study.
16. Can the randomized comparison in Table B support a cause-and-effect conclusion about AI access? Explain.
17. Can the comparison in Table C support a cause-and-effect conclusion about actual AI use? Explain carefully.
18. Identify one possible source of bias if students self-report their AI minutes.
19. Explain how noncompliance can contaminate the interpretation of a treatment effect.

### Unit 4: Probability, Random Variables, and Probability Distributions

20. Using Table D, find `P(regular AI use)`.
21. Using Table D, find `P(open AI-tutor culture)`.
22. Using Table D, find `P(regular AI use | open AI-tutor culture)`.
23. Are regular AI use and open AI-tutor culture independent in Table D? Justify numerically.
24. Suppose 5 students are randomly selected from a population where `p = 0.32` for regular AI-tutor use. Find the probability exactly 2 are regular AI-tutor users.
25. Let X be the number of regular AI-tutor users among 5 randomly selected students with `p = 0.32`. Find `E(X)` and `SD(X)`.
26. Find the probability that the first regular AI-tutor user appears on the fourth student selected.

### Unit 5: Sampling Distributions

27. For samples of size 120 from a population with true pass proportion `p = 0.50`, describe the approximate sampling distribution of `p-hat`. Check conditions.
28. If the true mean gain under the standard-resource condition is 10 points with population SD 12, describe the approximate sampling distribution of the sample mean gain for `n = 120`.
29. Under the null hypothesis that the two pass proportions are equal, explain why the observed difference in pass rates from Table B might or might not be surprising.
30. Explain why larger sample sizes make it easier to detect smaller real differences.

### Unit 6: Inference for Categorical Data: Proportions

31. Construct a 95% confidence interval for the proportion of AI-access students who passed the AP-style practice exam.
32. Construct a 95% confidence interval for the difference in pass proportions, `p_AI - p_standard`, using Table B.
33. Interpret the interval from Question 32 in context.
34. Test whether the AI-access condition produced a higher pass proportion than the standard-resource condition.
35. Explain the meaning of the p-value from Question 34 in context.
36. Describe a Type I error and a Type II error for the test in Question 34.

### Unit 7: Inference for Quantitative Data: Means

37. Construct a 95% confidence interval for the mean gain in the AI-access condition.
38. Construct a 95% confidence interval for the difference in mean gains, `mu_AI - mu_standard`, using Table B.
39. Interpret the interval from Question 38 in context.
40. Test whether the AI-access condition produced a greater mean gain than the standard-resource condition.
41. Explain why the randomized design matters when interpreting the difference in mean gains.
42. Suppose a critic says, "Students in the AI-access group were already stronger." Use Table B to respond statistically.

### Unit 8: Inference for Categorical Data: Chi-Square

43. Use Table D to state appropriate hypotheses for a chi-square test.
44. Calculate the expected count for restrictive culture and regular AI use.
45. Verify that the conditions for a chi-square test are met.
46. The chi-square test statistic for Table D is approximately `43.62`. Find the degrees of freedom and approximate p-value category.
47. State a conclusion in context.
48. Identify which cells contribute most to the chi-square statistic and explain what that means in context.

### Unit 9: Inference for Quantitative Data: Slopes

49. State hypotheses for testing whether average daily AI-tutor minutes are linearly associated with gain score.
50. Use Table E to calculate the test statistic for the slope.
51. Find the degrees of freedom.
52. State a conclusion in context.
53. Construct a 95% confidence interval for the slope.
54. Interpret the interval in context.
55. Explain why regression evidence alone is weaker causal evidence than the randomized comparison in Table B.

## Final Synthesis

56. A school administrator says, "The AP-style scores prove AI-supported instruction works." Explain why that statement is too strong.
57. A teacher says, "The AP-style scores prove AI-supported instruction fails whenever students do not use it correctly." Explain why that statement is also too strong.
58. Distinguish between the **intent-to-treat effect** of AI access and the **on-treatment association** for students who actually used AI regularly.
59. Write a statistically careful conclusion about what the full dataset does and does not show.
60. Propose a better follow-up study that could distinguish AI-tutor effects from student motivation, compliance, teacher culture, and phone-policy effects.

## Teacher Notes / Answer Key

### Worked Answer Key

1. Condition, school culture, and passed exam are categorical. AI minutes and gain score are quantitative.
2. A dotplot, histogram, or boxplot is appropriate. The distribution is right-skewed with high values at 75 and 95 minutes. A typical value is around 25 to 30 minutes. The data range from 0 to 95 minutes.
3. Median `27.5`, Q1 `11`, Q3 `47.5`, IQR `36.5`, range `95`.
4. Lower fence `11 - 1.5(36.5) = -43.75`; upper fence `47.5 + 1.5(36.5) = 102.25`. The value 95 is not an outlier by the `1.5 * IQR` rule.
5. The large high-end values create a right tail, and the mean is pulled toward that tail.
6. Restrictive regular-use rate: `21/120 = 0.175`. Open-culture regular-use rate: `66/120 = 0.55`.
7. Yes. Regular use is much higher in open AI-tutor culture, while no use is much higher in restrictive culture: `60/120 = 0.50` versus `20/120 = 0.167`.
8. For each additional AI-tutor minute per day, predicted gain increases by `0.085` points, on average.
9. There is a moderately strong positive linear association between AI-tutor minutes and gain score.
10. `r^2 = 0.62^2 = 0.3844`. About 38.4% of variation in gain score is explained by the linear relationship with AI-tutor minutes.
11. `6.2 + 0.085(40) = 9.6` points.
12. 180 minutes is likely outside the observed range, so this is extrapolation. The linear pattern may not continue that far.
13. The experimental units are AP Statistics students. The treatments are AI access and standard resources. Response variables include posttest score, gain score, pass status, and engagement.
14. Random assignment reduces systematic differences between groups, making the groups more comparable except for the assigned condition.
15. Blocking by school controls for school-level differences such as teacher culture, phone policy, scheduling, prior preparation, and local norms.
16. Yes, the randomized comparison can support a cause-and-effect conclusion about being assigned AI access, assuming the study was carried out properly.
17. No, not by itself. Actual use was not randomly assigned; it may be confounded with motivation, prior skill, family support, teacher encouragement, or school culture.
18. Students may overreport use to look diligent, underreport use if they fear punishment, or misremember their actual minutes.
19. Noncompliance means the assigned treatment and the received treatment differ. The assigned-group estimate can understate, distort, or complicate the effect of actually using the tool.
20. `87/240 = 0.3625`.
21. `120/240 = 0.5`.
22. `66/120 = 0.55`.
23. Not independent because `P(regular) = 0.3625`, but `P(regular | open) = 0.55`.
24. `C(5,2)(0.32)^2(0.68)^3 ≈ 0.322`.
25. `E(X) = np = 5(0.32) = 1.6`; `SD(X) = sqrt(np(1-p)) = sqrt(5)(0.32)(0.68) ≈ 1.04`.
26. `(0.68)^3(0.32) ≈ 0.101`.
27. Mean `0.50`; SD `sqrt(0.5*0.5/120) ≈ 0.0456`; approximately normal because expected successes and failures are both at least 10.
28. Mean `10`; SD `12/sqrt(120) ≈ 1.095`; approximately normal by the CLT because `n = 120` is large.
29. The observed difference is `69/120 - 47/120 = 0.183`. Whether this is surprising depends on the null sampling distribution. Later inference shows it is unlikely under equal pass proportions.
30. Larger sample sizes reduce standard error, so the sampling distribution is narrower. A real difference has a better chance of producing a large test statistic.
31. `p-hat = 69/120 = 0.575`; SE `sqrt(0.575*0.425/120) ≈ 0.0451`; 95% CI is approximately `0.575 ± 1.96(0.0451)`, or `0.486 to 0.664`.
32. Difference `0.575 - 0.392 = 0.183`; SE `sqrt(0.575*0.425/120 + 0.392*0.608/120) ≈ 0.0635`; 95% CI approximately `0.059 to 0.308`.
33. We are 95% confident the AI-access pass proportion is about 5.9 to 30.8 percentage points higher than the standard-resource pass proportion.
34. `H0: p_AI = p_standard`; `Ha: p_AI > p_standard`. Pooled proportion `116/240 = 0.483`. SE `sqrt(0.483*0.517*(1/120 + 1/120)) ≈ 0.0645`. `z ≈ 2.84`; p-value about `0.0023`; reject `H0`.
35. If true pass proportions were equal, the probability of getting a difference at least this large in favor of AI access by random chance is about 0.0023.
36. Type I: concluding AI access improves pass rate when it does not. Type II: failing to detect a real improvement from AI access.
37. `18.6 ± 1.98(12.4/sqrt(120))`, approximately `16.36 to 20.84`.
38. Difference `8.8`; SE `sqrt(12.4^2/120 + 11.7^2/120) ≈ 1.56`; 95% CI approximately `5.72 to 11.88`.
39. We are 95% confident AI access increases mean gain by about 5.7 to 11.9 points compared with standard resources.
40. `H0: mu_AI = mu_standard`; `Ha: mu_AI > mu_standard`. `t ≈ 8.8/1.56 = 5.65`; p-value is very small; reject `H0`.
41. Randomized design makes it more reasonable to attribute the difference in mean gains to assigned AI access rather than preexisting group differences.
42. The pretest means are similar: `48.2` versus `48.9`, so the data do not support the claim that the AI-access group started stronger on average.
43. `H0`: school culture and AI-use category are independent. `Ha`: school culture and AI-use category are associated.
44. Expected count for restrictive culture and regular AI use: `120*87/240 = 43.5`.
45. Expected counts are `43.5`, `36.5`, and `40` in each row, all at least 5. The data must also come from an appropriate random or well-designed study.
46. Degrees of freedom `(2-1)(3-1) = 2`. With `X^2 ≈ 43.62`, p-value is less than `0.001`.
47. Reject independence. There is strong evidence of an association between school culture and AI-use category.
48. The regular-use and no-use cells contribute most. Restrictive culture has far fewer regular users and far more nonusers than expected; open culture has far more regular users and far fewer nonusers than expected.
49. `H0: beta = 0`; `Ha: beta > 0` if testing for positive association, or `Ha: beta != 0` if testing for any linear association.
50. `t = 0.085/0.013 ≈ 6.54`.
51. `df = n - 2 = 78`.
52. Reject `H0`; there is strong evidence of a positive linear association between AI-tutor minutes and gain score.
53. Using about `t* = 1.99`, CI is `0.085 ± 1.99(0.013)`, or about `0.059 to 0.111`.
54. Each additional AI-tutor minute per day is associated with an average gain increase of about `0.059` to `0.111` points.
55. Regression here uses actual minutes, which were not randomly assigned. Motivation and other variables could confound the relationship.
56. It is too strong because the study directly supports a causal claim about assigned access, not a universal claim that AI-supported instruction always works. Implementation, student use, and assessment conditions still matter.
57. It is too strong because misuse or nonuse of a tool does not prove the tool is ineffective for students who use it as intended. Noncompliance contaminates the outcome.
58. The intent-to-treat effect compares assigned AI access with assigned standard resources. The on-treatment association compares students by what they actually did, such as regular AI use, but that comparison is more vulnerable to self-selection.
59. A careful conclusion: in this synthetic study, randomized AI access is associated with higher mean gains and pass rates, and actual AI use is positively associated with gain. However, actual use is confounded with student motivation and school culture, so the cleanest causal conclusion is about access under the study design.
60. A stronger follow-up study would randomize schools or classes to clearly defined phone/AI policies, track actual AI use with logs, require common in-class no-AI assessments, block by school and teacher, measure prior achievement and motivation, and compare both intent-to-treat and per-protocol results.

### Final Synthesis Guidance

A strong final answer should say:

- The randomized evidence supports a causal claim about **AI access**, not necessarily pure actual AI use.
- The actual-use evidence is stronger as an association than as a causal claim because of self-selection.
- School culture is associated with usage, so local anti-AI or pro-AI norms can contaminate interpretation.
- AP-style outcomes alone are insufficient if student effort, buy-in, or noncompliance differs across groups.
- The cleanest conclusion is that AI access, paired with independent demonstration requirements, appears to improve performance in this synthetic study, but further randomized work should separate access, actual use, student motivation, teacher implementation, and school culture.
