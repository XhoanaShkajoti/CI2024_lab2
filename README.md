# CI2024_lab2
CI2024_lab2

# Travelling Salesman Problem
Solve the given TSP instances using both a fast but approximate algorithm and a slower, yet more accurate one. Report the final cost and the number of steps.

# The fast and approximate first solution 
This solution utilizes a scalable Simulated Annealing (SA) algorithm to solve the Traveling Salesperson Problem (TSP) efficiently. I called it scalable because its supposed to increase the number of steps when the number of the cities is increased. Starts with a greedy solution to approximate a feasible initial tour. This tour serves as a starting point for the Simulated Annealing process, where we iteratively attempt to find shorter paths by gradually "cooling" the solution. To generate neighboring solutions, we perform 2-opt swaps, which reverse the order of cities between two indices. This reduces local loops and often leads to shorter paths.

## Performance 
| Dataset | Steps | Min path length |
| --- | --- | --- |
|Vanuatu | 2010 | 1345.5449 Km |
| Italy | 57540 | 4294.1059 Km |
| Russia | 167 | 42334.164 Km |
| US | 340 | 48050.025 Km  |
| China | 746 | 63962.918 Km |

## The slow but more accurate solution 
Evolutionary Algorithm with Edge Recombination Crossover and Simulated Annealing Mutation.The Evolutionary Algorithm generates a diverse population of potential solutions (tours) and evolves them across multiple generations, selecting the best solutions for the next generation.
1. **Initialization:** A portion of the initial population is generated using a greedy algorithm, while the rest is initialized randomly.
2. **Parent selection:** Tournament Selection, The algorithm uses a tournament selection strategy to choose parents based on their fitness, ensuring that only the best solutions continue.
3. **Genetic operators:** 
      - **Crossover:** Edge Recombination Crossover (ERX)
     - **Mutation:** Simulated Annealing Mutation 
      This operation performs small, probabilistic adjustments in the tour (by swapping or inverting segments), which refines solutions without losing the gains of previous generations.
4. **Population Management:** Steady state 
5. **Selection:** Elitism 

# Performance

| Dataset |Nr Generations | Fitness calls | Best sol Generation | Best sol length |
| --- | --- | --- | --- | --- |
|Vanuatu | 50 | 19800 | 3 | 1345.54 Km |
| Italy | 150 | 59400  | 8 | 4172.76 Km |
| Russia | 200 | 79200 | 118 | 33365.08 Km |
| US | 300 | 99000 | 237 | 40304.48 Km | 
| China | 400|158400  | 374 | 55648.75 Km |
