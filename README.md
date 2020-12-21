# Simulated Annealing

Simulated Annealing is a probabilistic algorithm used to find an approximate solution to a global optimization problem.  It is inspired by the controlled cooling of metals to reduce defects, known as annealing.  Simulated annealing starts with a random initial solution and a very high initial "temperature" parameter.  Each iteration generates a random neighbouring solution.  If this solution is better it replaces the current solution.  If it is worse then it may replace the current solution with a probability that depends on the temperature parameter; higher temperatures give a higher probability.  As the algorithm progresses, the temperature parameter decreases, giving worse solutions a smaller chance of replacing the current solution.  Allowing worse solutions at the beginning avoids converging to a local minimum rather than the global minimum. The algorithm explores the solution space widely at the beginning, but gradually homes in on a local solution as the temperature decreases.

## Simulated Annealing Algorithm

### Initial Parameters
	•	Find an initial Solution, S, by generating it randomly, Using the origin as the initial node.
	•	Use the provided temperature as the initial temperature
	•	Use the provided value for R, the rate of cooling parameter, given as Alpha
	•	Use Epsilon as the terminating factor

### Hoping between nodes
    • Choose a random neighbour of solution S, and call it S’

### Evaluating that next hop
    • Calculate the difference in cost: DifferenceOfCost= cost(S’)-cost(S)
    • Cost in this case is problem dependant. In a travelling sales man problem, the cost is the distance between nodes.
    • Decide whether to accept the new solution or not: 
      • if DifferenceOfCost<=0 (S’ is better than S, or the same as S), then S=S’, 
        else, set S=S’ with probability e^(-DifferenceOfCost)/CurrentTemperature

### Stopping Conditions 
    • If the initialized stopping conditions are met,
      exit with S as the final solution, 
      else reduce the temperature by setting T=r*T, and repeat from step 1


