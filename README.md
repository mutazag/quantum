<!-- TOC -->

- [Azure Quantum](#azure-quantum)
- [Quantum Inspired Optimisation](#quantum-inspired-optimisation)
    - [What is quantum-inspired optimization (QIO)?](#what-is-quantum-inspired-optimization-qio)
    - [Terminology](#terminology)
    - [A single smooth landscape](#a-single-smooth-landscape)
    - [A structured, rugged landscape](#a-structured-rugged-landscape)
    - [A scattered, random landscape](#a-scattered-random-landscape)
    - [Sweet spot for QIO](#sweet-spot-for-qio)
    - [methods for finding global minimum of a cost function](#methods-for-finding-global-minimum-of-a-cost-function)
    - [key concepts](#key-concepts)

<!-- /TOC -->


# Azure Quantum

Programs  here use a simulator to mimic quantum behavior. A simulator is can be used to experiment with quantum algorithms before running the program on a quantum computer. Azure Quantum, a quantum computing service that runs on Azure, can then be used to run the program on quantum hardware. 


![quantum_execution](images\6-quantum-execution-info.png)

* simulators: simulate Q# program on local computer or on azure compute
* resource estimators: estimate the resources required to rn a Q# program on a quantum computer


Quantum-inspired solutions: solve large, complex optimisation problems at scale using quantum-inspired solvers from Microsoft and partners such as 1QBit.

Solvers emulate certain processes from quantum physics by using classical hardware that's available today.

![quantum_hardware](images\6-azure-quantum.png)

* trapped ion quantum hardware from IonQ and Honeywell. 
* quantum hardware built from superconducting circuits from QCI.


# Quantum Inspired Optimisation 

Contoso logistics optimisation example: <https://docs.microsoft.com/en-us/learn/modules/solve-quantum-inspired-optimization-problems/1-introduction>


adiabatic quantum computing for solving optimisation problems: 

* First prepare a system and initialize it to its lowest energy state. For a simple system, one which we completely understand, this is easy to do.
* Next, slowly transform that system into a more complex one that describes the problem you are trying to solve. The adiabatic theorem states that, as long as this transformation happens slowly enough, the system has time to adapt and will stay in that lowest energy configuration. When we're done with our transformations, we've solved our problem.

## What is quantum-inspired optimization (QIO)?

Optimization problems are found in every industry, such as manufacturing, finance, and transportation. In fact, industries such as logistics are dedicated entirely to solving optimization problems. To solve these problems, we search through feasible solutions. The best solution is the one with the lowest cost. Adiabatic quantum algorithms are well-suited to solving many optimization problems.

Today, we can emulate adiabatic quantum algorithms by using quantum-inspired techniques on classical hardware, an approach which is known as quantum-inspired optimization (QIO). These techniques often perform better than state-of-the-art classical optimization techniques.

Applying QIO to real-world problems may offer businesses new insights or help lower costs by making their processes more efficient. QIO gives us the opportunity to:

* Find a solution faster than other optimization techniques for a fixed use case and fixed quality of solution.
* Find a higher quality solution than other optimization techniques for a fixed problem and fixed amount of time.
* Use a more realistic model than other optimization techniques by extending the problem to consider more variables.

Since QIO methods are heuristics, they're not guaranteed to find the optimal solution. Also, they don't always outperform other optimization techniques. In reality, it depends on the problem, and discovering what makes QIO perform better than other methods in some situations and not others is still an active area of research.

## Terminology 

* **Cost function**. This is a mathematical function to be minimized. For Contoso Logistics, the cost function is the weight difference between the two ships. In other scenarios, it might be length of travel or a monetary cost.
* **Search space**. This is the space that contains all the feasible solutions to the optimization problem. Each point in this search space is a valid solution to the problem but it's not necessarily the lowest point, which corresponds to the lowest cost solution.


Together, the search space and the cost function are often referred to as an optimization landscape. In the case of a problem that involves two continuous variables, the analogy to a landscape is quite direct.

## A single smooth landscape 

cost function plot: 

![simple_landscape](images\plot-simple.png)

This kind of problem is easily solved with techniques such as _gradient descent_, where you begin from an initial starting point and greedily move to any solution with a lower cost. After a few moves, the solution converges to the **global minimum**. The global minimum is the lowest point in the optimization landscape. **QIO offers no advantages over other techniques with these straightforward problems.**

## A structured, rugged landscape

QIO works best with problems where the landscape is rugged, with many hills and valleys.

![structured_rugged_landspace](images\plot-rugged.png)

In this scenario, one of the greatest challenges is to avoid getting stuck at any of the sub-optimal _local minima_. A rugged landscape can have multiple valleys. Each of these valleys will have a lowest point, which is the local minimum. One of these points will be the lowest overall, and that point is the _global minimum_. **These rugged landscapes present situations where QIO can outperform other techniques.**

## A scattered, random landscape

random cost function, the solutions are completely random, brute force search is the best technique, no algo can improve on that. 

![random_landscape](images\plot-random.png)

## Sweet spot for QIO

![summary_landspace](images\plot-summary.png)

Here are the necessary conditions for QIO to perform well, compared to other classical optimization algorithms:

* Optimization landscapes should be rugged but structured. Such landscapes occur frequently in real-world problems.
* If the number of variables is too small, then simplistic algorithms are already sufficient. For problems with hundreds of variables, QIO has achieved orders of magnitude improvement over previously used methods.


## methods for finding global minimum of a cost function 

* simulated anealing: a heuristic based on a probabilistic technique for approximating the global optimum of a given function.
* quantum anealing: find low energy state of a problem, and therefore the optimal or near-optimal combination of elements. 

simulated anealing heuristics are useful in situations where finding an exact solution take too long. simulated anealing is not QIC. 

## key concepts

* [Adiabatic quantum computation](https://wikipedia.org/wiki/Adiabatic_quantum_computation) 
* [Gradient descent](https://wikipedia.org/wiki/Gradient_descent) 
* [Simulated annealing](https://wikipedia.org/wiki/Simulated_annealing) 
* [Quantum annealing](https://wikipedia.org/wiki/Quantum_annealing) 
* [Ising model](https://wikipedia.org/wiki/Ising_model) 