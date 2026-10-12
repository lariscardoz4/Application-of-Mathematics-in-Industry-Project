# Pre-modelling cost note — P1 delivery promise
**Project:** LARIS P1 — The Delivery Promise (Olist Brazilian E-Commerce)  
**Written:** 12 October 2026, before modelling  
**Decision:** At checkout, what delivery duration should the marketplace promise to the buyer? The estimate is made when the buyer clicks pay. Operations owns the estimate; the checkout page communicates it.
## Target and direction of error
Predict the number of hours from purchase to customer delivery, using only information available at checkout. Let the error be **predicted hours minus actual hours**.
| Error | Meaning for the buyer | Assumed cost |
|---|---|---:|
| **Underestimate** (prediction is too few hours) | The parcel arrives later than promised. The brief links late delivery with poor reviews and seller loss. | **R$10 per order per hour underestimated** |
| **Overestimate** (prediction is too many hours) | The parcel arrives earlier than promised. An unnecessarily late promise may discourage a purchase. | **R$2 per order per hour overestimated** |
## Assumptions and decision rule
The brief provides no measured cost data. These are **illustrative planning assumptions**, not Olist findings or verified marketplace costs. I assign underestimation five times the cost of overestimation because the brief describes poor reviews and seller departure as consequences of late delivery, while the cost of a conservative (too-late) promise is a possible loss of conversion. The round amounts make that 5:1 priority explicit; they do not claim that one hour has been proven to cost these exact amounts. Replace them with marketplace evidence if available and test whether the conclusion changes under other cost ratios.
For an order, estimated cost is **R$10 × hours underestimated + R$2 × hours overestimated**. Sum this across the evaluation orders and divide by their count to report mean cost per order. For example, underestimating by 3 hours costs R$30 under this assumption; overestimating by 3 hours costs R$6. For the regression metric panel, use pinball loss at quantile **10 / (10 + 2) = 0.833**, which reflects these asymmetric hourly penalties, and report the ordinary error metrics alongside it.
**Scope:** This note sets the pre-modelling cost rule for P1's checkout delivery-time estimate. P1 also asks about bad-review risk and choosing 50 sellers for support calls; those decisions have different error costs and must be described separately before modelling them. Credit Olist and the dataset's CC BY-NC-SA 4.0 licence in the project memo and repository.
