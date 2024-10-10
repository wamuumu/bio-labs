# Notes

**Note** The goal is to minimize a certain objective function f(x). Therefore, a lower fitness corresponds to a better solution.

## Exercise 1

### _Q1: What happens if you make λ smaller e.g. λ = μ?_

If λ becomes smaller, then the number of offsprings is reduced. This scenario limits the exploration of new solutions, so the overall fitness is increased.

### _Q2: What happens if you increase the mixing number ρ?_

IF the mixing parameter is increased, then the overall fitness is reduced, obtaining a better result. This happens because more parents are involved in the generation of a new offspring, which means more diversity (i.e. search space increased).

### Different strategies

Instead of using the 'None' strategy, which means that there is no self-adaption, is more convenient to use the 'Global' and 'Individual' strategies, which produce better results. In particular, the 'Individual' strategy is the one that works better and produces overall the lowest fitness. This happens because the 'Global' strategy uses a distinct mutation step-size for each solution, which is better wrt. the 'None' strategy which has a fixed one sigma for all the offsprings. These strategies are however outperformed by the 'Individual' strategy, that introduces a distinct mutation step-size for each genome of each solutions. Of course, more sigmas corresponds to better solutions, since the search space is explored in a better way.  

## Exercise 2

### _Q1: How does the self-adaptation strategy influence performance on this problem?_

Without self-adaptation (i.e. None), the mutation step-size remains fixed, which may lead to slow progress. Woth self-adatpion instead, the mutation step-size is adjusted for each solution (i.e. Global) or for each gene of each offspring (i.e. Individual), leading to a wider exploration of the search space and thus to better solutions.

### _Q2: Does what you see here confirm what you suspected from the previous exercise?_

As it can be seen, the results obtained confirm what it can be saw in the first exercise. In fact, the 'None' strategy is the one producing the higher fitness value, while the 'Individual' strategy is the one producing the lowest.

### _Q3: How do the values of μ, ρ, and λ influence the performance given a particular self-adaptation strategy and other parameters?_

If μ is increased, then the population is increased. This imply more diversity, which can be either beneficial or not. In particular, it can help in the exploration process, but if it becomes too high then the convergence is slowed down.

If ρ is increased, then the diversity is increased. This allows for a better exploration of the search space, and thus produces a better fitness value. This, however, seems to favor only 'Global' and 'Individual' strategies (i.e. self-adaptive strategies).

If λ is decreased, then the number of offsprings is decreased too. This modification limits the exploration of the search space, producing overall worst fitness values. Also here, the 'None' strategy seems to not suffer too much from this change.

### _Q4: Can you come up with any rules of thumb for choosing these parameters?_

A higher value for λ is generally preferred, especially in the early stages where can be beneficial for the exploration. On the other hand, μ and ρ need to be adjusted: if μ is too high, then the algorithm struggles to converge. If the ρ is too small, then the diversity is penalized. It needs to be high in the early stages, and reduced to favor convergence later on.

### _Q5: Can you find a choice of parameters that work properly across several problems?_

After testing different runs with distinc parameters, my conclusion is:
- have a not too small μ (e.g 25 - 50)
- have a small ρ, but not too small to favor diversity (e.g. 5)
- have a λ = 2*μ (e.g. 50 - 100)

## Exercise 3

### _Q1: Can CMA-ES find optima to different problems with fewer function evaluations?_

Yes, CMA-ES with fewer function evaluations outperforms all the previous strategies in all the problem classes.

### _Q2: How do these differences change with different pop. sizes and problem dimensions?_

If the problem dimensions is small, then both CMA-ES and self-adaptive strategies produces optimal results, which simple ES like Individual or Global sometimes performing better, especially if ρ is set correctly. As the number of dimensions increase, then CMA-ES outperforms all the other strategies. For the population size, CMA-ES always outperforms the others.

## Final questions

### _Q1: Do the observations you made while varying μ, ρ, and λ confirm or contradict the conclusions you drew in the previous module’s exercises?_

Yes, increasing λ and μ tends to slow down convergence, but improves robustness by increasing diversity. Also increasing ρ tends to increase diversity, but putting it too small may force a faster convergence.

### _Q2: What are the advantages of self-adaptation in evolutionary computation?_

Self-adaptation allows the algorithm to dynamically adjust the mutation step-size per individual (i.e. Global strategy) or per individual-gene (i.e. Individual strategy), improving performances and leading to a better exploration of the search space.

### _Q3: In what ways might self-adaptation be occurring in biological organisms?_

**Global Self-Adaptation**: A tree that loses its leaves in winter to conserve energy. This is similar to global self-adaptation, where an entire organism changes its behavior to survive harsh conditions. The same happens for example with bears in winter, where they undergo hibernation to contrast food scarisity and hard environmental conditions.

**Individual Self-Adaptation**: A bacteria that needs to adapt a specific gene faster than others in order to face and contrast a new antibiotic.

### _Q4: Compare the different self-adaptation strategies explored in this exercise. In what ways are certain strategies better than others for optimization? In what ways are certain strategies more biologically plausible than others?_

Global strategy works well for simple problems where all the variables (i.e. genes) of an individual can be treated in the same way. Individual strategy, instead, is helpful in complex problems, where each gene needs a special treatment. For this reason, the latter is more biologically plausible (e.g. different traits in a organism evolves with different rates).

### _Q5: Describe what reasons may contribute to better performance of CMA-ES and what can be the conditions when CMA-ES is not better than a basic ES._

As it can be seen from the previous exercises, CMA-ES outperforms basic ES in many cases because it can adapt both the mutation step-size and the covariance matrix, which allows it to change the shape and orientation of the search distribution. However, in simple problems (e.g. low-dimensional), the overhead caused by covariance matrix adaptation of CMA-ES might not yield significant performance gains over a basic ES.