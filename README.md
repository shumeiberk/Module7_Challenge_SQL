# Challenge Overview
Now that Bobby has proven his SQL chops, his manager has given him two more assignments: 
- Determine the total number of employees per title who will be retiring, and 
- Identify employees who are eligible to participate in a mentorship program. 
This information will help Bobby’s manager prepare for the “silver tsunami” as many current employees reach retirement age.

Bobby’s new assignment consists of three parts: two additional analyses and a technical report to deliver the results to his manager. To help him complete these tasks, you will submit the following deliverables:

- Technical Analysis Deliverable 1: Number of Retiring Employees by Title. You will create three new tables, one showing number of [titles] retiring, one showing number of employees with each title, and one showing a list of current employees born between Jan. 1, 1952 and Dec. 31, 1955. New tables are exported as CSVs. 

- Technical Analysis Deliverable 2: Mentorship Eligibility. A table containing employees who are eligible for the mentorship program You will submit your table and the CSV containing the data (and the CSV containing the data)

# Resources
Data Source: (departments, employees, dept_emp, salaries, titles, dept_manager.csv) Software: Postgres 11.5, pgAdmin4

# Challenge Results

Given the company size of PH, it was helpful to organize all the employee data in an ERD (entity relationship diagram).  As you can see from the visualization of the relationship across the 6 core databases, there were a lot of relationships between employee data that needed to be established to analyze the pending retirement of the "silver tsunami" and mentorship eligibility.
![EmployeeDB](https://github.com/shumeiberk/Module7_Challenge_SQL/blob/master/EmployeeDB.png.png)

Various queries were built to filter out the essential information to tease out the individuals who are about to retire and those eligible to be mentored.  General reference tables were created (ie manager_info, retirement_info, etc) so that they can be fitlered out for the criteria of upcoming titles that are about to retire.  Given that the databse also would have repeat individuals because of title changes, additional queries were created to count unique the titles and employees.

From the PH employee database there are over 300k employees.  From the queries created, I pulled out interim tables to filter the soon to retire employees which make up around 33k employees across 7 titles.  For additional analysis we will need to find the overlap of how many of those soon to retire can train up the 1.5k unique employees that are eligible to be mentored.  Bobby's recommendation to his manager would be to flag a potential problem with the "silver tsunami" since almost 10% of the PH employees will retire soon but only 1% of employees are eligible to be mentored, which means there could be a big gap in headcount for PH if all 10% decide to retire around the same time but only 1% will be trained up to backfill their roles.  
