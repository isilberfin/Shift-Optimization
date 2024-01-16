# Shift-Optimization
In this project I used [**Google OR Tools**](https://developers.google.com/optimization) to solve a basic shift optimization problem, ensuring efficient employee scheduling while considering preferences and constraints.
OR Tools CP-SAT solver is used for modeling which is the constraint programming tool. For our case, we have 3 shifts that needs to be filled in our company: 08.00-11.00, 11.00-14.00, 14.00-17.00 and  the second shift (11.00,14.00) is the busiest one. 
*dynamic_shift_optimization* is the funtion that solves our problem. It takes 5 parameters : 
* *num_employees :* Number of employees we have in company
* *num_shifts :* Number of shifts 
* *num_days :* Number of working days
* *shift_density :* Number of people needed for shifts
* *employee_preferences :* Employee's working time preference
To check out the model logic, constraint programming and how this code works line by line you can check my [**medium article**](https://medium.com/@isilberfin/shift-optimization-with-google-or-tools-f23da014e480) We defined the 3 components which are necessary for optimization process :
* Decision variables  : I used Boolean variables to represent whether a particular employee is assigned to a specific shift on a given day. It takes a value of 1 if the assignment is made, and 0 otherwise.
* Constraints : 1. There should be at least 2 employees during busy shift, “shift_density” parameter otherwise. 2. Each employee works at most one shift per day.
* Objective : Maximizing employee satisfaction (by considering employee shift preferences)

Also, I created a matrix and did necessary name mappings in the function to have a nice, visual output. The "shift_optimization_solution_matrix.xlsx" file is saved when the function runs

References
* https://developers.google.com/optimization
