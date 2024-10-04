# Notes

## Exercise 1

**Kursawe Objective functions**
![alt text](./img/img_02/Kursawe.png "Kursawe objectives")

### _Q1: What happens when you run the GA with this fitness function?_

If the GA is run with this specific configuration of combining two functions into a single fitness one with weights = [0.5, 0.5], then initially the fitness is very high (around 8-9) especially in the worst individuals. Then, as it can be seen, it makes rapid progress in improving both objective functions. After around 1000 evaluations, the rate of improvement is slowed down as the algorithm converges towards an optimal solution, which tries to achieve the best possible fitness goals in both functions (i.e no improvements are made).

### _Q2: Why do you obtain this result?_

This result is obtained since two different objective functions are combined into a single one with equal weights, meaning that the GA is trying to optimize them both equally. After around 1000 evaluations, the algorithm struggles to improve the fitness, since the objectives relative scaling is pretty much different (f1 tends to produce negative values, while f2 instead tends to produce positive values due to the sine function)

### _Q3: What happens if you give the first (or second) objective all of the weight?_

If an objective function get all of the weights (i.e. weight = 1), then the multi-obejctive GA problem essentially turns into a single-objective optimization problem. This means that the algorithm tries to achieve better fitness only on the specified function, and the associated results will be highly optimized for that particular objective.

### _Q4: Can you find a weighting able to find a solution that approaches the optimum on both objectives?_ 

In my opinion, the best overall performance is achieved when both objectives are assigned equal weights, either with additive or multiplicative method. In this way, it sure that the results aren't skewed towards a certain objective. However, I noticed that significant results can also be obtained by increasing the weight of the second objective, for example, using weights of [0.4, 0.7] or [0.3, 0.7]. In these cases, the best individuals are typically found more quickly, stabilizing around 1000 evaluations. This may occur because greater emphasis is placed on the second objective, which tends to yield higher positive values initially, leading to better solutions in fewer evaluations.

### _Q5: Does your weighting still work on the new problem?_

Also here, I think that the best weighting is achieved when all the objectives are assigned equal weights, since it's more balanced, but little slower compared in terms of convergence compared to an approach where the last objective gets the higher weight (e.g. weights = [0.3, 0.3, 0.4] or also [0.25, 0.25, 0.5]).

**Note** It seems that privileging complex functions with higher weights tends to stabilize the results faster, but the overall best solution is slightly penalized. 

### _Q6: Can you think of a method for combining the objectives that might work better than using a weighted sum?_

While the combination of multiple objective functions into a single one using a weighted sum is easy to understand and implement, I still think that other techniques such as NSGA2 perfoms better. However, if the focus is the combination of multiple objectives into a single one, then a better approach would be an **adaptive weighting**, which is similar to an additive weighting, but with weights that change and adapt over time. With this approach, the algorithm can give much importance to certain objectives in the early stages, and dynamically adjust the weights of the other functions in the middle stages.

## Exercise 2

### _Q1: How do the solutions you find here compare to those found in exercise 1?_

As can be seen in the plotted Pareto front, the two objectives seem proportionally inverse. In fact, lower values for f1 leads to higher values for f0 and viceversa. This happens because, as we already saw in the first exercise, the two objectives have different relative scaling.

### _Q2: Is there a single solution that is clearly the best?_

In my opinion, the best solution needs to be searched in the middle of the front [-18, -15]. As it can be seen, the best solutions is the one that achieves f0 = -17.5 and f1 = -3.5

### _Q3: Can you still find good solutions?_

### _Q4: What happens if you increase the population size or the number of generations?_

## Exercise 3

### _Q1: Is the algorithm able to find reasonable solutions to this problem? Use what you have learned about population sizes and number of generations to improve the quality of the found solutions._

The algorithm seems to find reasonable solutions to this problem, as highlighted by the Pareto front plotted. This shows a set of trade-off solutions between the two objectives: minimizing brake mass (f0) and minimizing stopping time (f1). With the provided population size of 10 and a maximum of 10 generations, the algorithm is able to find a set of reasonable, but limited solutions for the disk brake design problem. From previous exercises, I saw that reasonable numbers for population and generations would be respectively 50 and 100. By setting this values, the Pareto front covers a wider range of solutions.

### _Q2: Do you see any patterns in the Pareto-optimal solutions that may help you in designing a well-performing disk-brake in the future?_

From the plotted Pareto front, it is clear that there's is an inverse relationship between the two objectives. As the mass f0 decreases, the stopping time f1 increases and viceversa. This translates in "lighter brake results in worse performance of stopping time". For a future design of this system, I think there's a need to a trade-off between the twos: for example, if the car has a limiting mass, then we may accept longer stopping time and viceversa. Another thing to note is that in certain points, if the mass is reduced slightly, the time is increased by a small amount. So these solutions need to be taken into account and considered acceptable.

## Instructions & Questions 