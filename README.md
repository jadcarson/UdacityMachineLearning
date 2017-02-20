# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Constraint propagation is using constraints imposed on the problem to narrow the possible 
range for the domain of answers.  You can then use other constraints you have on this smaller 
domain to potentially narrow it further.  This could then open up some previously used 
constraints to reduce the possible domain of answers again.  For naked twins, you look for 
identical sets of 2 possible choices between two peers in the Sudoku grid and then remove those 
choices from all shared peers.  This is an example of using constraint propagation as you have a 
constraint, “if a box and its peer have exactly two choices and those choices are identical, 
no shared peer can be either of those two choices,” and can use it to reduce the domain of 
possible answers for other boxes.  The boxes that had values removed could then freshly fall 
under the naked twins constraint and further reduce the domain for the remaining boxes.  
This could also allow the further use of previously used constraint techniques, such as 
elimination and only choice.  These in turn could then allow naked twins to be run again 
with some new twins appearing.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: For the diagonal Sudoku problem, the constraint propagation used was by using the techniques 
of elimination and only choice.  These were slightly modified by adding two diagonals to the 
peer list, which in turn allowed these two techniques to constrain even more boxes on the 
Sudoku grid.  For example, if the box A1 had a 7 in it, elimination would also constrain the 
boxes D4, E5, F6, G7, H8, and I9 to not having a 7 in them in addition to all the other boxes 
it constrains in a normal Sudoku.  

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.