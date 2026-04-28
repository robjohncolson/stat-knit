# Investigative Task: Evaluating an AI-Tutor Pedagogy

A high school AP Statistics teacher in Massachusetts implemented an AI-tutor-supplemented curriculum during the 2024–25 school year. The class had **n = 22** students. At year's end, **all 22 scored a 1** on the AP exam. The national 1-rate that year was **17%**. The teacher reports that 18 of the 22 students "boycotted" the exam (left it largely blank as protest); the remaining 4 attempted it.

Separately, a randomized controlled trial published in *Scientific Reports* (Kestin et al., 2025, **N = 194** undergraduates, randomized crossover) compared an AI tutor to active-learning classroom instruction on identical content. Reported result: AI-tutor arm post-test mean ≈ **4.5**, traditional arm ≈ **3.5**, pooled SD ≈ **1.0**, **p < 10⁻⁸**.

The teacher's father, citing the all-1s outcome, argues "the data shows your method failed."

---

## (a) Sampling and external validity *(Unit 3)*

The teacher's class is **not** a random sample from any larger population. Identify (i) the population the local result can validly describe and (ii) the population the RCT can validly describe. Explain why averaging the two as if equally weighted commits a **selection bias** error.

> *Expected:* Local sample = volunteer convenience sample, blue-union-MA, single classroom, single teacher, n = 22 — describes only itself. RCT = randomized within a defined frame (Harvard undergrads in physics) — supports causal inference within that frame and provides reasonable generalization to similar learners. The local sample is non-random and confounded with political/cultural variables; it cannot be pooled as evidence against the RCT.

---

## (b) One-proportion z-test on the local outcome *(Unit 6)*

Test $H_0: p = 0.17$ vs. $H_a: p > 0.17$ where $p$ = probability a student in this class scores a 1.

$$\hat{p} = 22/22 = 1.00, \quad SE_0 = \sqrt{\frac{0.17 \cdot 0.83}{22}} \approx 0.080$$

$$z = \frac{1.00 - 0.17}{0.080} \approx 10.4, \quad p\text{-value} \approx 0$$

**Reject $H_0$.** The 1-rate is wildly higher than national. Then immediately explain why this rejection does *not* support the father's causal claim — go to (c).

---

## (c) Intent-to-treat vs. per-protocol; identifying the estimand *(Unit 3 + Unit 6 interpretation)*

Of 22 students, 18 deliberately did not attempt the exam. Define:

- **Intent-to-treat (ITT) estimand:** mean exam score for *all* assigned students. Includes non-compliers.
- **Per-protocol (PP) estimand:** mean exam score for students who *actually engaged* with both the instruction and the assessment.

The all-1s figure is an ITT measure with **~82% non-compliance**. Argue that the ITT estimate here measures **student political compliance with the assessment**, *not* the causal effect of AI-tutor instruction on statistical reasoning skill. Analogy: a drug RCT in which 82% of the treatment arm refuses to swallow the pill cannot be used to claim the drug is ineffective.

**The relevant on-treatment data** are: in-class Blooket performance, FRQ-style work submitted under observation, verbal defenses of reasoning. State that the father's argument confuses ITT non-compliance with causal failure.

---

## (d) Two-sample inference on the RCT *(Unit 7)*

Using the published numbers (means 4.5 vs. 3.5, pooled SD ≈ 1.0, $n_1 = n_2 = 97$):

$$SE = 1.0 \cdot \sqrt{\tfrac{1}{97} + \tfrac{1}{97}} \approx 0.144$$

$$t = \frac{4.5 - 3.5}{0.144} \approx 6.96, \quad df \approx 192, \quad p < 10^{-8}$$

**95% CI for the mean difference:** $1.0 \pm 1.97(0.144) \approx (0.72,\ 1.28)$.

**Cohen's d ≈ 1.0** (very large effect). Conclude: at standard $\alpha$, we reject $H_0: \mu_{AI} = \mu_{trad}$. Causal direction is licensed because randomization controls for confounders by design.

---

## (e) Power and the "we don't have the data yet" claim *(Unit 6)*

Compute approximate power of the RCT to detect $d = 1.0$ at $\alpha = 0.05$ with $n_1 = n_2 = 97$:

