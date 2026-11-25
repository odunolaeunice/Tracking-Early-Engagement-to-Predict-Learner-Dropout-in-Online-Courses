# Tracking Early Engagement to Predict Learner Dropout in Online Courses

Can engagement and registration data from the first four weeks identify learners at risk of dropping out early enough for a coordinator to step in?

## Overview
This project uses registration and early activity data to flag learners at risk of withdrawing. It produces a simple week-4 risk flag so project coordinators can contact the right learners in time.

## Data
- **Dataset:** Open University Learning Analytics Dataset (OULAD)
- **Size:** 32,593 learner-module records across seven modules
- **Note:** UK higher-education data, used as a proxy for a training programme
- **Dropout definition:** final result of "Withdrawn"

## Approach
Built in Python (Google Colab). The analysis answers five questions:
1. How big is the dropout problem?
2. When do learners leave?
3. Which early signals matter?
4. Can a week-4 risk flag be built?
5. How can results be presented so a coordinator can act?

## Key Findings
- **Baseline:** 31.2% withdrew and 47.2% passed. Dropout ranges from 44.5% (module CCC) to 11.5% (module GGG).
- **Timing:** 26.6% of withdrawals happen before the course starts and 50.0% by the end of week 4.
- **Early signals:** Learners who missed an assessment due by day 28 withdrew at 40.4%, against 17.9% for those who submitted.
- **Risk flag:** Logistic regression using only information available by day 28 reached an AUC of 0.686 (module-only: 0.613). Dropout rises from 10.7% (Low) to 20.3% (Medium) and 35.7% (High).

## Recommendations
- Reach out before the course starts.
- Check at week 4 and contact High-risk learners first.
- Check earlier in fast-exit modules (e.g. BBB, EEE) and test whether contact lowers dropout.

## Limitations
- Proxy dataset; findings show associations, not causes.
- A week-4 flag only reaches learners still registered at that point (about half of withdrawals).
- Some groups are small, and 93 withdrawals have no recorded date.
- The flag is a screening aid, not a verdict on any individual. Learner background is used to monitor equity, not to decide who gets support.

## How to Run
1. Download the dataset from the Open University Learning Analytics Dataset page.
2. Open `notebook.ipynb` in Google Colab.
3. Upload the data files and run all cells.

## Tools
Python, pandas, scikit-learn, matplotlib, Google Colab

## Author
Odunola Eunice Adams, Tech with Eunice
[Contact email / LinkedIn]
