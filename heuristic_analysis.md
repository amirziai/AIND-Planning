# Planning Heuristic Analysis

The results are compared based on time complexity, space complexity, and optimality.

### No heuristics
Problem | Algorithm | Expansion | Goals | New_Nodes | Time | Optimal
---- | ---- | ---- | ---- | ---- | ---- | ----
P1 | DFS | 21 | 22 | 85 | 0.02 | False
P1 | BFS | 43 | 56 | 180 | 0.03 | True
P1 | UCS | 55 | 57 | 224 | 0.04 | True
P2 | DFS | 624 | 625 | 5602 | 3.5 | False
P2 | BFS | 3343 | 4609 | 30509 | 13 | True
P2 | UCS | 4840 | 4842 | 43918 | 44 | True
P3 | DFS | 408 | 409 | 3364 | 1.7 | False
P3 | BFS | 14663 | 18098 | 129631 | 97 | True
P3 | UCS | 16963 | 16965 | 149136 | 3.7e+02 | True

Across all problems DFS is the fastest (time complexity) but is not resulting in optimal results. BFS is resulting in less expansions and new nodes relative to UCS and it is faster so it's superior to UCS.

### Using heuristics
Problem | Algorithm | Expansion | Goals | New_Nodes | Time | Optimal
---- | ---- | ---- | ---- | ---- | ---- | ----
P1 | A* with h1 | 55 | 57 | 224 | 0.04 | True
P1 | A* ignore precond | 41 | 43 | 170 | 0.04 | True
P1 | A* pg levelsum | 11 | 13 | 50 | 2.3 | True
P2 | A* ignore precond | 1504 | 1506 | 13800 | 13 | True
P2 | A* with h1 | 4840 | 4842 | 43918 | 42 | True
P2 | A* pg levelsum | 85 | 87 | 831 | 2.8e+02 | True
P3 | A* ignore precond | 4723 | 4725 | 41835 | 84 | True
P3 | A* with h1 | 16963 | 16965 | 149136 | 3.8e+02 | True
P3 | A* pg levelsum | 378 | 380 | 3461 | 1.8e+03 | False



A* with
1. Cost of 1 (uniform)
2. Number of steps ignoring preconditions
3. Level sum using a planning graph
