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

- With elitism, the algorithm converges
- Without elitism, 

### _Change the parameter ``num_runs`` to $10$ or more. Does the boxplot confirm -in statistical terms- what you observed on a single run?_

## Final questions

### _What is the genotype and what is the phenotype in the problems considered in this lab?_

### _Why are hidden nodes sometimes needed for a Neural Network to solve a given task? What is the defining feature of problems that networks without hidden nodes are unable to solve?_

### _Why are recurrent connections needed to solve certain problems? What is the defining feature of problems that networks without recurrent connections are unable to solve? Are there problems that require recurrent connections and multiple hidden nodes?_

