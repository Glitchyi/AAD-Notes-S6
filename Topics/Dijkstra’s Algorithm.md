## Introduction

Dijkstra's algorithm is a well-known method for finding the shortest paths from a single source node to all other nodes in a weighted graph with non-negative edge weights. Developed by Dutch computer scientist Edsger W. Dijkstra in 1956, it is used extensively in routing and as a subroutine in other graph algorithms[1][2].

## Algorithm

Here is the pseudocode for Dijkstra's algorithm:

```pseudo
function Dijkstra(Graph, source):
    dist[] = array of size |V| (number of vertices in the graph) with all values set to INFINITY
    prev[] = array of size |V| with all values set to NULL
    dist[source] = 0
    Q = priority queue containing all nodes in the graph

    while Q is not empty:
        u = vertex in Q with the smallest distance in dist[]
        remove u from Q

        for each neighbor v of u still in Q:
            alt = dist[u] + length(u, v)
            if alt < dist[v]:
                dist[v] = alt
                prev[v] = u

    return dist[], prev[]
```

## Explanation

The algorithm operates by maintaining a priority queue (Q) of vertices whose shortest distance from the source is tentatively known but not yet finalized. It starts by setting the distance to the source node as zero and all other nodes as infinity. The previous node in the optimal path of each node is initially set to null.

The main loop of the algorithm continues until the priority queue is empty. In each iteration, the node (u) with the smallest tentative distance is removed from the queue. The algorithm then considers every unvisited neighbor (v) of u. For each neighbor, it calculates the distance from the source to v through u. If this distance is less than the currently known distance to v, the algorithm updates the distance to v and sets u as the previous node on the path to v.

This process repeats until the priority queue is empty, at which point the array dist[] contains the shortest distances from the source to all other nodes, and the array prev[] can be used to reconstruct the shortest paths. To find the shortest path from the source to a particular vertex, you trace back from that vertex in prev[] until you reach the source