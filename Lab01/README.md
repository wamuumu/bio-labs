# Notes

## Exercise 1

**Note**: Since the sphere function is being used, the better fitness is obtained when the results are closer to zero, which is the global minimum.

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
