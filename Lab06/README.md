# Notes

## Exercise 1

### _What is the effect of each behavior coefficient?_

* Alignment (angle of the neighbors): this aligns the boid velocity to the average velocity of near boids, so that they keep moving in the same direction. If this coefficient is increased, then boids match their velocity (direction and speed) more closely with their neighbors, forming a more unified cluster. On the other hand, a lower coefficient makes the boids' movement more independent.

* Cohesion (distance from the center of the swarm): this encourages boids to move towards the average position of nearly boids. If this coefficient is increased, then it causes boids to cluster together more rapidly. Otherwise, the boids result in a more disperse movement.

* Separation (distance from the neighbors): this ensures that boids avoid collisions by maintaining a safe distance from the neighbors. If this coefficient is increased, then the crowding effect is reduced. Otherwise, they move closer and closer, potentially leading to overcrowding and increased collisions.

### _Which combination of coefficients leads to the most `natural` flock behavior?_

In my opinion, the most `natural` flock behavior is achieved with:
* A high alignment coefficient (e.g. 0.8)
* A medium cohesion coefficient (e.g. 0.5)
* A medium separation coefficient (e.g. 0.5)

## Exercise 2

### _What kind of behavior does PSO have on different benchmark functions, in comparison with the EAs? Does it show better or worse results? Does it converge faster or not?_

By comparing the PSO with the EA and the GA, it can be noticed that:
* GA produces the highest fitness within the three algorithms
* In terms of best fitness, EA and PSO are very close. Sometimes EA performs little better, other times PSO performs better. Overall, EA seems more consistent.
* In terms of convergence, EA is much more faster: all the plots (best, average, median and worst) converge quickly to very low fitness values, meaning that the EA is able to rapidly solve the problem. On the other hand, PSO show more fluctuations, especially in the worst case although the best and median values remain low.

### _What happens if you run the script multiple times? Do the various algorithms (and especially PSO) show consistent behavior?_

In the unimodal cases, the three algorithms seem to be consistent. The results obtained by running multiple times the Sphere and Rosenbrock functions are very close. In particular, the GA best fitness is really close in each test, while the EA and PSO best values can slightly increase or decrease, showing sometimes better performances on EA and other times on PSO.

In the multimodal cases, the EA seems to be the more consistent approach in both convergence and best fitness overall. By running different tests, it has been noticed that sometimes the PSO best fitness is the best among the three algorithms (e.g. in a Griewank benchmark the ES obtained 0.42 while the PSO 0.007). However, in most the cases, the ES produces the best fitness values and it's by far the faster to converge.

### _Increase the problem dimensionality. What do you observe in this case?_

By increasing the problem dimensionality, the behavior of the plots seems to remain consistent (e.g. the ES is the faster to converge and shows less fluctuations). Of course, the best fitness values have changed, showing that in the unimodal cases the lowest values are achieved by the GA, followed by ES and finally by PSO. On the other hand, in the multimodal cases, GA and PSO are the ones that perform better, while ES achieved, for most the tests, the worst fitness values. 

| Results with a 20-dimensionality problem | 1°  | 2°  | 3°  |
|------------------------------------------|-----|-----|-----|
| Sphere                                   | GA  | ES  | PSO |
| Rosenbrock                               | GA  | ES  | PSO |
| Griewank                                 | GA  | PSO | ES  |
| Ackley                                   | ES  | GA  | PSO |
| Rastrigin                                | GA  | PSO | ES  |
| Schwefel                                 | PSO | GA  | ES  |

### _Change the population size and the number of generations, such that their product is fixed. Try two or three different combinations and observe the behavior of the three different algorithms. What do you observe in this case? Is it better to have smaller/larger populations or a smaller/larger number of generations? Why?_

By changing the fixed product between population size and number of generations, also the algorithms performances change. In particular, in all the three, as the population decreases and the number of generation increases, the results obtained are better since:
* GA seems to perform the same in all the cases. With lower population, the algorithm has more opportunities to explore different areas with mutation and crossover
* For the same reason as GA, a smaller population with more generations can allow ES for a more detailed and gradual exploration. 
* PSO has much more time to make its particles iteratively adjust their positions, gradually converging on optimal solutions.

**Note** Although lower population resulted in the best results, it is important to remember that can lead to a faster and premature convergence due to for example lack of diversity.

| Sphere function  | 100 pop / 50 gen | 50 pop / 100 gen | 25 pop / 200 gen | 10 pop / 500 gen |
|------------------|------------------|------------------|------------------|------------------|
| GA               | 2.06e-05         | 1.37e-05         | 1.62e-05         | 7.90e-07         |
| ES               | 1.32e-14         | 1.19e-14         | 7.07e-15         | 8.65e-16         |
| PSO              | 8.73e-10         | 6.56e-14         | 4.26e-26         | 2.32e-52         |

## Final questions

### _When do you think it is useful to have a lower (higher) cognitive learning rate? What about the social learning rate?_

A lower cognitive learning rate can be useful in all those problems where there are many local optima (such as in multimodal problems) and the particles are likely getting stucked in their own local best positions. On the other hand, a higher congnitive learning rate can be used if the global best changes and particles doesn't need to rely on that, but instead much more on their local best positions.

Following the beforementioned examples, if the global best changes, then a lower social learning rate is preferred to prevent the convergence to an outdated point. On the other hand, a higher social learning rate is used when the global optimum is stable and reliable, thus emphasizing the convergence to that point (e.g. in a unimodal function).

### _From a biological point of view, which neighborhood topology do you consider as the most plausible?_

From a biological point of view, I think the most plausible topology would be the _ring topology_. It effectively captures the nature of local interactions, reflecting how many species operate within **small groups** and interact primarily with their immediate **neighbors** (e.g. friends and family). Another good consideration can be done with the _cluster topology_, which embodies the social structures where animals make groups and interact mostly within them, and occasionally with neighborign groups.
