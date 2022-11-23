# Retirement Analysis with Python

## Overview of Project
 
### Purpose

The purpose of the project is to analyze retirement data using Python in order to find number of retiring employees per title, and identify employees who are eligible to participate in a mentorship program.

## Results

### Retirement Analysis Results

- 7 unique roles will need to be filled.

- 72,458 employees will have to be replaced.

- 50% of the retirees are engineeres.

- 5% of the retirees are leadership.

## Summary

- How many roles will need to be filled as the "silver tsunami" begins to make an impact?

7 unique roles will need to be filled. 72,458 employees will have to be replaced.

- Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

Yes there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees.

	SELECT DISTINCT ON (e.emp_no) e.emp_no, e.first_name, e.last_name, s.salary, s.from_date, s.to_date, t.title
	FROM employees AS e
	INTO retirement_salaries
	INNER JOIN salaries AS s
	ON (e.emp_no = s.emp_no)
	INNER JOIN titles AS t
	ON (e.emp_no = t.emp_no)
	WHERE s.to_date = '9999-01-01'
	ORDER BY e.emp_no, to_date DESC;

	SELECT title, SUM(salary) AS "salary_sum"
	INTO retirement_salaries_sum
	FROM retirement_salaries
	GROUP BY title
	ORDER BY "title_count" DESC;
