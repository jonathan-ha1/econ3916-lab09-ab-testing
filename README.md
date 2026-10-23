# A/B Testing — Designing the Data-Generating Process

## Objective
This lab uses a job training experiment and a mobile game A/B test to show why random assignment matters, how to test whether an effect is real, and how to plan the sample size an experiment needs.

## Methodology
- Loaded the LaLonde NSW job training experiment (445 people: 185 trainees and 260 controls) and computed the experimental ATE as the difference in mean 1978 earnings.
- Simulated an observational comparison group to show selection bias, and split the gap as Observational ATE = True ATE + Selection Bias.
- Ran a permutation test with 9,999 shuffles to check whether the ATE could be due to chance.
- Computed a bootstrap BCa 95% confidence interval for the ATE.
- Ran a power analysis to find the power of the study and the sample size needed to detect three different dollar effects.
- Applied the same difference in means, permutation test, and bootstrap to the Cookie Cats A/B test (90,189 players, gate at level 30 or 40, Day-1 retention).
- Wrote a sample-size function, n_needed(), checked it against the power analysis, and used it to size a rerun of the Cookie Cats test.

## Key Findings
- In the LaLonde experiment, trainees earned $1,794.34 more than controls (permutation p = 0.0046, 95% CI $575.18 to $3,262.37), so the training had a real positive effect.
- The simulated comparison group gave an ATE of $-14,784.45. Without random assignment, the same program looked like it hurt earnings, which shows how much selection bias can distort a result.
- In Cookie Cats, gate_30 had a retention difference of 0.59 pp over gate_40 (p = 0.0752), which is not significant at the 0.05 level.
- A rerun of Cookie Cats would need 111,192 players per group to detect that difference with 80% power.
