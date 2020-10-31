# Pewlett-Hackard-Analysis
## Overview
The purpose of this analysis is to write a query to create a list of employees reitiring by title, and a list of employees eligible for the mentorship program. By looking at these lists we can determine if there will be enough current mentorship eligible employees to fill all of the positions as people start to retire, or if Pewlett-Hackard will have to hire more employees to fill the positions.

## Results 
The first deliverable shows how many people are up for retirement under each title. I determined likelihood to retire on the employee's birth date. 

![](data/retiring_titles_count.png)

- There are a lot of people that could potentially retire soon, with the highest need being for Senior Engineers. Based off our analysis, 29,414 Senior Engineers are considering retiring soon. 
- The second highest need, not far behind Senior Engineers, is Senior Staff. 28,254 Senior Staff members are likekly to consider retiring soon. 

The second deliverable for my analysis shows a list of all current employees that are eligible for the mentorship program, which is also based on birth date.

![](data/mentorship_eligibility.png)
- There are 1,550 employees in this list
- Clearly, Pewlett-Hackard will likely need to hire many more people to fill these 90,000 positions that may be open soon.
- There are over 29,000 Senior Engineer positions that may need to be filled soon, and only 529 mentorship eligible Senior Engineers at the company.


## Summary 
- **How many roles will need to filled as the 'silver tsunami' begins to make an impact?** My first image shows 90,398 people could retire soon, and only 1,549 current employees are eligible for the mentorship program, meaning over 88,000 roles will need to be filled due to the 'silver tsunami.'
- **Are there enough qualified, retirement ready employees in the departments to mentor the next generation of PH employees?** No, Pewlett-Hackard will have to hire many more employees to fill these positions over time. 

## Additional Queries
An additional query I used was to compare the number of retirees to the number of mentorship eligible employees. 

~~~~
SELECT COUNT(title), title 
FROM mentorship_eligibility
GROUP BY title
ORDER BY COUNT(title) DESC;
~~~~

This made it easy to see how many mentoship eligible employees there were by title. 

Another query I found useful was one that narrowed down the results of the retiring by title table to only current employees. I simply altered the table created for Deliverable 1 to include this filter.

~~~~
SELECT * FROM retirement_titles
WHERE to_date = '9999-01-01';
~~~~