---
tags: []
---
## Time Complexity

$$ O(E \log E) $$ 
## Algorithm

The algorithm works by sorting the edges in ascending order of their weights and then iteratively adding edges to the MST  if they don't form a cycle with the previously added edges.

## Visualization

To visualize and remember the steps of Kruskal's algorithm, we can use a table format:

| Step | Edge   | Weight | Included? | Reason                               |
| ---- | ------ | ------ | --------- | ------------------------------------ |
| 1    | (A, B) | 2      | Yes       | First edge                           |
| 2    | (B, C) | 3      | Yes       | Doesn't form a cycle                 |
| 3    | (C, D) | 4      | Yes       | Doesn't form a cycle                 |
| 4    | (A, E) | 5      | Yes       | Doesn't form a cycle                 |
| 5    | (E, F) | 6      | Yes       | Doesn't form a cycle                 |
| 6    | (B, F) | 7      | No        | Forms a cycle with (B, C) and (E, F) |
| 7    | (C, E) | 8      | No        | Forms a cycle with (C, D) and (A, E) |

In this table:

1. The first column represents the step number.
2. The second column lists the edges in ascending order of their weights.
3. The third column shows the weight of each edge.
4. The fourth column indicates whether the edge is included in the MST or not.
5. The fifth column provides the reason for including or excluding the edge.

Here's how the algorithm progresses:

1. The first edge (A, B) with weight 2 is included in the MST as the starting edge.
2. The next edge (B, C) with weight 3 is included because it doesn't form a cycle with the previously added edge.
3. The edge (C, D) with weight 4 is included for the same reason.
4. The edge (A, E) with weight 5 is included as it doesn't form a cycle.
5. The edge (E, F) with weight 6 is included as it doesn't form a cycle.
6. The edge (B, F) with weight 7 is not included because it forms a cycle with the previously added edges (B, C) and (E, F).
7. The edge (C, E) with weight 8 is not included because it forms a cycle with the previously added edges (C, D) and (A, E).

By visualizing the algorithm using this table, you can easily understand the process of selecting edges based on their weights and avoiding cycles to construct the minimum spanning tree.