# Chapter 4: Search Methods and Heuristic Search

## Overview

Search methods are fundamental to artificial intelligence, providing algorithms to explore possible solutions to problems. This chapter covers systematic search approaches, both uninformed and informed, with a focus on heuristic search methods that utilize problem-specific knowledge.

## 1. Problem-Solving Agents

### Components of Search Problems
A search problem consists of:
1. **Initial State:** The starting point of the problem
2. **Actions:** Available operations that can be applied to states
3. **Transition Model:** How actions change states
4. **Goal Test:** Criteria for determining if a state is a goal
5. **Path Cost:** Function to calculate the cost of a path

### State Space Representation
- **State Space:** The set of all possible states
- **State:** A representation of a situation
- **Solution:** A path from initial state to goal state
- **Optimal Solution:** Solution with lowest path cost

## 2. Uninformed Search Strategies

Uninformed search (or blind search) algorithms use only the problem definition, without any additional information about states beyond the problem definition.

### 2.1 Breadth-First Search (BFS)
**Characteristics:**
- Explores nodes level by level
- Uses a FIFO (queue) data structure
- Complete and optimal for uniform cost problems

**Algorithm:**
```
1. Add initial state to queue
2. While queue is not empty:
   a. Remove first node from queue
   b. If goal, return solution
   c. Add all children to end of queue
```

**Complexity:**
- Time: O(b^d) where b is branching factor, d is depth
- Space: O(b^d) - high space requirement
- Complete: Yes (if b is finite)
- Optimal: Yes (if path cost is non-decreasing function of depth)

### 2.2 Depth-First Search (DFS)
**Characteristics:**
- Explores as far as possible along each branch
- Uses a LIFO (stack) data structure
- Complete but not optimal

**Algorithm:**
```
1. Add initial state to stack
2. While stack is not empty:
   a. Remove top node from stack
   b. If goal, return solution
   c. Add all children to top of stack
```

**Complexity:**
- Time: O(b^m) where m is maximum depth
- Space: O(bm) - much more space efficient than BFS
- Complete: No (infinite depth spaces)
- Optimal: No

### 2.3 Depth-Limited Search
DFS with a depth limit: l

### 2.4 Iterative Deepening Search (IDS)
Combine benefits of DFS and BFS by gradually increasing depth limits.

**Advantages:**
- Space complexity of DFS
- Completeness of BFS
- Optimality when step cost is 1

**Time Complexity:** O(b^d)
**Space Complexity:** O(bd)

### 2.5 Uniform Cost Search (UCS)
Expands nodes based on path cost instead of depth.

**Algorithm:**
- Uses priority queue ordered by path cost
- Equivalent to BFS when all step costs are equal

## 3. Informed Search Strategies

Informed search (or heuristic search) uses problem-specific knowledge to find solutions more efficiently.

### 3.1 Heuristic Functions
A heuristic function h(n) estimates the cost of the cheapest path from node n to a goal node.

