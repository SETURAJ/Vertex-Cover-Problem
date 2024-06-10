# Vertex-Cover-Problem

This repository demonstrates the Vertex Cover Problem project. 🐱 

## Overview

The identification of a minimum vertex cover within a graph is a well-established problem
in computer science, characterized by its status as a paradigmatic example of an
NP-hard optimization challenge. The minimum vertex cover can be used to determine the fewest number of cameras needed to monitor city traffic effectively.

❗The code cannot be shared due to integrity!!

## Methodology

A polynomial time reduction from the VERTEXCOVER
problem to CNF-SAT was deployed. A polynomial time reduction is an algorithm that operates
in time polynomial in its input size. Here’s an overview of the process:
Reduction Process: We transform the given instance of the VERTEX-COVER problem
into an equivalent instance of the CNF-SAT problem, ensuring that a solution to the
CNF-SAT problem corresponds to a solution for the original VERTEX-COVER problem.
Minisat SAT Solver: Following the reduction, we utilize a Minisat SAT solver to efficiently
determine a satisfying assignment for the CNF-SAT problem, which, in turn,
provides a solution to the original VERTEX-COVER problem.


## Optimization
We employed binary search optimization to determine the minimum vertex cover value
(k) in our algorithm. This application significantly reduced the search time for CNF-SAT
by eliminating numerous false minimum possibilities of vertex cover size. Initially, the
code performed effectively for vertices up to 15, producing outputs in under a minute.
However, as we extended its application to higher vertices (e.g., 20, 25), we observed a
substantial increase in execution time. For instance, the algorithm ran for approximately
6 minutes for 20 vertices and 45 minutes for 25 vertices, prompting us to terminate
execution for higher vertex values due to excessive runtimes.

The primary cause of this performance degradation lies in the third constraint, which
generates an extensive number of clauses. This constraint operates in exponential time,
and the overall time efficiency of the CNF-SAT algorithm is inherently exponential.
While the Vertex Cover problem is NP-complete and cannot be solved in polynomial
time, we sought to enhance the efficiency of CNF-SAT by devising a more intelligent
and efficient encoding strategy.

To address this issue, we introduced modifications to the CNF-SAT algorithm to optimize its performance. The Minisat Solver, in its attempt to find a solution for all possibilities,
explores permutations of the vertex cover size. We recognized that the correctness of
certain permutations could be determined by the correctness of others, allowing us to
streamline the search process.




