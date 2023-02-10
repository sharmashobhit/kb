### State
A state in a problem represents the summary of the problem at current(or at time t) time.

### Initial State
Starting state of the problem. 

### Action
An action is defined as something that changes the state of the system from A to B.

### Transition Model
`Result(State, Action) => New State`. Effectively, the transition model represents the action and the resultant state after the action is taken on the previous state.

### Goal Test
Goal test represents the final stage of the problem. In a simple case it can be 1 state. for more complicated cases, we can have various goals.

### Path cost function
Cost evaluation function to solve the problem. Can be a factor of money, time or any other resource we're trying to optimize.

### Optimal Solution
A solution that has the lowest path cost among all of the possible solutions.

### Node
A node is a representation of the system at a particular point of time.
- State: 
- Parent
- Action
- Path cost


---
# Search Strategies
## Uninformed search:
Blind BFS/DFS. We navigate just on the algorithm.

## Informed Search
There is some information from the system being shared with the search algo. This is then used to tweak the search algorithm.

#### Greedy BFS:
Only cares about the heurestic. `h(n)`. The heurestic is coded in picking up the next item from the frontier
	
#### A* Algorithm
A* takes Greedy BFS to another level by adding the cost factor as well. `g(n) + h(n)`

---

# Adversarial Algorithms
When there are 2 parties involved working against each other.

#### Minimax algorithm
