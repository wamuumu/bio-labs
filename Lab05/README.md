# Notes

## Exercise 1

### _How do your results change from the unconstrained version (from the previous lab)?_

As can be seen from the two different plots, in the constrained version the number of "good" solutions is reduced. In the unconstrained version, the Pareto-front presents some solutions that offer a good balance between the two objectives. In contrast, in the constrained version, solutions present worse trade-offs between f0 and f1, resulting in a Pareto-front that is not well-defined. This may happen because some areas of the unconstrained version are now excluded in the constrained one due to costraint violations, leading to a smaller set of optimal solutions.

### _Do your previous parameters continue to solve the problem? (Try to increase the population size and/or the number of generations to see if you can find better solutions)._

As in the unconstrained version, by adjusting parameters like population size and the number of generations, it is possible to achieve better results. For instance, when the population size is increased to 50 and the maximum number of generations to 100, a more diverse set of solutions is found. In this specific case, the Pareto-front becomes more well-defined and similar to what was obtained in the previous lab. However, the constrained version still produces fewer optimal solutions compared to the unconstrained case, since some solutions are discarded due to constraint violations.

## Exercise 2

### _Do you see any difference in the GA’s behavior (and results) when the penalty is enabled or disabled?_

* In same cases, the unpenalized worst fitness fluctuates more due to a larger exploration of the search space
* In some cases, in the unpenalized version, the initial progress is more rapid
* In some cases, the penalized version results in a feasible solution

RosenbrockCubicLine (unpenalized)
Best Individual: [1.03028423 1.05629959]
Best Fitness: 0.003606594729740141
f = 0.003606594729740141
g1 = -0.056271818001571106
g2 = 0.08658382207817095
(unfeasible)

RosenbrockCubicLine (penalized)
Best Individual: [1.00552209 1.01187006]
Best Fitness: 0.017485907885017922
f = 9.37578137006987e-05
g1 = -0.011869892436831009
g2 = 0.017392150071317225
(unfeasible)

RosenbrockDisk (unpenalized)
Best Individual: [1.01732965 1.03480414]
Best Fitness: 0.0003027346443394138
f = 0.0003027346443394138
g1 = 0.10577922851779764
(unfeasible)

RosenbrockDisk (penalized)
Best Individual: [0.97763965 0.96581388]
Best Fitness: 0.010569289946491991
f = 0.010569289946491991
g1 = -0.11142427544858435
(feasible)

### _Try to modify the penalty functions used in the code of each benchmark function, and/or change the main parameters of the GA. Are you able to find the optimum on all the benchmark functions you tested?_

### _Is the GA able to find the optimal solution lying on the unit circle? If not, try to change some of the GA’s parameters to reach the optimum._

Yes, the GA is able to find the optimal solution lying on the unit circle. As described in the Sphere benchmark, the constraint g1 is x^2 + y^2 = 1. Thus, since this is a maximizing problem, then the best solutions should lie on the unit circle and they must have fitness close to 1, like in the example reported below.

* Best Individual: [-0.96962685 -0.23851529]
* Best Fitness: 0.9970657654925787
* f = 0.9970657654925787
* g1 = -0.0029342345074212517 (feasible)

### _By default, the sphere function is defined in a domain [−5.12, 5.12] along each dimension. Try to increase the search space to progressively increasing boundaries (e.g. [−10, 10], [−20, 20], etc.). Is the GA still able to explore the feasible region and find the optimum?_

It depends. For boundaries like [-10, 10] or [-20, 20] the GA is still able to find the optimal solutions, but if they are further increased, then the GA won't be able to find any.

Boundaries: [-10, 10]
Best Individual: [0.96197045 0.26847245]
Best Fitness: 0.9974646058224048
f  = 0.9974646058224048
g1 = -0.002535394177595185
(feasible)

Boundaries: [-20, 20]
Best Individual: [ 0.67411654 -0.73786432]
Best Fitness: 0.9988768572335911
f  = 0.9988768572335911
g1 = -0.0011231427664089022
(feasible)

Boundaries: [-30, 30]
Best Individual: [ 13.88584256 -15.82394546]
Best Fitness: -1
f  = 443.2138735478158
g1 = 442.2138735478158
(unfeasible)

### _If not, try to think of a way to guide the GA towards the feasible region. How could you change the penalty function to do so?_

In order to handle larger search spaces, then the penalty can be further decreased. For example, if the penalty is set to be -1.5 * g1, then all the unfeasible solutions will be strongly penalized and the results will be inside the feasible region with the constraint be respected.

Best Individual: [0.92994    0.36768557]
Best Fitness: 0.9999810845533967
f  = 0.9999810845533967
g1 = -1.891544660326261e-05
(feasible)

### _Try to modify the sphere function problem by adding one or more linear/non-linear constraints, and analyze how the optimum changes depending on the presence of constraints._

## Final questions

### _What do you think is the most efficient way to handle constraints in EAs?_

### _Do you think that the presence of constraints makes the search always more difficult? Can you think of cases in which the constraints could actually make the search easier?_