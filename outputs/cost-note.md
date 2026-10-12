# Pre-modelling cost note — Olist late-delivery warning
**Project:** LARIS P1 — Olist Brazilian E-Commerce  
**Written:** 12 October 2026, before modelling  
**Decision to evaluate:** At the order level, should the seller proactively contact the customer and check fulfillment when an order is predicted to arrive after its promised delivery date?
## Prediction and decision
Predict whether an order will be delivered after its estimated delivery date, using only information available at the chosen prediction time. A **positive** prediction means “likely late” and triggers one low-cost intervention: a proactive customer update and fulfillment check. The target date and prediction time must be fixed before modelling; information recorded after the prediction time must not be used as a predictor. This is an operational hypothesis to evaluate, not a claim that the dataset contains all information needed to intervene.
## Cost assigned to each error
| Prediction error | What happens | Illustrative cost per order |
|---|---|---:|
| **False negative** — predicted on time, actually late | The warning is missed, so the assumed proactive update/check is not made. Allow **R$25** for avoidable service handling and goodwill effort after a late delivery. | **R$25** |
| **False positive** — predicted late, actually on time | The unnecessary update/check is made. Allow **R$5** for staff time and contact overhead. | **R$5** |
**Assumptions, not observed Olist costs:** These round values are placeholders for a small seller, not measured Brazilian market rates or costs supplied by Olist. The R$25 allowance assumes a missed warning causes roughly 15 minutes of support work at R$60/hour (R$15) plus R$10 of expected goodwill handling. The R$5 allowance assumes about five minutes of proactive handling at R$60/hour. The dataset does not establish that an intervention prevents lateness or that these costs occur; the amounts represent decision costs to test. Replace them with seller, course, or documented evidence if available, and show sensitivity to alternative values.
## How the costs will be used
For each candidate model/decision threshold, calculate **R$25 × false negatives + R$5 × false positives**, per evaluated order (and report the evaluation-set size). Compare this total alongside the full required metric panel. Choose a threshold/model using this predeclared cost rule only after evaluation; do not revise the costs to favor a result. This simplified calculation excludes true-positive and true-negative benefits, intervention effectiveness, and all other operating costs.
**Scope note:** The course rubric describes a fixed team of 3–4. This project is being prepared as an individual submission; confirm with the instructor that individual submission is permitted before proceeding.