**Admissible Heuristic:** Never overestimates the actual cost (optimistic).
**Consistent Heuristic:** For every node n and successor n' with step cost c, h(n) ≤ c(n,n') + h(n').

### 3.2 Greedy Best-First Search
Tries to expand the node that appears to be closest to the goal.

**Evaluation function:** f(n) = h(n) (heuristic only)

### 3.3 A* Search
Combines uniform-cost search and greedy best-first search.

**Evaluation function:** f(n) = g(n) + h(n)
- g(n) = cost from start to n
- h(n) = heuristic estimate from n to goal

**Characteristics:**
- Complete: Yes (if b is finite and h(n) is bounded)
- Optimal: Yes (if h(n) is admissible)
- Time/Space: Depends on quality of heuristic

**Properties of A*:**
- A* is optimally efficient: No other tree-search algorithm that is admissible will expand fewer nodes than A* with the same heuristic.
- If h(n) = h*(n), A* runs in linear time

## 4. Constraint Satisfaction Problems (CSPs)

### CSP Definition
A CSP consists of:
- A set of variables (X1, X2, ..., Xn)
- A set of domains (D1, D2, ..., Dn) for each variable
- A set of constraints that specify allowable values

**Example:** Map coloring, N-Queens, Sudoku

### CSP Solving Methods
1. **Backtracking Search:** Systematic approach with backtracking when constraints are violated
2. **Forward Checking:** Prevent assignments that conflict with current assignments
3. **Constraint Propagation:** Reduces domain sizes using constraint information

### Local Search Methods
For optimization problems where path to goal doesn't matter.

#### Hill Climbing
- Local search algorithm that moves toward increasing value
- Problems: Local maxima, ridges, plateaux

#### Simulated Annealing
- Allows some "bad" moves to escape local maxima
- Temperature parameter controls acceptance of bad moves

#### Genetic Algorithms
- Maintains population of states
- Uses selection, crossover, and mutation operators

## 5. Adversarial Search

### Game Playing
Two-player games with alternating moves and well-defined rules.

### Minimax Algorithm
Optimal algorithm for deterministic, turn-taking, zero-sum games.

**Algorithm:**
- MAX (our side) wants to maximize utility
- MIN (opponent) wants to minimize utility
- Alternates between MAX and MIN levels

**Pseudocode:**
```
function MINIMAX-DECISION(state) returns an action
   return argmax MIN-VALUE(RESULT(state, a))
   
function MAX-VALUE(state) returns a utility value
   if TERMINAL-TEST(state) then return UTILITY(state)
   v ← -∞
   for each a in ACTIONS(state) do
      v ← MAX(v, MIN-VALUE(RESULT(state, a)))
   return v
   
function MIN-VALUE(state) returns a utility value
   if TERMINAL-TEST(state) then return UTILITY(state)
   v ← +∞
   for each a in ACTIONS(state) do
      v ← MIN(v, MAX-VALUE(RESULT(state, a)))
   return v
```

### Alpha-Beta Pruning
Way to improve minimax efficiency by pruning branches that won't affect final decision.

- α (alpha): Best value found so far at any choice point along the path for MAX
- β (beta): Best value found so far at any choice point along the path for MIN

## 6. Heuristic Function Design

### Key Principles
1. **Admissibility:** Never overestimate actual cost
2. **Dominance:** h2 dominates h1 if h2(n) ≥ h1(n) for all n
3. **Relaxed Problems:** Remove constraints to get admissible heuristic
4. **Pattern Databases:** Precompute exact costs to goal for subproblems

### Common Examples
**8-Puzzle Problem:**
1. **Misplaced tiles heuristic:** Count number of tiles in wrong position
2. **Manhattan distance:** Sum of distances of tiles from their goal positions

## 7. Search Strategy Comparison

| Algorithm | Complete? | Optimal? | Time | Space |
|-----------|-----------|----------|------|-------|
| BFS | Yes* | Yes* | O(b^d) | O(b^d) |
| DFS | No | No | O(b^m) | O(bm) |
| IDS | Yes* | Yes* | O(b^d) | O(bd) |
| UCS | Yes* | Yes | O(b^C*/ε) | O(b^C*/ε) |
| Greedy | No | No | O(b^m) | O(b^m) |
| A* | Yes* | Yes* | O(b^d) | O(b^d) |

*If finite state space and redundant paths are eliminated

## Practice Problems and Solutions

### Problem 1: Search Space Analysis
**Question:** Consider a search space with branching factor b=3 and goal at depth d=4. Calculate the maximum number of nodes generated by BFS before finding the solution.

**Solution:**
BFS explores nodes level by level.
- Level 0: 1 node (root)
- Level 1: 3 nodes
- Level 2: 3² = 9 nodes
- Level 3: 3³ = 27 nodes
- Level 4: 3⁴ = 81 nodes (goal is here)

Total nodes = 1 + 3 + 9 + 27 + 81 = 121 nodes

### Problem 2: A* Algorithm
**Question:** In an A* search, if g(n) = 10 and h(n) = 5, what is f(n)?

**Solution:**
f(n) = g(n) + h(n) = 10 + 5 = 15

### Problem 3: Heuristic Admissibility
**Question:** In a pathfinding problem on a grid, Manhattan distance is used as a heuristic. Is this admissible? Why?

**Solution:**
Yes, Manhattan distance is admissible because it never overestimates the actual cost:
- It assumes movement only horizontally and vertically
- Actual path cost will always be ≥ Manhattan distance (diagonal movement would be more efficient)
- Since it's an underestimate (or equal in the best case), it's admissible

### Problem 4: Minimax Evaluation
**Question:** Consider a game tree where MAX has 3 possible moves, and for each move, MIN has 2 responses. If the terminal values are [5, 3, 6, 2, 8, 1], what move should MAX choose?

**Solution:**
MIN chooses minimum at each level:
- After move 1: MIN chooses min(5, 3) = 3
- After move 2: MIN chooses min(6, 2) = 2
- After move 3: MIN chooses min(8, 1) = 1

MAX chooses maximum: max(3, 2, 1) = 3
MAX should choose move 1.

### Problem 5: Search Strategy Selection
**Question:** For a problem with large branching factor but shallow solutions, which search strategy would be most appropriate and why?

**Solution:** Iterative Deepening Search (IDS) would be most appropriate because:
- It has the space efficiency of DFS (O(bd) space)
- It has the completeness of BFS
- It guarantees finding the shallowest solution (optimal for uniform cost)
- Even though it repeats work, the overhead is acceptable when solutions are shallow
- It avoids the space complexity of BFS which becomes prohibitive with large branching factors

## Key Takeaways

- Uninformed search methods explore systematically without problem-specific knowledge
- Informed (heuristic) search methods use problem-specific knowledge to guide search
- A* is optimal when using an admissible heuristic
- Different search strategies have different time/space/optimality trade-offs
- Admissible heuristics never overestimate actual cost
- Game playing uses adversarial search with minimax and alpha-beta pruning

## Additional Practice Problems

### Advanced Problem 1: Heuristic Admissibility
**Question:** For the 8-puzzle, which is more admissible: Manhattan distance or number of misplaced tiles? Explain.

**Solution:** 
Both are admissible, but Manhattan distance is more informed (dominant) because it accounts for the distance each tile must move, not just whether it's in the correct position. Since Manhattan distance never overestimates the actual cost and provides better estimates, it will typically expand fewer nodes than misplaced tiles heuristic.

### Advanced Problem 2: A* vs Greedy Search
**Question:** For what types of problems would you prefer A* over greedy best-first search?

**Solution:**
A* is preferred when:
- Solution optimality is required
- The heuristic is admissible
- The path cost is important
- You need guaranteed completeness
Greedy search might be preferred when only speed matters and optimality is not required, though it may not find the optimal solution or even complete solution in some cases.