# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?
A: First, we need to locate the naked twins which means that what boxes have the same values and they're of length 2 for each of the unit. Then, among all the "common" peers of these twn boxes in each unit, if for any of them whose value contains a subset of the naked twin values, we remove those subset.
Therefore, the local constraint for the naked twins problem is that if 2 boxes in a specific unit have the exact same values, then all the peers of these 2 boxes in this unit cannot contain those 2 values, which results in reducing the search space. By doing so for all the units, then the entire search space would be much smaller.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?
A: We need to make sure either of the diagonal having dinstict numbers, which basically is the same property as the "unit" has. Then as long as we add the diagonal boxes to the unit list, the "search" and "reduce_puzzle" should handle this case.
Therefore, the local constraint for the diagonal sudoku problem is that each of the 2 diagonal must have distinct values from 1 to 9. Then for the boxes on the diagonal, they would have an extra unit to be added to their unit list and thus the peers. As we solve the diagonal sudoku, the reduce_puzzle would consider all the peers for all the boxes, including the diagonal boxes. Then the output results would satisfy the local constraint for the diagonal boxes as well.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project.
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the `assign_value` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login) for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

