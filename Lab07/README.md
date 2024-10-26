# Notes

## Exercise 1

### _Which algorithm provides the best solution in most cases?_ 

In all the three problem instances, the ACS produces by far the shortest distance, meaning that in all the scenarios it has obtained the higher fitness.

### _What can you say about the number of function evaluations needed to converge?_

As shown in the plots, within the first few hundred evaluations the ACS fitness graph produces a quick rise in fitness, meaning that it is more suited to TSP problem compared to the EA. After this initial peak, there are some fluctuations, meaning that the algorithm tries to explore different solutions, but no significant improvements are performed, so overall the ACS stabilizes very quickly. For the EA, the best solution increases across function evaluations, showing a gradual and continuos improvement over time. The convergence here happens more slowly than ACS, with improvements still visible at then end of the evaluations (i.e. it requires a lot of evaluations to stabilize and convergence).