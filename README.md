# Ex-3-Implement-Depth-First-Search-Traversal-of-a-Graph

**Name:Hoshini S**

**Register Number:2305003006**

### Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.

### Theory:

Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. 
The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). 
Use a Boolean visited array to avoid processing a node more than once. 
A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. 
The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking. 

### Algorithm:

Step 1:
Start the program.

Step 2:
Create an empty dictionary graph = {}.

Step 3:
Input the number of nodes n.

Step 4:
For each node, input its name and its comma-separated neighbors.
Store them in the dictionary.

Step 5:
Ask for the starting node for DFS.

Step 6:
Call the dfs(graph, start, visited_list) function.

Step 7:
Inside DFS:

Add the current node to visited.
For each neighbor of the node:
If the neighbor is not visited, recursively call DFS for it.

Step 8:
When no more neighbors are left, return the visited list.

Step 9:
Print the DFS traversal order.

### Program:
```
def dfs(graph, node, visited):
    if node not in visited:
        visited.append(node)
        for neighbor in graph.get(node, []):
            dfs(graph, neighbor, visited)
    return visited

graph = {}
n = int(input("Enter number of nodes: "))

for _ in range(n):
    node = input("Enter node: ").strip()
    neighbors = input(f"Enter neighbors of {node} (comma separated): ").split(",")
    graph[node] = [neighbor.strip() for neighbor in neighbors if neighbor.strip()]

start_node = input("Enter the starting node for DFS: ").strip()

print("DFS Traversal Order:", dfs(graph, start_node, []))

```

### Sample Input:
A B
A C
B D
B E
C E

### Sample Output:

Graph: {'A': ['B', 'C'], 'B': ['A', 'D', 'E'], 'C': ['A', 'E'], 'D': ['B'], 'E': ['B', 'C']}

DFS Traversal Path: ['A', 'B', 'D', 'E', 'C']

### Input:
<img width="442" height="208" alt="image" src="https://github.com/user-attachments/assets/aa79ff43-8875-4b7e-99ac-25bf59a7d7e3" />

### Output:
<img width="413" height="25" alt="image" src="https://github.com/user-attachments/assets/dac04867-f5c3-42ff-9105-8138d40e961c" />


**Result:**

Thus the program to implement depth first search of a traversal graph has been executed successfully.
