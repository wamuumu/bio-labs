# Notes

## Exercise 1

### _Which algorithm provides the best solution in most cases?_ 

In all the three problem instances, the ACS produces by far the shortest distance, meaning that in all the scenarios it has obtained the higher fitness.

### _What can you say about the number of function evaluations needed to converge?_

As shown in the plots, within the first few hundred evaluations the ACS fitness graph produces a quick rise in fitness, meaning that it is more suited to TSP problem compared to the EA. After this initial peak, there are some fluctuations, meaning that the algorithm tries to explore different solutions, but no significant improvements are performed, so overall the ACS stabilizes very quickly. For the EA, the best solution increases across function evaluations, showing a gradual and continuos improvement over time. The convergence here happens more slowly than ACS, with improvements still visible at then end of the evaluations (i.e. it requires a lot of evaluations to stabilize and convergence).

## Exercise 2

**Note** Needed to change benchmarks.py code for Knapsack, otherwise overflow error:

```python 
import numpy as np

fitness.append(np.int64(self.capacity) - np.int64(total_weight))
```

### _Which algorithm provides the best solution in most cases?_ 

The ACS provides the best solution in most cases, especially with the increase of the knapsack's capacity. For lower capicity, the two algorithms provide very similar results, with EA sometimes beating ACS.

### _What can you say about the number of function evaluations needed to converge?_

Both algorithms seem to converge fast, with a rapid rise in fitness within the first evaluations. However, ACS seems to be faster and quicker: both "best fitness" and "median and average fitnesses" stabilize early on, meaning that ACS needs fewer evaluations than EA.

## Exercise 3

### _Which algorithm provides the best solution in most cases?_

Also in this version of the Knapsack, the ACS seems to perform better, especially with larger capacities.

### _What can you say about the number of function evaluations needed to converge?_

Same as before, the ACS shows a more stable behavior respect to the EA, which increases as the evaluations increase.

### _Do you observe any difference on the algorithmic behavior between this exercise and the previous one?_

The two behaviors seems pretty similar, with the 0/1 Knapsack version performing little better.

### Final questions

### _What are the main differences between continuous and discrete optimization problems? Do you think that any of these two classes of problems is more difficult than the other?_

In continuos problems, decision variables can take any value within a range, while in discrete problems (such as TSP) each variable is a discrete value (such as a city). For this reason, I think that discrete problems are simpler than continuos ones, such as the search / solution spaces are finite with a limited number of solutions to consider.

### _Why is ACO particularly suited for discrete optimization?_

ACO mimics ant behavior, with ants making discrete decisions guided by pheromones in order to reach food. This probabilistic step-by-step approach works well in discrete problems like TSP or Knapsack, since iteratively the solution is constructed and adjusted by improving and exploring new paths.

### _Consider the two versions of the Knapsack problem (0/1, and with duplicates). Which of the two problems is more challenging from an optimization point of view? Why?_

In the 0/1 version, the optimizer needs only to decide wheter to include or not a specific object in the knapsack. For this reason, 0/1 is much simpler than the other version, given that the duplicates version introduces more combinations to evaluate. 