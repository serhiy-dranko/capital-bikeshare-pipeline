# A/B Test: Classic vs Electric Bike Trip Duration

## Hypothesis

H₀: There is no difference in mean trip duration between classic and electric bike riders.  
H₁: Electric bike riders have different mean trip durations than classic bike riders.  
Significance level: α = 0.05

## Results

| Metric | Classic Bike | Electric Bike |
|--------|-------------|---------------|
| n | 1,500 | 1,500 |
| Mean duration (min) | 12.37 | 21.52 |
| Std deviation (min) | 10.57 | 22.85 |

p-value: 0.00000 
Cohen's d: 0.51 : Large effect  
Verdict: Reject H₀

## Plain English Interpretation

The p-value is effectively zero if members and casual riders truly rode for the same duration on average. 
The 9.16 min gap between the groups would almost never appear by chance. We can confidently reject the null hypothesis: the difference is real. 
Cohen's d of 0.51 puts this in "50-50" territory, meaning the effect is genuine but the two groups still overlap substantially. 
This is a signal, not a clean separation between every individual ride.

## Confound Check

Bike type does not explain the gap. Across both classic and electric bikes, casual riders consistently ride longer than members: 
 - classic 22.28  min vs 12.31 min  
 - electric: 17.70  min vs 12.46 min 
The member_casual split persists regardless of which bike is used. Which confirms that rider behaviour are not equipment choice. Is just driving the duration difference.

## Recommendation

The 12.37% of casual riders already taking trips 10-15 minutes are behaviourally indistinguishable from members and represent the target.

Pricing policy between the two commute peaks (roughly 09:00 to 16:00). When casual ridership is proportionally elevated and member usage dips are should be reviewed to capture aditional revenue without changing the member base.
