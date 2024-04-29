---
tags:
---
[[Topics/Sub Topics/Floyd Warshall|Floyd Warshall]]
[[Topics/Sub Topics/Matrix Chain Multiplication|Matrix Chain Multiplication]]

## Introduction

Dynamic Programming (DP) is a methodological approach used in computer science and mathematics to solve complex problems by breaking them down into simpler subproblems. It is particularly effective for optimization problems where the goal is to find the maximum or minimum solution subject to certain constraints. The essence of dynamic programming lies in solving each subproblem just once and storing its solution in a table, thereby avoiding the need for redundant computations. This approach not only ensures correctness but also significantly improves efficiency, especially for problems with overlapping subproblems and optimal substructure.

## Control Abstraction

```control abstraction
function DynamicProgrammingSolution(problem):
    # Step 1: Identify the subproblems
    subproblems = identifySubproblems(problem)

    # Step 2: Recursively define the solution in terms of subproblems
    defineSolution(subproblems)

    # Step 3: Compute solutions to subproblems bottom-up
    for subproblem in subproblems:
        solution[subproblem] = computeSolution(subproblem)

    # Step 4: Construct full solution from subproblem solutions
    fullSolution = constructSolutionFromSubproblems(subproblems, solution)

    return fullSolution
```

## Explanation

### Process Overview
Dynamic programming algorithms start by identifying overlapping subproblems and optimal substructure within the main problem. The algorithm then solves these subproblems and stores their solutions for future reference. The solutions to larger problems are then constructed from these stored solutions.

### Overlapping Subproblems and Optimal Substructure
- **Overlapping Subproblems**: This is a scenario where the same subproblems are solved multiple times within the context of solving the larger problem.
- **Optimal Substructure**: This implies that an optimal solution to the problem can be constructed from optimal solutions to its subproblems.

### Top-Down and Bottom-Up Approaches
Dynamic programming can be implemented using either a top-down approach with memoization or a bottom-up approach with tabulation.
- **Top-Down with Memoization**: This involves solving the problem from the top down by breaking it into subproblems and storing their solutions for future reference.
- **Bottom-Up with Tabulation**: This solves the problem from the bottom up by first solving the smallest subproblems and then combining their solutions to solve larger subproblems.

### Advantages and Applications
- **Advantages**: Dynamic programming increases efficiency, simplicity, flexibility, optimality, clarity, and code reusability.
- **Applications**: It is applicable to a wide range of problems, such as computing the Fibonacci sequence, finding the longest common subsequence, determining the shortest path in a graph, and solving the knapsack problem.

In summary, dynamic programming is a powerful technique for solving problems that are characterized by overlapping subproblems and optimal substructure. It is an optimization over plain recursion, ensuring that each subproblem is solved only once, which leads to more efficient and effective solutions.