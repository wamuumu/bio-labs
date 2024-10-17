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
