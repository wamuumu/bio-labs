# Notes

## Exercise 1

### _Do the same EA parameters that you used for ``Or`` work for ``And`` as well? If not, modify them until you are able to solve ``And``._

The same parameters used to resolve the `Or` worked also for the `And`, with the last producing however a slightly higher fitness (e.g. 0.013 compared to 0.0009). This happens because these two operations are straightforward and simple.

### _Can you solve it? If you are unable to solve it, why is that?_

The `Xor` operation cannot be solved by the network. This happens because this operation isn't **linearly separable**, so a ANN with only input and output layer cannot resolve it.

### _Does this allow you to solve the problem? What if you change this value to 2 or more?_

With the addition of 1 hidden units, the ANN still cannot solve it. This addition improves the single decision boundary given by the previous layer, but it is not enough. If the number of hidden units is increased again to 2 or more, then the ANN can now resolve the `Xor` operation because there are enough hidden units for the creation of two decision boundaries.

### _How many hidden nodes are required to solve this problem? Can you provide an explanation for why that is the case?_

In order to solve the `Xor` problem, at least two hidden nodes are required as they allow the network to understand the minimum of two decision boundaries to solve it.

## Exercise 2

### _Can you solve it? If you are unable to solve it, why is that?_

With the provided ANN structure, the `TemporalOr` cannot be solved. This happens because the provided network structure isn't able to remember any previous value, as it is a simple FFNN.

### _If you set ``recurrent`` to be ``True``, can you now evolve a successful network?_

Yes, by setting ``recurrent`` to ``True``, the ANN can now solve the problem.

### _Why might recurrence be important for solving a temporal problem such as this?_

Recurrence might be important for solving temporal problems since it provides the NN a system to process sequential data, so the ability to remember at each time step (t) what happened before in order to adapt the output dinamically.

### _Do the same EA parameters that solved ``Temporal Or`` also work for ``Temporal And``? Why, or why not?_

Yes, the same parameters also worked for the `Temporal And` problem. This is because, similar to the `Temporal Or`, the neural network needs to remember whether the first input was a `1`. In `Temporal And`, the network should output a `1` only if both inputs are `1` (i.e., two consecutive ones). The recurrent connection allows the network to maintain this memory across time steps, enabling it to correctly apply the AND logic, similarly to what happened for the OR logic.

### _Are you able to find a successful network for the ``Temporal Xor``?_

Yes, to solve the ``Temporal Xor`` problem, it is necessary to increase the number of hidden units to **2 or more**. This is because, while recurrence allows for a sort of memory system, a single hidden unit alone cannot solve a non-linearly separable problem like ``Xor``. The additional hidden units allow the network to form multiple decision boundaries to solve the ``Temporal Xor``. (Before, in order to resolve the static ``Xor``, the NN was provided with two fixed input units. In this case, the recurrence is foundamental to make the NN able to behave like the static one with the _memory_, and as in the previous case two or more hidden units are required).

### _If not, think back to what you just saw in the previous exercise. What combination of recurrence and no. of hidden nodes is needed to solve ``Temporal Xor`` and why is that?_

_See previous answer._

## Exercise 3

### _What do you observe? Is the algorithm without elitism able to converge to the optimal fitness value? What about the algorithm with elitism? What is the effect of elitism on convergence? What about the number of species and their dynamics?_

The elitism produces overall the best fitness, reaching a faster convergence than the no-elitism, which value fluctuates significantly and doesn't surpass the fitness value of 3 (it never reaches the optimal value). In particular, in the no-elitism, species are not stable, with frequent changes (i.e. the beneficial traits are not taken into consideration). Thus, it can be seen that elitism produces overall less species because elite individuals are preserved and less changes are made between each generation. The effect of elitism on convergence is that elite individuals are preserved, allowing their beneficial traits to be passed on continuosly among the generations.

### _Change the parameter ``num_runs`` to 10 or more. Does the boxplot confirm -in statistical terms- what you observed on a single run?_

Yes, it can be clearly seeen that the elitism produces overall the best fitness value. However, it this case, the no-elitism algorithm can surpass the fitness value of 3. The distribution of data shows that it goes between 3 and 3.9, with most of the data between 3.2 and 3.8, some outliers outside this range and a median value of 3.3. This suggests that in more runs also the no-elitism can achieve good results, that however aren't even closer to the elitism.

## Final questions

### _What is the genotype and what is the phenotype in the problems considered in this lab?_

In the problems considered during this lab, the genotype encodes the actual NN structure, so all the information regarding nodes, links and hidden units. The phenotype is instead the actual NN in action, that interacts with some input values and produces the output for ``OR``, ``AND`` and ``XOR`` problems.

### _Why are hidden nodes sometimes needed for a Neural Network to solve a given task? What is the defining feature of problems that networks without hidden nodes are unable to solve?_

Hidden layers are sometimes required to solve a given task because they allow a NN to learn and represent non-linear relationships between input and output (they enable the NN to learn how to combine the inputs in complex ways in order to solve a given problem). Without them, a NN would never be able to solve problems that are not linearly-separable like XOR.

### _Why are recurrent connections needed to solve certain problems? What is the defining feature of problems that networks without recurrent connections are unable to solve? Are there problems that require recurrent connections and multiple hidden nodes?_

Some problems require recurrent connections to be solved since they give the NN the ability to retain information about previous inputs, enabling it to handle tasks that involve sequential data over time. The set of problems that these NNs are able to solve includes those with temporal dependencies, where a good outcome can be achieved only by introducing a sort of "memory" system, since data heavily rely on previous values (e.g. Natural Language Processing, Speech Recognition, Regression problems like Forecasting and many more).

