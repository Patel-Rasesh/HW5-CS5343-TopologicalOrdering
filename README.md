# Sorting algorithm for interdependent tasks
Consider a task A which is dependent on tasks B and C - accompanying notation is (A -> B, C),
and task B is dependent on tasks X and Y - (B -> X, Y).
If we were to run A, we need to perform and complete X and Y first. To figure out such interdependency, we use this topological sorting algorithmm which is presented here.

## TopologicalOrdering
This repository covers Breadth-First Search (BFS) and Depth First Search (DFS) for Topological Ordering or sorting. I will cover it for predetermined directed graphs.

###### Briefly explaining how each of the approach works - 
# Breadth-First Search (BFS)
Since at the beginning we are concentrating on a node and its neighbors (therefore Breadth-First search), we will sequentially consider each node with smallest in-degree (or predecessor count).
###### Definition : In-degree of a node is a count of incoming edges to that node.
Steps - 
1. Start with a node that has 0 in-degree.
2. Add that node to the final sorted queue.
3. Recompute in-degree for each node.
4. Repeat step 1.
5. If no node with 0 in-degree is found, a cycle is detected in your directed graph.
6. Return the queue.

# Depth-First Search (DFS)
While our objective of sorting a graph is same as before, in this technique we are maintaining two flags (boolean variables) - visited and done.
When a node is visited, its respective Visited flag is marked as True (or 1).
When a node is visited and executed, its respective Done flag is marked as True.
###### Note - A node can only be executed either when its children are in completed or it has no child.
Depth implies that we will continue following one path at a time.

In the code, instead of maintaining two separate flags, I have maintained a hashtable. Each key (node) can one of two values - 1 (Visited) or 2 (Done).
