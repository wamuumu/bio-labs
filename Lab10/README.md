# Notes

## Exercise 1

### _Try out different parameter combinations of numOpponents, archiveType, archiveUpdate, and updateBothArchives, and observe what kind of robot behavior is evolved. Can you find cases where the prey "wins"? Can you find cases where the predator "wins"?_

"numOpponents": 1,
"archiveType": "GENERATION",
"archiveUpdate": "AVERAGE",
"updateBothArchives": True,   

 --> Prey fitness is increasing, but also predators fitness is decreasing.
 --> The two fitness values stabilizes at around the same, so it means that no-one wins

"numOpponents": 1,
"archiveType": "GENERATION",
"archiveUpdate": "WORST",
"updateBothArchives": False,   

--> Same as before, but the fitness was a little lower due to the fact that WORST is picked

"numOpponents": 3,
"archiveType": "GENERATION",
"archiveUpdate": "WORST",
"updateBothArchives": False, 

--> Same 

"numOpponents": 3,
"archiveType": "HALLOFFAME",
"archiveUpdate": "WORST",
"updateBothArchives": False, 

For every parameters combination, it seems like that the predators cannot reach the preys. While the prey fitness increases, the other correctly decreases. However, it still doesn't decrease enough to make the predators able to catch the preys. In the simulation, the predator only produces a circle and never vary its movement, while the prey seems to move away from the predator.



### _Try to change the fitness formulation and observe what kind of behavior is evolved. Remember to change the two flags problemPreysMaximize and problemPredatorsMaximize properly, according to the way you defined the fitness function._

## Exercise 2

### _Is the co-evolutionary algorithm able to evolve an optimal (without sorting errors) SN, in the default configuration?_


### _Try to investigate this problem in different configurations. In particular, focus on the effect of the size of the input sequences (`INPUTS`), the number of input sequences per parasite (`P_NUM_SEQ`), and the two population sizes (`POP_SIZE_HOSTS` and` POP_SIZE_PARASITES`). If needed, also change the size of the Hall-of-Fame (`HOF_SIZE`) and the number of generations  (`MAXGEN`). What conclusions can you draw? For instance: What makes the problem harder? What is the effect of `P_NUM_SEQ`? What can you do to solve the harder problem instances?_

## Final questions

### _Can you provide some example applications where you think a competitive co-evolution approach could be used?_

### _Can you think of some other competitive co-evolutionary dynamics in nature different from the prey-predator case?_