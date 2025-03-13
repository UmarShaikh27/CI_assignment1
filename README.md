# Evolutionary Algorithm for Solving the Traveling Salesman Problem (TSP)

## Overview

This project implements an evolutionary algorithm to solve the Traveling Salesman Problem (TSP). The algorithm employs various parent and survival selection strategies to evolve a population of solutions over multiple generations.

## Features

- Reads TSP instances from `.tsplib` files
- Computes Euclidean distances between cities
- Implements multiple selection strategies:
  - **Parent Selection:** Fitness Proportionate Selection (FPS), Rank-Based Selection (RBS), Binary Tournament, Truncation, and Random Selection
  - **Survival Selection:** FPS, RBS, Binary Tournament, Truncation, and Random Selection
- Uses order-based crossover and swap mutation
- Tracks and visualizes the best fitness and average fitness over generations

## Requirements

- Python 3.x
- Required libraries:
  - `matplotlib`
  - `numpy`
  - `random`
  - `math`

Install dependencies using:

```sh
pip install matplotlib numpy
```

## Usage

### Running the Algorithm

1. Place the TSP dataset file (e.g., `qa194.tsp`) in the same directory as the script.
2. Run the script with the default settings:
   ```sh
   python tspEA.py
   ```
3. The script will iterate through generations, optimizing the TSP tour and displaying the final fitness results.

### Configurable Parameters

Modify the following parameters in the script:

```python
pop_size = 194  # Population size
num_offspring = 194  # Number of offspring per generation
generations = 400  # Number of generations
mutation_rate = 0.18  # Mutation probability per gene
iterations = 10  # Number of runs for averaging results
parent_selection = "fps"  # Options: "fps", "rbs", "binary_tournament", "truncation", "random"
survival_selection = "rbs"  # Options: "fps", "rbs", "binary_tournament", "truncation", "random"
```

### Output & Visualization

- The script prints the best fitness and best tour found.
- After completing the iterations, it plots the average and best-so-far fitness history across generations.

## Algorithm Breakdown

1. **Read TSP File**: Parses `.tsplib` files to extract city coordinates.
2. **Initialize Population**: Generates a random population of TSP tours.
3. **Evaluate Fitness**: Computes the total Euclidean distance for each tour.
4. **Parent Selection**: Selects parents based on a chosen strategy.
5. **Crossover & Mutation**: Applies order-based crossover and swap mutation.
6. **Survival Selection**: Selects the next generation based on a chosen strategy.
7. **Repeat for Generations**: Evolves the population over multiple generations.
8. **Plot Results**: Displays the convergence trend of the evolutionary algorithm.

## Example TSP Dataset Format (`qa194.tsp`)

```
NAME: qa194
TYPE: TSP
DIMENSION: 194
NODE_COORD_SECTION
1 1088 3763
2 1465 3412
3 2563 2438
...
194 2000 1500
EOF
```



# Job Shop Scheduling Problem (JSSP) Evolutionary Algorithm

## Overview

This project implements an Evolutionary Algorithm (EA) to solve the Job Shop Scheduling Problem (JSSP). The algorithm optimizes job schedules to minimize the makespan (total time required to complete all jobs) by evolving populations of schedules over multiple generations.

## Features

- **Flexible JSSP Instance Parsing:** Reads job and machine data from a text file.
- **Genetic Operators:** Includes selection, crossover, and mutation mechanisms.
- **Multiple Selection Methods:** Supports FPS, RBS, Tournament, Truncation, and Random selection.
- **Graphical Analysis:** Plots the evolution of the makespan over generations.
- **Configurable Parameters:** Allows customization of population size, mutation rate, number of generations, and selection strategies.

## Installation

Ensure you have Python installed along with the required dependencies:

```sh
pip install numpy matplotlib
```

## Usage

1. **Prepare a JSSP instance file** with the following format:
   - The first line contains two integers: the number of jobs and machines.
   - Each subsequent line represents a job with alternating machine IDs and processing times.
2. **Run the algorithm:**

```sh
python q2.py
```

## Code Structure

- **`Operation`**\*\* Class:\*\* Represents an individual operation in a job.
- **`Job`**\*\* Class:\*\* Represents a job consisting of multiple operations.
- **`JSSPInstance`**\*\* Class:\*\* Parses and stores the JSSP data.
- **Evolutionary Algorithm Components:**
  - **Initialization:** Generates random schedules.
  - **Selection:** Different methods to select parents and survivors.
  - **Crossover (PPX):** Ensures precedence preservation in offspring.
  - **Mutation:** Random swaps to introduce diversity.
  - **Evaluation:** Calculates makespan for schedules.
- **Visualization:** Plots the average and best-so-far makespan trends over generations.

## Example Execution

Modify the `file_path` variable to point to your JSSP instance file and configure parameters as needed:

```python
file_path = "abz7.txt"
pop_size = 30
generations = 200
mutation_rate = 0.18
parent_selection = "rbs"
survivor_selection = "tournament"
```

Run the script multiple times to observe algorithm performance over iterations.

## Example .txt format for JSSP instance:



10 5
1 21 0 53 4 95 3 55 2 34
0 21 3 52 4 16 2 26 1 71
......

