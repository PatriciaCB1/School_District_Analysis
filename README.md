# School_District_Analysis

## Overview of the school district analysis: 
  
Originally we had undertaken this analysis to deep-dive into school district data and to report on any interesting findings in terms of co-relations between certain school attributes and their impact on outcomes.  We combined data at the school level from the school board with student level data from the schools.  Throught our process we cleaned the data, merged the school and student data files and organized the data into various dataframes to analyze various attributes such as:  School Type, number of students, reading and math outcomes and overall pass counts and rates based on students achieving >= 70% in both math and reading.  We further explored the impact number of students, type and budget within a school had on the outcomes.

On completion of our analysis, we were advised the students_complete.csv file showed some evidence of academic dishonesty; specifically, reading and math grades for Thomas High School ninth graders appeared to have been altered. Although the school board does not know the full extent of the academic dishonesty, they wanted to uphold state-testing standards. As a result we were asked to replace the math and reading scores for Thomas High School with NaNs while keeping the rest of the data intact. It has further been requested that we repeat the school district analysis and write summary report to describe how these changes affected the overall analysis.

Resources:
  ## Resources
  - Data Sources:  schools_complete.csv, students_complete.csv, clean_students.csv
  - Software:  Anaconda 4.9.2, Jupyter Notebook 6.0.3 , Python 3.7.6 
  - Using:  Pandas, NumPy


## Results: 

### How is the district summary affected?
 - The number of total students reduced from 39,170 to 38,709 - due to the 461 student records removed for Thomas High School.
 - While overall metrics were impacted, the impact was minimal - no changes >= 1% so not significant enough to report.
 
 Original District Summary
 
![Original_District_Summary1](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/Original_District_Summary1.png)

Revised District Summary
![Revised_District_Summary](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/Revised_District%20Summary.png)

### How is the school summary affected?
- Not surprisingly, the only numbers in the school summary that were impacted were the numbers for Thomas High School.
- None of the other schools were impacted by our edits to the data => this means that our updates / edits were successful and the code executed properly.
- Import to note, in our school summary we removed all 9th grade scores for THS from the counts and % passed for math, reading and overall but we did not remove the student count of 461 from our Total Students nor did we revise our calculations for Average Math Score or Average Reading Score.  
- The following significant differences were noted for Thomas High School:
  - % Passing Math: increased from 66.9% to 93.2% 
  - % Passing Reading: increased from 69.7% to 97.0%
  - % Overall Passing: increased from 65.1% to 90.6% 
  
  This was the result of only taking into consideration the passing percentages for grades 10-12.  Including the 9th grade scores had negatively impacted these measures, likely due to NaN counting as zero and the new student count totals were not effectively reflected. Conversely, by removing the 9th grade scores we are likely artificially inflating our passing %s.  I would suggest assigning the appropriate grades to the grade 9 students (even if grade is failing due to dishonest academic activity) so we are working with complete data and reporting more accurately.  This did not impact the schools overall "ranking" so may not have a material impact.  Would like to explore the data both ways to be confident though.
  
 School Summary
![School_Summary](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/School_Summary_DF.png)

### How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
- Replacing the ninth graders' math and reading scores actually had a positive effect on Thomas High School's performance relative to the other schools.  Although, in following directions to the letter, our actions removed the 9th grade Thomas High School Students from the District Summary but not from the school summary which meant that the overall number of students changed in the district summary but not in the student summary (i.e. we removed their grades for reading and math but left them in the student count as we should have).
- Thomas High School saw a small decline in % Overall Passing but Thomas High School retained its position as #2 in Top Schools.

THS Performance Relative to Other Schools
![THS_Performance_Relative_To_Other_Schools](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/THS_Performance_Relative_To_Other_Schools.png)


### Replacing the grades for the 9th grade students for reading and math with nAn had the following impacts:
  - Math and reading scores by grade:  The math and reading scores by grade were not impacted, except for THS 9th grade scores appearing as nan, confirming our code and removal of those grades had the desired impact. 
  
  Math Scores By Grade
  
  
  ![Math_scores_by_grade](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/Math_Scores_By%20Grade.png) 
  
  Reading Scores By Grade
  
  
  ![Reading_scores_by_grade](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/Reading_Scores_By_Grade.png)
  
  
  - Scores by school spending were not at all impacted.  As per our previous analysis there almost appears to be a negative relationship between school spending and outcomes though it is likely this driven by school type.  For district schools, higher spend did not lead to better outcomes.  
  
  Scores by School Spending
  
  ![School_Spending](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/School_Spending.png)
  
  - Scores by school size were not impacted because we did not remove the actual students just their grades.  The omission of data did not lower scores in a meaningful way.
  
  Scores by School Size
  
  ![School_Size](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/School_Size.png) 
  
  - Scores by school type were not at all impacted.  As per our initial analysis, Charter schools significantly out perform District (% Overall Pass Charter 90% to % Overall Pass District 54%).  Even with lower spend per student (normalizing for the fact that District Schools typically have higher student counts within our data) Charter schools still outperform district schools.
  
  Performance Detailing Type & Spend
  
  ![Performance detailing Type Spend](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/School_Summary1.png)
  
  Scores by School Type
  ![School_Type](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/School_Type.png)
  
  Top 5 performing schools are all Charter Schools 
  ![Top Schools](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/Highest_Performing_Schools.png)
  
 Bottom 5 performing schools are all District Schools
 
 ![Bottom_Schools](https://github.com/PatriciaCB1/School_District_Analysis/blob/main/Lowest_Performing_Schools.png)

## Summary of Changes after removing all math and reading schools for 9th graders at Thomas High School

  - All 9th grade scores for Thomas High School have been removed and replaced with NaN.
  - Totals were revised for reading, math and overall for Thomas High School so only grades 10-12 are reflected in the final percentages.  Total Students still reflects the total actual number of students for the school.
  - This has created significant increase in the percentage pass scores for Thomas high school for reading, math and overall.  
  - District Scores were not significantly impacted (though student total decreased)
  - Scores by Size, Spend and Type were not impacted, nor was Thomas High School's position as 2nd top school.
  
  In an effort to be prudent it would be recommended to assign scores to the impacted students for reading and math and to reassess the data once these have been added to our data set in order to confirm overall findings.
  
 School type appears to have the largest impact on positive outcome - with Charter schools significantly outperforming District Schools.

