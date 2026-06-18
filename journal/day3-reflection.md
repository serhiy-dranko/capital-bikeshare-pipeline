1. What surprised you most in the data? Not "I found that members ride shorter" — go deeper. Was the magnitude of the difference surprising? Did any number contradict your intuition before you ran the analysis?

   That how much analysis we can build based only on one month data with only 13 columns. We only have basic information about the duration of trips. Surprising that during analysis of Joint probability table we can calculate that Electric bike choice and rider type are not independent. And pridict customer future behaviour.

2. What was the hardest part of building this pipeline? Be specific. Not "it was hard" — which stage? Which formula? What did you have to do to get past it?

  The harders one was understand how this work  =TTEST('06.1_SAMPLING'!D2:D1501,'06.1_SAMPLING'!D1502:D3001,2,3) and all tasks conected to Probability calculation. When I went trought it I've learnt how Sampling and A-B testing work on real life and how companies work with this data in real life.

3. What does your A/B test result actually mean for Capital Bikeshare? Pretend you're explaining it to the Head of Operations. What should they do (or not do) based on your p-value and Cohen's d?

   The A/B test shows that Casual riders take significantly longer trips than Members, with an average duration that is 74% higher (21.5 vs. 12.4 minutes). The extremely small p-value (< 0.001) indicates that this difference is very unlikely to be due to random chance. Cohen’s d of 0.51 suggests a moderate and practically meaningful effect size, meaning the behavioral difference is substantial enough to matter operationally. Capital Bikeshare should treat Casual and Member riders as distinct customer segments when planning operations, forecasting demand, and designing marketing campaigns, but should not assume that membership itself causes shorter trips.

4. If you had one more day and access to 12 months of data instead of one month, what would you investigate? This question is about thinking like a data analyst — what questions does your current analysis leave unanswered?

   The main question is Do we have this paterns of Customer behavior whole year of irt depend from time of the year.