$$\text{power} \approx P(Z > 1.96 - 1.0\sqrt{97/2}) = P(Z > 1.96 - 6.96) \approx 1.000$$

Power is essentially 1. The claim "we don't have the data" is equivalent to either (i) being unaware of high-powered evidence that already exists, or (ii) treating $\alpha$ thresholds asymmetrically (require evidence for AI, accept tradition by default). Both are inferential errors, not neutral positions.

---

## (f) Confounding in the local sample *(Unit 3)*

List confounders in the local AP-score outcome that are **not** present in the RCT:

- Political identification of students with anti-AI in-group
- Teacher reputation effect (admin/peer signaling about the teacher)
- Self-selection into the class
- Single-teacher / single-school effect (no replication)
- Knowledge that the score itself was being used as social currency

The RCT randomization breaks the link between treatment and these variables; the local "study" does not. Local outcome is therefore not a valid test of the treatment effect even before the non-compliance issue.

---

## (g) Chi-square test for differential response *(Unit 8)*

Suppose the teacher records the following 2×2 table from the *next* cohort (n = 30), classifying students by prior engagement and post-tutor performance:

|                     | Improved ≥ 1 letter grade | Did not improve | Total |
|---------------------|---------------------------|-----------------|-------|
| Previously disengaged | 9                         | 3               | 12    |
| Previously engaged    | 4                         | 14              | 18    |
| **Total**             | **13**                    | **17**          | **30** |

Test $H_0$: improvement is independent of prior-engagement status.

Expected counts: e.g. $E_{11} = 12 \cdot 13 / 30 = 5.2$. Computed $\chi^2 \approx 8.6$, df = 1, $p \approx 0.003$.

**Reject independence.** AI-tutor benefit is **not uniform**: marginal gain is concentrated in students the prior system underserved — exactly the pattern the tutoring literature predicts (Bloom's 2-sigma, with largest gains for students far from the group-paced mean).

---

## (h) Linear regression with interaction *(Unit 2 + Unit 9 interpretation)*

Fit:

$$\widehat{\text{Score}} = \beta_0 + \beta_1(\text{AI hours}) + \beta_2(\text{prior engagement}) + \beta_3(\text{AI hours} \times \text{prior engagement})$$

Interpret a finding where $\hat\beta_1 > 0$, $\hat\beta_3 < 0$: AI hours raise score on average, but the *marginal* benefit shrinks for already-engaged students. This formalizes the qualitative claim: **AI as tutor disproportionately helps students with the most slack between actual and potential performance**, rather than uniformly boosting everyone.

---

## (i) Synthesis: stating the defensible conclusion *(skills 1.E, 4.B)*

Write a paragraph, in AP-rubric style, that:

1. Identifies the **causal question** ("Does AI-tutor instruction increase statistical reasoning skill relative to traditional instruction?").
2. Identifies **which evidence is admissible** for that question (RCT — yes; local ITT outcome under boycott — no).
3. States the **direction and magnitude** of the admissible evidence ($d \approx 1.0$, $p < 10^{-8}$).
4. Identifies the **failure mode** of the local "evidence" (selection bias, confounding, near-total non-compliance).
5. Concludes that the empirical claim — *"AI-tutor instruction produces faster skill acquisition than traditional instruction, with the largest marginal gains for previously underserved students"* — is **supported by the data available as of 2026**, and that arguments to the contrary based on the local outcome rely on inferential errors a Unit 3/Unit 6 student is expected to identify.

---

## Skills covered

| Part | AP Stats skill |
|------|----------------|
| (a)  | Sampling, external validity, generalizability |
| (b)  | One-proportion z-test |
| (c)  | Estimand definition, ITT vs PP, interpretation under non-compliance |
| (d)  | Two-sample t-inference, CI, effect size |
| (e)  | Power, Type II error, asymmetric evidentiary standards |
| (f)  | Confounding, randomization as causal license |
| (g)  | Chi-square independence, differential treatment effect |
| (h)  | Regression, interaction terms, marginal effect interpretation |
| (i)  | Scope of inference, synthesis, communication |

---

**Pedagogical point:** a student who can correctly answer (a)–(i) can reconstruct the argument from first principles, without needing to share the author's priors. The defense is not "trust me" — it is "here is the test, and here is what the rubric says."
