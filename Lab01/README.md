# Notes

**Note** Since the sphere function is being used, the better fitness is obtained when the results are closer to zero, which is the global minimum.

## Exercise 1

### _Q1: Do the mutations tend to improve or worsen the fitness of the parent?_

It depends. Mutations can both improve or worsen the fitness based on the parent initial value, the mutation magnitude and the number of dimensions.

### _Q2: Are low or high mutation magnitudes best for improving the fitness? How does this depend on the initial value of the parent and on the number of dimensions of the search space?_

**Note** As the mutation magnitude increases, the range of the generated offsprings increases. 

Depending on the initial value of the parent:
* If the parent has an high initial value (e.g. x = 10), then high magnitudes can help in exploring and achieving a better fitness.
* If the parent has a low initial value (i.e. x = 0.1), then its fitness is already close to zero. Therefore, a low mutation magnitude is preferred.

Depending on the number of dimensions of the search space:
* As the number of dimension increases, the fitness value of the parent moves away from the global minimum. Thus, a higher mutation magnitude is preferred for better exploring and getting closer to the optimal value.
* As the number of dimensions lowers, the fitness value becames closer to the optimal. Therefore, lowers mutation magnitudes are preferred.

## Exercise 2

In the **one-dimensional** condition, the search space is very small. Thus, a mutation can drastically improve or worsen the distance from the global optimum. This is based on the actual parent value and mutation magnitude. In particular, **larger-mutaions** are more likely to move the offsprings' value far from the parent value. For instance, if the value is close to the global minimum and the mutation magnitude is high, then the resulting offsprings would be far away from the global minimum. On the other hand, if the parent value is high, a higher mutation value can significantly move from the parent and may be helpful in improving the overall fitness.

In the **ten-dimensional** case, the search space grows exponentially. In this case, each mutation in each dimension can push the offspring closer to or further from the global minimum. Since here we have 10x the dimensions of the first case, each of them can improve or worsen the fitness of the offsprings. However, random mutations in all dimensions are unlikely to improve fitness. Instead, most mutations push the offspring further from the optimum, worsening fitness in most cases. As for the one-dimensional case, if the mutation magnitude is high and the parent value in all the dimension is close to the optimal minimum, then the result will be a fitness far away from the optimal value. Same thing if the parent value is high, since random mutations tend to worsen the fitness.

In the **hundred-dimensional** case, the search space is very wide. In this case, it's very difficult for random mutations (i.e. with high magnitude) to improve fitness in all the 100 dimensions. Thus, most mutations will likely push the individual further from the global optimum in several dimensions, resulting then in a worse fitness on average.

**Note** As the dimensionality of the parent increases, the effects of random mutations tend to worsen the final result, especially if the parent initial value is far from the global optimum. This is because in high-dimensional spaces, mutations are distributed across many variables, making it less likely for all variables to improve simultaneously. Each mutation has a smaller impact on individual dimensions, and the chance of introducing dangerous mutations in one or more dimensions increases. Consequently, the overall fitness of the offspring tends to degrade as the dimensionality increases, particularly if the initial parent is not already close to an optimal solution.

## Exercise 3

### _Q1: How close is the best individual from the global optimum?_

With the data provided, the best individual is pretty close to global optimum. This is because we are in a one-dimensional space, and the sphere function is able to easily find a really good individual.

### _Q2: How close are the best individuals now from the global optimum?_

As the number of dimensions increases, the algorithm struggles to find very good individuals. For instance, the distance from the global optimum increases exponentially.

### _Q3: Can you get as close as in the one-dimensional case by modifying the mutation magnitude and/or the number of generations?_

As the mutation magnitude increases, the results worsen. This is because in multi-dimensional cases, random mutation are likely to worsen the final results, since each muation tends to move far away from the parent. If the number of generation increases, the results obtained are better, but not even close to the one-dimensional case.

## Exercise 4

### _Q4: Did you see any difference in the best fitness obtained? Try to explain the result._

The results clearly show three different fitness values for the three distinct mutation magnitudes. In particular, the lowest magnitude isn't enough to move towards zero (i.e. the global optimum), while the highest one tends to over explore the search space, moving away from the best value. The middle one strikes a good balance between exploration and stability, achieving the better fitness value.


## Final questions

### _Q1: What is the genotype and what is the phenotype in the problems considered in this lab?_

The genotype is the representation of the parent in the search space, which is not mutated but it is used to generate the offsprings. So, for instance, some genotypes are:
- [1] in one-dimensional cases
- [10, 10] in two-dimensional cases
- N * [100] in N-dimensional cases

Instead, the phonotype is the manifestation of the genotype. So, after mutating the initial genotype (parent), the new genotypes are obtained (offsprings) and the corresponding phenotypes are their fitness values, which represent how good the individuals are.

### _Q2: What are the advantages and disadvantages of low/high mutation magnitudes in EAs?_

There are several advantages and disadvantages of low/high mutation magnitudes.

#### Low mutation magnitudes
- [PRO] If the initial value is good, then low mutation magnitudes can be used to adjust the solution
- [PRO] If the initial value is good, then low mutation magnitudes avoid to negatively affect the solution
- [PRO] Maybe low mutation magnitudes help in the convergence
- [CON] If the initial value is not good, then low mutation magnitudes don't help in the exploration

#### High mutation magnitudes
- [PRO] Can help in the exploration phase
- [PRO] Introduce large variations, which can be good in certain scenario, but bad in others
- [CON] If the initial value is good, then high mutation magnitudes can move the solution far away from the global optimum
- [CON] Maybe they don't help in convergence

### _Q3: Based on the previous observations, do you think there is an optimal mutation magnitude for a biological organism? Do mutations typically improve or worsen the fitness of a biological organism? In which situations do you think low/high mutation rates are advantageous for a population of bacteria?_

1) Based on the previous exercises (especially Exercise 4), I don't think that there's an optimal mutation magnitude, but th privileged ones are those that can strike a balance between exploration and stability.
2) Based on all the previous exercises, mutations typically tend to worsen the fitness because there are really low of them that can be considered benefcial, while the most are neutral or harmful for the offsprings individuals.
3) Low mutation rates are advantageous especially when a high fitness is alredy achieved, meaning that the bacteria populaiton is well adapted to the current environment. Small mutations avoid to drastically move away from that value and to perform harmful changes. On the other hand, high mutation rates are advantageous if the bacteria population need to adapt for a specific environment or extreme conditions (e.g. surving in hot places, antibiotic resistance). These allow the bacteria to explore more genetic solutions and incresing the probability to find beneficial adaptations.

In particular, low mutations rates are preferred in stable environments, while higher ones are crucial in extreme and harmful conditions.