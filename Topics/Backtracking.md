---
tags:
  - "#done"
---
[[Topics/N-Queens Problem]]

## Introduction

Backtracking is an algorithmic technique for solving problems recursively by trying to build a solution incrementally, one piece at a time, and removing those solutions that fail to satisfy the constraints of the problem at any point in time. This approach is often applied to constraint satisfaction problems such as puzzles, crosswords, and combinatorial optimization problems. Backtracking can be thought of as a depth-first search (DFS) on a tree where each node represents a partial candidate solution that gets expanded one step at a time.

## Control Abstraction

```control abstraction
function Backtrack(solution):
    # If the current solution is complete and satisfies all constraints
    if isComplete(solution):
        output(solution)
        return
    
    # Construct candidates for the next step of the solution
    for candidate in constructCandidates(solution):
        # Make a move: add the candidate to the solution
        makeMove(solution, candidate)
        
        # Recursively apply the backtracking algorithm with the new solution
        Backtrack(solution)
        
        # Unmake the move: remove the candidate from the solution
        unmakeMove(solution, candidate)
```

## Explanation

Backtracking algorithms consist of a recursive problem-solving approach that incrementally builds candidates to the solutions and abandons a candidate ("backtracks") as soon as it determines that this candidate cannot possibly lead to a final solution.

### Key Components of Backtracking:
- **Choice**: At each step, the algorithm makes a choice from a set of possible options.
- **Constraints**: The algorithm must satisfy specific conditions at each step; if a choice violates a constraint, it is discarded.
- **Goal**: There is a clear end condition that the algorithm must meet to consider a solution complete.

### Process of Backtracking:
1. **Start**: Begin with an empty solution vector or an initial state.
2. **Extend**: Incrementally add components to the solution vector until a solution is formed or constraints are violated.
3. **Constraint Check**: At each extension, check whether the current partial solution satisfies the problem's constraints.
4. **Backtrack**: If constraints are violated, then backtrack to the previous step and try a different option.
5. **Solution Found**: If the solution vector is complete and satisfies all constraints, output the solution.

### Advantages of Backtracking:
- **Completeness**: Backtracking is guaranteed to find all solutions or determine that no solution exists.
- **Space Efficiency**: It uses only linear space, with the maximum depth of the recursion tree corresponding to the size of the solution space.
- **Flexibility**: It can be applied to a wide range of problems without modification to the general algorithm.

### Disadvantages of Backtracking:
- **Time Complexity**: The time complexity can be high because it explores the entire solution space in the worst case.
- **Optimization**: It does not necessarily produce solutions quickly since it may explore many unnecessary paths before finding a solution.

### Common Applications:
- **Puzzles**: Solving Sudoku, N-Queens, and other logic puzzles.
- **Combinatorial Problems**: Generating permutations, combinations, and subsets.
- **Graph Problems**: Finding Hamiltonian cycles, coloring problems, and other graph-related challenges.

In summary, backtracking is a systematic way to iterate through all possible configurations of a search space in order to find solutions to computational problems that satisfy a set of constraints. It is a versatile and conceptually simple approach, though it can be computationally expensive for problems with large search spaces.