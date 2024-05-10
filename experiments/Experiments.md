# Experiments plan:

Plan and log of experiments that require significant computational time (a.e. models retraining.)

| Experiment | Description | Score | Resolution |
|------------|-------------|-------|------------|
| 1_1 | Count hits for each cleanign stage, for each step in stemming pipeline | 0.93665 (beseline) | There are redundant steps in stemming pipeline. Cleaning counts are non-informative  |
| 1_2 | Remove cleaning stage | 0.90399 | Substantial change. Worth checking impact of each component |
| 1_3 | Remove stemming stage (use words as is to build embeddings) | 0.93657 | Impact is insignificant stemming is not effective |
| 1_4 | Perform only one iteration with pseudo-labels | 0.93481 | Degradation is detectable, but not catastrophic |
| 1_5 | Replace the decision thereshold for the values to 0.4: more comments are considered toxic, may mitigate the datasets imbalance | 0.92395 | Degradation, but not severe. interesing to observe increasing of threshold, later to check the performance with smaller change |
| 1_5_1 | Replace the decision thereshold for the values to 0.55: have more confident examples of the toxic comments | 0.94915 {wip: still grows} | Improvement in AUC score, not obvious, as change of the threshold has impact on scoring splits. Note 1_5 also worth checking in baseline conditions |
| 1_6 | Disable both stemming and cleaning: check for interdependance, get the most basic score | ? | |
| 1_2_1 | No cleaning, but punctuation stage | ? | |
| 1_2_2 | No cleaning, but misspelled replacements stage | ? | |
| 1_2_3 | No cleaning, but numbers dropping | ? | |
