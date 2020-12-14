# School_District_Analysis

## Overview of the school district analysis: Explain the purpose of this analysis.
  
Originally we undertook this analysis to deep-dive into school district data and to report on any interesting findings in terms of co-relations between certain school attributes and their impact on outcomes.  We combined data at the school level from the district school board with student level data from the schools.  Throught our process we cleaned the data, merged the school and student data files and organized the data into various dataframes to analyze the various attributes such as:  School Type, number of students, reading and math outcomes and overall pass counts and rates based on based on students achieving >= 70% in both math and reading.  We further explored the impact number of students within a school had on the success of students and also the role whether budget or type potentially inpacted school outcomes.

On completion of our analysis, we were advised the students_complete.csv file showed some evidence of academic dishonesty; specifically, reading and math grades for Thomas High School ninth graders appeared to have been altered. Although the school board does not know the full extent of the academic dishonesty, they want to uphold state-testing standards. As a result we have been asked to replace the math and reading scores for Thomas High School with NaNs while keeping the rest of the data intact. It has further been requested that we repeat the school district analysis and write summary report to describe how these changes affected the overall analysis.

## Results: Using bulleted lists and images of DataFrames as support, address the following questions.

### How is the district summary affected?
 - The number of total students reduced from 39,170 to 38,709 - due to the 461 student records removed for Thomas High School.
 - While overall metrics were impacted, the impact was minimal - no changes >= 1% so not significant enough to report.
 
 Original District Summary
 
![Original_District_Summary](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/Original_District%20Summary.png)

Revised District Summart
![Original_District_Summary](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/Revised_District%20Summary.png)

### How is the school summary affected?
- The only numbers in the school summary that were impacted were the numbers for Thomas high school.
- None of the other schools were impacted by our edits to the data => this means that our updates / edits were successful and the code executed properly.

### How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
- Replacing the ninth graders' math and reading scores actually had a positive effect on Thomas High School's performance relative to the other schools.  Although, in following directions to the letter, our actions removed the 9th grade Thomas High School Students from the District Summary but not from the school summary which meant that the overall number of students changed in the district summary but not in the student summary (i.e. we removed their grades for reading and math but left them in the student count as we should have).
- Thomas High School saw a decline small decline in % Overall Passing but Thomas High School retained its position as #2 in Top Schools. 

### Replacing the grades for the 9th grade students for reading and math with nAn had the following impacts:
  - Math and reading scores by grade:  The math and reading scores by grade 
  - Scores by school spending were not at all impacted 
  - Scores by school size were not impacted because we did not remove the actual students just their grades and the change in overall grades for the size band THS                  sits in was not significantly impacted by the removed grades.
  - Scores by school type were not at all impacted.

##Summary: Summarize four major changes in the updated school district analysis after reading and math scores for the ninth grade at Thomas High School have been replaced with NaNs.

