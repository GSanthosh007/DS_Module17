# Ex24 Topological Sort
## DATE: 
## AIM:
To compose a Java program to determine whether a topological ordering for a directed graph is possible or not.

## Algorithm
1. Initialize variables:  
   - Declare `topoOrder`, `indeg` arrays and a queue to manage vertices with zero indegree.  

2. Create the graph:  
   - Use a method `createGraph()` to initialize the adjacency matrix or list.  

3. Calculate indegree for each vertex:  
   - For each vertex, compute the indegree.  
   - If indegree is 0, add the vertex to the queue.  

4. Perform topological sorting:  
   - Initialize `count` to 0.  
   - While the queue is not empty:  
     - Remove a vertex from the queue.  
     - Add it to `topoOrder`.  
     - For each neighbor, remove the edge and decrease its indegree.  
     - If indegree becomes 0, enqueue the neighbor.  

5. Check for cycles:  
   - If `count` is less than total number of vertices, the graph contains a cycle and topological ordering is not possible.  

6. Print the topological order:  
   - Display vertices in topological order if no cycle exists.  

7. End the program.

## Program:
```java
/*
Program to determine whether the topological ordering for a graph is possible or not
Developed by: Santhosh G
RegisterNumber: 212223240152
*/

import java.util.*;

public class TopologicalSort {

    static int n = 6; // Example number of vertices
    static int[][] adj = new int[n][n]; // adjacency matrix
    static int[] indeg = new int[n];
    static int[] topoOrder = new int[n];
    static Queue<Integer> queue = new LinkedList<>();

    static void createGraph() {
        // Example edges
        adj[5][2] = 1;
        adj[5][0] = 1;
        adj[4][0] = 1;
        adj[4][1] = 1;
        adj[2][3] = 1;
        adj[3][1] = 1;
    }

    static void calculateIndegree() {
        for (int i = 0; i < n; i++) {
            indeg[i] = 0;
            for (int j = 0; j < n; j++) {
                indeg[i] += adj[j][i];
            }
            if (indeg[i] == 0)
                queue.add(i);
        }
    }

    public static void main(String[] args) {
        createGraph();
        calculateIndegree();

        int count = 0;

        while (!queue.isEmpty()) {
            int v = queue.poll();
            topoOrder[count++] = v;

            for (int i = 0; i < n; i++) {
                if (adj[v][i] == 1) {
                    adj[v][i] = 0;
                    indeg[i]--;
                    if (indeg[i] == 0)
                        queue.add(i);
                }
            }
        }

        if (count < n) {
            System.out.println("No topological ordering possible, graph contains cycle");
        } else {
            System.out.println("Vertices in topological order are:");
            for (int i = 0; i < count; i++)
                System.out.print(topoOrder[i] + " ");
            System.out.println();
        }
    }
}
```
# Output:
<img width="1246" height="575" alt="71f71fcd-87ec-46e4-99d8-847900f991b5" src="https://github.com/user-attachments/assets/a7fd6bf1-d3ed-49d6-8baf-5ab5b2e13ab0" />


# Result:
Thus, the Java program for determining whether a topological ordering for the graph is possible or not is implemented successfully.
