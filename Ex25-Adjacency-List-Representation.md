# Ex25 Adjacency List Representation
## DATE:
## AIM:
To write a Java program to represent a given graph using an adjacency list.

## Algorithm
1. Initialize variables:  
   - Declare `V` (number of vertices) and `edges` list.  

2. Read the number of vertices and edges:  
   - Assign values to `V` and number of edges.  

3. Input edges of the graph:  
   - Create an `Edge` class with `src` and `dest`.  
   - For each edge, read `src` and `dest`.  

4. Construct the graph:  
   - Create a `Graph` class containing an array of `LinkedList<Integer>` for adjacency lists.  
   - For each edge, add `dest` to the adjacency list of `src`.  

5. Print the graph:  
   - Iterate through each vertex and print its adjacency list.  

6. End the program.

## Program:
```java
/*
Program to represent the given graph using adjacency list
Developed by: Santhosh G
RegisterNumber: 212223240152
*/

import java.util.*;

class Edge {
    int src, dest;
    Edge(int s, int d) {
        src = s;
        dest = d;
    }
}

class Graph {
    int V;
    LinkedList<Integer>[] adjList;

    Graph(int V) {
        this.V = V;
        adjList = new LinkedList[V];
        for(int i = 0; i < V; i++)
            adjList[i] = new LinkedList<>();
    }

    void addEdge(int src, int dest) {
        adjList[src].add(dest);
    }

    void printGraph() {
        for(int i = 0; i < V; i++) {
            System.out.print("Vertex " + i + ":");
            for(Integer v : adjList[i])
                System.out.print(" " + v);
            System.out.println();
        }
    }
}

public class AdjacencyListGraph {
    public static void main(String[] args) {
        int N = 5; // number of vertices
        Edge[] edges = {
            new Edge(0, 1),
            new Edge(0, 4),
            new Edge(1, 2),
            new Edge(1, 3),
            new Edge(1, 4),
            new Edge(2, 3),
            new Edge(3, 4)
        };

        Graph graph = new Graph(N);

        for(Edge e : edges)
            graph.addEdge(e.src, e.dest);

        graph.printGraph();
    }
}
```
# Output:
<img width="523" height="597" alt="36c3bb99-6a63-449e-9ab7-ff85c5774791" src="https://github.com/user-attachments/assets/285d6565-fa1f-4ea5-b429-10116afe6ac0" />


# Result:
Thus, the Java program to represent the given graph using an adjacency list is implemented successfully.
