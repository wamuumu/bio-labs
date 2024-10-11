# Notes

## Exercise 1

### _How do your results change from the unconstrained version (from the previous lab)?_

As can be seen from the two different plots, in the constrained version the number of "good" solutions is reduced. In the unconstrained version, the Pareto-front presents some solutions that offer a good balance between the two objectives. In contrast, in the constrained version, solutions present worse trade-offs between f0 and f1, resulting in a Pareto-front that is not well-defined. This may happen because some areas of the unconstrained version are now excluded in the constrained one due to costraint violations, leading to a smaller set of optimal solutions.

### _Do your previous parameters continue to solve the problem? (Try to increase the population size and/or the number of generations to see if you can find better solutions)._

As in the unconstrained version, by adjusting parameters like population size and the number of generations, it is possible to achieve better results. For instance, when the population size is increased to 50 and the maximum number of generations to 100, a more diverse set of solutions is found. In this specific case, the Pareto-front becomes more well-defined and similar to what was obtained in the previous lab. However, the constrained version still produces fewer optimal solutions compared to the unconstrained case, since some solutions are discarded due to constraint violations.

## Exercise 2

### _Do you see any difference in the GA’s behavior (and results) when the penalty is enabled or disabled?_

### _Try to modify the penalty functions used in the code of each benchmark function, and/or change the main parameters of the GA. Are you able to find the optimum on all the benchmark functions you tested?_

### _Is the GA able to find the optimal solution lying on the unit circle? If not, try to change some of the GA’s parameters to reach the optimum._

### _By default, the sphere function is defined in a domain [−5.12, 5.12] along each dimension. Try to increase the search space3 to progressively increasing boundaries (e.g. [−10, 10], [−20, 20], etc.). Is the GA still able to explore the feasible region and find the optimum?_

### _If not, try to think of a way to guide the GA towards the feasible region. How could you change the penalty function to do so?_

### _Try to modify the sphere function problem by adding one or more linear/non-linear constraints, and analyze how the optimum changes depending on the presence of constraints._

## Final questions

### _What do you think is the most efficient way to handle constraints in EAs?_

### _Do you think that the presence of constraints makes the search always more difficult? Can you think of cases in which the constraints could actually make the search easier?_