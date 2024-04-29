---
tags:
---
## Time Complexity

$$ O(n^2.81) $$ 
## Introduction

Strassen's algorithm is a divide-and-conquer algorithm used for matrix multiplication. It is an efficient method for multiplying two matrices, especially when the matrices are large. The algorithm reduces the number of scalar multiplications required, making it more efficient than the standard matrix multiplication algorithm, which has a time complexity of O(n^3).

The main idea behind Strassen's algorithm is to divide the matrices into smaller sub-matrices, perform matrix multiplications on these sub-matrices, and then combine the results to obtain the final product matrix. This approach takes advantage of the fact that matrix multiplication can be expressed in terms of addition and subtraction of products of smaller matrices.
## Algorithm

The Strassen's algorithm for matrix multiplication can be described as follows:

```
STRASSEN(A, B)
    if A and B are small enough (e.g., 1x1 matrices)
        return A * B  // Perform standard matrix multiplication

    else
        Divide A into four sub-matrices:
            A11, A12, A21, A22
        Divide B into four sub-matrices:
            B11, B12, B21, B22

        P1 = STRASSEN  (A11 + A22, B11 + B22)
        P2 = STRASSEN  (A21 + A22, B11)
        P3 = STRASSEN  (A11, B12 - B22)
        P4 = STRASSEN  (A22, B21 - B11)
        P5 = STRASSEN  (A11 + A12, B22)
        P6 = STRASSEN  (A21 - A11, B11 + B12)
        P7 = STRASSEN  (A12 - A22, B21 + B22)

        C11 = P1 + P4 - P5 + P7
        C12 = P3 + P5
        C21 = P2 + P4
        C22 = P1 - P2 + P3 + P6

        Combine the sub-matrices C11, C12, C21, and C22 to form the final product matrix C

    return C
```

### Explanation

1. The `STRASSEN` function takes two matrices `A` and `B` as input.
2. If the matrices are small enough (e.g., 1x1 matrices), the standard matrix multiplication is performed, and the result is returned.
3. Otherwise, each matrix is divided into four sub-matrices: `A11`, `A12`, `A21`, `A22` for matrix `A`, and `B11`, `B12`, `B21`, `B22` for matrix `B`.
4. Seven products (`P1` to `P7`) are computed recursively using Strassen's algorithm on various combinations of the sub-matrices.
5. The final product matrix `C` is constructed by combining the results of the seven products using addition and subtraction operations.
6. The sub-matrices `C11`, `C12`, `C21`, and `C22` are combined to form the final product matrix `C`.
7. The function returns the final product matrix `C`.

---

The key advantage of Strassen's algorithm is that it reduces the number of scalar multiplications required for matrix multiplication. Instead of the standard O(n^3) time complexity, Strassen's algorithm has a time complexity of O(n^2.807), which makes it more efficient for large matrices.

It's important to note that Strassen's algorithm becomes more efficient than the standard matrix multiplication algorithm only when the matrices are sufficiently large. For small matrices, the overhead of dividing and combining the sub-matrices may outweigh the benefits of the algorithm.

Here's a table that visualizes the multiplications in Strassen's algorithm:

| Product | Multiplication            |
| ------- | ------------------------- |
| P1      | (A11 + A22) × (B11 + B22) |
| P2      | (A21 + A22) × B11         |
| P3      | A11 × (B12 - B22)         |
| P4      | A22 × (B21 - B11)         |
| P5      | (A11 + A12) × B22         |
| P6      | (A21 - A11) × (B11 + B12) |
| P7      | (A12 - A22) × (B21 + B22) |

This table clearly shows the seven products (P1 to P7) and their corresponding multiplications involving the sub-matrices of matrices A and B.

The first column lists the product names (P1, P2, ..., P7), and the second column displays the multiplication operations performed on the sub-matrices.

For example, the first row shows that P1 is calculated by multiplying (A11 + A22) with (B11 + B22), where A11, A22, B11, and B22 are sub-matrices of the input matrices A and B.