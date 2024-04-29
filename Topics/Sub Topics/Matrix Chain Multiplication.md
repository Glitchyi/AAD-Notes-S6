---
tags:
---
## Time Complexity

$$ O(n^3) $$ 
## Introduction

Matrix Chain Multiplication is a classic optimization problem that seeks the most efficient way to multiply a sequence of matrices. The challenge lies not in the multiplication itself, but in determining the optimal order of matrix multiplications that minimizes the total scalar multiplications involved. This problem is significant in various computational fields, particularly in optimizing the computational complexity of large-scale matrix operations[1][2][4].

## Algorithm

Here is the pseudocode for the Matrix Chain Multiplication using dynamic programming:

```pseudo
function matrixChainOrder(p):
    n = length(p) - 1
    // m[i][j] represents the minimum number of scalar multiplications needed
    // to compute the matrix A[i]A[i+1]...A[j] = A[i..j]
    m = array[1..n][1..n] initialized with 0

    // cost is zero when multiplying one matrix.
    for i = 1 to n:
        m[i][i] = 0

    // l is the chain length.
    for l = 2 to n:
        for i = 1 to n-l+1:
            j = i+l-1
            m[i][j] = infinity
            for k = i to j-1:
                // q is the cost/scalar multiplications
                q = m[i][k] + m[k+1][j] + p[i-1]*p[k]*p[j]
                if q < m[i][j]:
                    m[i][j] = q

    return m[1][n]
```

## Explanation

The algorithm uses a dynamic programming approach to solve the problem by breaking it down into smaller subproblems. It involves a table `m` where the entry `m[i][j]` stores the minimum number of scalar multiplications needed to multiply the sequence of matrices from `i` to `j`.

- **Initialization**: The diagonal of the table `m` is initialized to zero because the multiplication cost of a single matrix with itself is zero.
- **Chain Length**: The algorithm then considers chains of increasing lengths, from 2 up to `n`.
- **Subproblem Calculation**: For each subchain (from matrix `i` to matrix `j`), it calculates the minimum multiplication cost by trying every possible split point `k` between `i` and `j`. For each split, it calculates the cost of multiplying the matrices from `i` to `k` and from `k+1` to `j`, and adds the cost of multiplying the resulting two matrices.
- **Optimal Cost Storage**: The minimum cost found for each subchain is stored in `m[i][j]`.
- **Result**: After filling the table, `m[1][n]` contains the minimum number of scalar multiplications needed to multiply the entire chain of matrices from 1 to `n`.

This approach ensures that all possible parenthesizations are considered, and by using dynamic programming, it efficiently finds the optimal solution by building on solutions to smaller subproblems