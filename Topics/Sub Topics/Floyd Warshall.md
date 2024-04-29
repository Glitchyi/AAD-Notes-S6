---
tags:
---
## Time Complexity

$$ O(n^3) $$ 
## Introduction

The Floyd-Warshall algorithm is a fundamental algorithm used in computer science and graph theory for finding the shortest paths between all pairs of nodes in a weighted graph. It can handle both positive and negative edge weights but is not suitable for graphs with negative cycles. The algorithm is named after its developers, Robert Floyd and Stephen Warshall, and is notable for its application of dynamic programming principles.

## Algorithm

Here is the pseudocode for the Floyd-Warshall algorithm:

```pseudo
function FloydWarshall(graph):
    n = number of vertices in the graph
    // Create a matrix to store distances between every pair of vertices
    dist = array[1..n][1..n]

    // Initialize the distance matrix
    for i from 1 to n:
        for j from 1 to n:
            if i == j:
                dist[i][j] = 0
            else if there is an edge from i to j:
                dist[i][j] = weight of the edge from i to j
            else:
                dist[i][j] = infinity

    // Update the distance matrix
    for k from 1 to n: // k is the intermediate vertex
        for i from 1 to n:
            for j from 1 to n:
                if dist[i][j] > dist[i][k] + dist[k][j]:
                    dist[i][j] = dist[i][k] + dist[k][j]

    return dist
```

## Explanation

The Floyd-Warshall algorithm uses a three-dimensional dynamic programming approach to systematically explore all possible paths between each pair of vertices in the graph. The algorithm operates in three nested loops corresponding to the vertices of the graph:

1. **Initialization**: The distance matrix `dist` is initialized such that `dist[i][j]` is set to the weight of the edge between vertices `i` and `j` if it exists, to zero if `i` equals `j`, and to infinity otherwise.

2. **Dynamic Update**: The core of the algorithm involves updating the `dist` matrix to include each vertex `k` as an intermediate point in paths between all pairs of vertices `(i, j)`. For each pair of vertices, the algorithm checks if the direct path from `i` to `j` is longer than the path from `i` to `k` followed by `k` to `j`. If so, it updates `dist[i][j]` to the sum of `dist[i][k]` and `dist[k][j]`.

3. **Result**: After all vertices have been considered as intermediate points, the `dist` matrix contains the lengths of the shortest paths between all pairs of vertices.

This method ensures that the shortest paths are calculated efficiently, with a time complexity of $$O(n^3)$$ and a space complexity of $$O(n^2)$$making it suitable for dense graphs where direct comparisons between all pairs of nodes are feasible