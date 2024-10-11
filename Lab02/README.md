# Notes

**Note** Since the sphere function is being used, the better fitness is obtained when the results are closer to zero, which is the global minimum.

## Exercise 1

**Note** In this first exercise, the mutation and crossover rates are set both to 1 in distinct runs, thus the expected results should produce mutation-only and crossover-only offsprings.

### _Do you see any difference between the two results? Why?_

From the results obtained running the first exercise, it is clear that there's a difference between the results of mutation-only and crossover-only in terms of fitness. In particular, mutation-only approach produces lower fitness value, which is better given that the sphere optimization function is used and the goal is to minimize the fitness. The difference between the two results can be explained by the fact that **mutation-only approach** allows for exploration of the search space, retrieving information for new genetic material that can improve the fitness. On the other hand, **crossover-only approach** only recombines existing genetic material, limiting the arease of the search space to explore. Given that the population lacks in diversity, this approach may fail to achieve optimal fitness values.

## Exercise 2

**Note** In this exercise, the mutation rate is fixed and set to 50%. Thus, a genome has a 50% chance to mutate. However, the crossover rates change.

### _Is there an optimal crossover fraction for this fitness function? Why?_

The optimal crossover fraction depends on how well crossover can combine useful traits from parents. By running the exercise with different crossover rates ranging from [0...1], the results show that the optimal range is around `0.5`. This happens because a balanced approach between mutation (fixed to `0.5`) and crossover can introduce a good mix of **exploration** and **exploitation**. Higher values for crossover can limit the exploration, while lower values can reduce the mix of traits. 

## Exercise 3

### _Which tournament size gives better results for the fitness function sphere and why?_

For the sphere function (unimodal), a larger tournament size tends to give better results. This happens because a **higher selection pressure** is applied (2 groups of 10 where we take 1 champion each), meaning that **less offsprings individuals with better fitness** are taken. This approach helps in the convergence towards to the unique global optimum of the sphere function.

### _Which tournament size is better for the fitness function Rastrigin and why?_

![Rastrigin Objective Function](./img/img_02/Rastrigin_function.png "Rastrigin function")

On the other hand, for the Rastrigin function, a smaller tournament size produces the best results. This happens because the Rastrigin function is a multimodal function, meaning that it has many local optima. By applying a **lower selection pressure** (10 groups of 2 where we take 1 champion each), the algorithm maintains more **diversity** in the population, which helps in exploring different regions of the search space (i.e. smaller tournament size avoid a faster convergence to the local optima)

## Exercise 4

**Note** By increasing the population initial range, the overall diversity between the individuals in increased, leading the solution to move away from the optimal value.

### _Do you see a different algorithmic behavior when you test the EA on different benchmark functions? Why?_

Yes, different benchmark functions exhibit different behaviours based on their parameters, given that some of them are unimodal while others multimodal.

#### Mutation magnitude
In unimodal functions, where there is one gloabal optimum, a low mutation magnitude is potentially preferred as it usually allows a faster convergence to that point. Too high mutation magnitudes can potentially move far away the fitness from the optimal value.

In multimodal functions, where there are many local optima and one global optimum, a higher mutation magnitude can be helpful to escape the local optima. This allow for a faster exploration that can be useful to reach the global optimum. Similar to unimodal functions, if the mutation magnitude is too high, then the exploration becomes completely random, potentially moving far away from the global optimum.

#### Crossover rate
In both unimodal and multimodal functions, the crossover rate should often be set to an intermediate value (e.g. `0.5`) to obtain the best performance. 

However, in unimodal functions, a slightly higher rate (e.g. `0.75`) can be beneficial to accelerate the convergence to the global optimum. This is not true in multimodal functions, where a higher crossover rate can lead to a premature convergence to a local optima.

#### Selection pressure
By changing population size and tournament size, the selection pressure is affected. 

Unimodal functions are benefited if less "groups" are created (i.e. high tournament size, meaning high selection pressure). Since there is only a global optimum, a high selection pressure accelerate convergence by favoring the individuals with the best fitness. In multimodal functions, a lower selection pressure should be preferred, given that a premature convergence can lead the solution towards a local optima.

### _What is the effect of changing the number of variables on each tested function?_

Increasing the number of variables increases the complexity of each function, as they represent the number of dimensions in the search space. A higher number of dimensions tends to make the search more difficult, producing higher overall fitness values, especially in multimodal functions.

## Final questions 

### _Why is it useful to introduce crossover in EA? Can you think of any cases when mutation only can work effectively, without crossover? What about using crossover only, without mutation?_

1) Crossover can be useful in evolutionary algorithms since it allows for the combination of the genetic material from two distinc parents, allowing the new offspring to inherit beneficial traits from both. 

2) Mutation-only can be beneficial when a unimodal low-dimensional problem needs to be analyzed or in all those problems where solutions are already close to the optimal and only need to be fine-tuned with a small mutation magnitude. Mutation can be beneficial when the initial population has a low diversity.

3) Crossover-only can be used where the initial population has a high diversity, meaning that new solutions can be found by only recombining the beneficial traits of the parents or when solutions are already close to the optimal and only need to be adjusted by a little.

### _What’s the effect of changing the fraction of offspring created by crossover?_

By changing the crossover rate, new solutions can beneficiate from both exploration with mutation and exploitation with crossover. This allows the next generation to inherit and combine beneficial traits from the parents while also introducing variations that can lead to better solutions.

### _Are there optimal parameters for an EA?_

Results during this lab showed that an optimal value for both crossover and mutation rates is `0.5`, which strikes a good balance between exploration and exploitation. All the other parameters are problem-specific, meaning that they need to be adjusted accordingly based on the actual problem.

### _What are the advantages and disadvantages of low/high selection pressure?_

High selection pressure is obtained when a small set of individuals with the better fitness is chosen. This could lead to a faster convergence by exploiting the best solutions for future generations (e.g. unimodal functions). However, this approach penalize the diversity of the population by eliminating individuals with lower fitness and can potentially move the solution to a premature convergence (e.g. multimodal functions).

On the other hand, low selection pressure allows for diversity preservation, enabling less fit individuals to contribute in the evolution process. This may lead to slow convergence, which can be really helpful in multimodal functions where local optima need to be avoided, but doesn't give any major focus to good solutions.