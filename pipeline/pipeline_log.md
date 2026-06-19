# Pipeline Log - Capital Bikeshare Analytics Pipeline

This log records every significant decision made during pipeline construction: 
data quality issues found, cleaning rules applied, design choices and their rationale.

Built in Google Sheets. September 2023 Capital Bikeshare data.

## Day 1 

## Stage 1 Raw ingestion

  Date:6/12/2026 09:47:34
  
  Source: capitalbikeshare.com/system-data
  
  File: 202309-capitalbikeshare-tripdata.csv
  
  Row count (incl. header): 450091
  
  Columns: 13
  
  Schema documentation:
  
  - Quality issue 1: Trailing empty rows. 2 empty rows at the end of the file (import artifact) affect all columns
  - Quality issue 2: Gaps in the stations id's and name's. The reason is dockless trips are not assigned to a station; this is expected behavior.
  - Quality issue 3: Gaps in end_lat / end_lng 667 records, cause unknown.
  - Decision: we will handle these issues in Stage 2
    
  Problem: Google Sheets limitations do NOT allow us to copy all 450091 rows in tab 02_CLEAN while limiting rows for the entire file to 1M rows. The solution was to sample data from 100,000 rows for sampling and further work. Advice: Switch to Excel, this program limits each sheet to 1.3M rows. Not the entire document.


## Stage 2 Cleaning complete
  
  Valid rows: 97044
  
  Invalid rows: 2955
  
  % pass rate: 97.04
  
  Exclusion reasons documented: duration out of range, blank fields"

## Stage 3 Aggregation complete

  Sections built: Overall Metrics, Duration by Segment, Hourly Distribution, Duration Buckets
  
  All formulas reference 02_CLEAN with is_valid=TRUE filter
  
  Downstream tabs (04, 05, 07, 08) should read from this tab only"

## Stage 4 Statistics layer complete

  Key finding 1: Highest bucket 5-10 min 29584 rides (30.5 %)
  
  Key finding 2: Coefficient of variation is 106.92 %
  
  Distribution shape: right-skewed
  
  Mean vs median gap: 4.51 minutes — implies this significantly inflate the average duration of a ride."

## Stage 5 Probability layer complete

Independence finding: electric bike choice is dependent of rider type near 7% difference

  P(electric|member) = 36.92%  vs  P(electric|casual) = 29.53%  vs  P(electric overall) = 35.05%
  
  Business implication: Classic bikes dominate both segments, but especially among members (47.12%). Casual riders are the only users of docked 
  bikes, although they also rarely use them (1%). For planning: docked bikes serve exclusively the casual segment. If the goal is to increase 
  membership, docked bikes will not help conversion."

## Stage 6 Experiment sample prepared

  Classic bike rows: 1,500 (randomly selected from valid rows)
  
  Electric bike rows: 1,500 (randomly selected from valid rows)
  
  Selection method: RAND() frozen, sort ascending, take first 1500
  
  Columns included: ride_id, rideable_type, member_casual, duration_min, hour_of_day, is_weekend"
  
## Stage 7 A/B test complete

 Test: Classic vs Electric bike trip duration
  
  n per group: 1,500
  
  p-value: 5.67%
  
  Cohen's d: 0.07
  
  Verdict:The difference is statistically significant but If there were truly no difference between trip durations we would see a difference this larger by 
  chance 5.67%.Cohen's d Large Meaning: Real but minor.
  
  Confound check: rider type does not explain the difference
  

Test: Member vs Casual bike trip duration

  n per group: 1,500
  
  p-value: 0.00%
  
  Cohen's d: 0.51
  
  Verdict:The difference is statistically significant but If there were truly no difference between trip durations we , we would see a difference less 
  than 0.01 % of the .Cohen's d Large Meaning: Large Not conclusive
  
  Confound check: customer type explain the difference
  
## Stage 7 Dashboard complete

  Sections: Pipeline Health, Key Metrics, Experiment Results
  
  All values reference upstream tabs — no independent computations
  
  Charts: duration histogram (from 04_STATS), A/B test histogram (from 07_AB_TEST)

## Day 2 

## Stage 1 Narrative arc chosen: Arc A — The Rider Gap
  
  Story headline: ""Members and casual riders use the bikeshare system in fundamentally different ways.""
  
  Reason for choice: When I did A/B testing and looked at the Confound check table and saw the difference between customer types, I want to look 
  into it in more detail.

## Stage 2 Visual storytelling complete

  Arc chosen: Arc A — The Rider Gap
  Charts built: 
    - Capital Bikeshare - From Raw Data to A/B Test Decision
    - Capital Bikeshare pipeline
    - Casual riders take trips twice as long as members
    - Bikeshare becomes a commuter tool after 8:00 - then goes quiet until 17:00
    - The gap between Members and Casual riders narrows as trip duration increases.
    - Same Bike, Different Purpose Members Ride 74% Shorter.
    - Classic bikes show high probability regardless of customer type
      
  Insight cards created: 7
  
  Exported to: Day5_Presentation/
    
## Day 3

## Stage 1 GitHub repo created

  Repo URL: https://github.com/serhiy-dranko/capital-bikeshare-pipeline

## Stage 2 GitHub documentation complete

  Repo URL: https://github.com/serhiy-dranko/capital-bikeshare-pipeline
  
  README: complete (Key Findings filled with real numbers)
  
  Analysis files: stats_summary.md · probability_findings.md · ab_test_results.md
  
  Assets uploaded: 9 charts · 8 insight cards
  
  Journal entry: journal/day3-reflection.md
  
  Repo checklist: all items cleared

  Folder structure: data/, pipeline/, charts/, insight_cards/, analysis/, journal/
  
  Visibility: Public

  ## Day 4 

## Portfolio complete

  Portfolio URL: https://serhiy-dranko-portfolio.carrd.co
  
  GitHub repo URL: https://github.com/serhiy-dranko/capital-bikeshare-pipeline
  
  Sections: header · Capital Bikeshare case study · visuals · next project · links
  
  Next project idea: To analyze which smartphone features have the strongest relationship with price and summarize the results
  
  Day 5 links: saved and tested

   ## Day 5

  ## Visual storytelling update

  Arc chosen: Arc A — The Rider Gap
 
  Charts built: 
  
  - Capital Bikeshare - From Raw Data to A/B Test Decision
  - Capital Bikeshare core question
  - Capital Bikeshare pipeline
  - Capital Bikeshare data quality
  - Casual riders take trips twice as long as members
  - Bikeshare becomes a commuter tool after 8:00 - then goes quiet until 17:00
  - The gap between Members and Casual riders narrows as trip duration increases.
  - Same Bike, Different Purpose Members Ride 74% Shorter.
  - Classic bikes show high probability regardless of customer type
  - GitHub and Portfolio
  - What I learned during the project
  - What I'd Investigate Next
  - END Chart
      
  Insight cards created: 14
  
  Exported to: /insights_cards

  Schema entry: data/schema updated
