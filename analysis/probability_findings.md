# Probability Analysis — Rider and Bike Type

## Empirical Probabilities

| Event | Probability |
|-------|------------|
| P(casual) | 25.30% |
| P(member) | 74.70% |
| P(electric bike) | 35.05% |
| P(classic bike) | 63.95% |
| P(docked bike) | 1.00%  |
| P(duration > 30 min) | 9.64% |
| P(duration < 5 min)  | 18.00% |

## Independence Test: Is electric bike preference independent of rider type?

P(electric | member) = 36.92% 
P(electric | casual) = 29.53%
P(electric overall) = 35.05%

Finding: Electric bike choice and rider type are dependent: members select electric bikes 36.92% vs 29.53% for casual riders. 
7.4% gap that exceeds what random variation would produce if the two variables were unrelated. 
In other words, knowing someone's rider type meaningfully shifts the probability of which bike they'll choose.

## Business Implication

Since members disproportionately favour electric bikes and generate 74.7% of all rides, electric fleet expansion should be prioritised 
at high-membership stations. Conversely, docked bikes serve exclusively casual riders, so docked infrastructure investment does nothing 
for membership growth and should be evaluated as a separate tool.
