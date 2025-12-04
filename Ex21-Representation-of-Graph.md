# Ex21 Representation of Graph
## DATE:
## AIM:
To write a Java program to display the adjacency matrix of a graph using the given edges and number of vertices.

## Algorithm
1. Start  
2. Read the number of vertices V.  
3. Declare an adjacency matrix `adjMatrix[V][V]`.  
4. Initialize all elements of the matrix to 0.  
5. Calculate the maximum number of edges as `V * (V - 1) / 2`.  
6. For each edge, read the vertices `e1` and `e2` and update the adjacency matrix. Stop if `e1 == -1 && e2 == -1`.  
7. Print the adjacency matrix.  
8. End.

## Program:
```java
/*
Program to display the adjacency matrix of the given graph.
Developed by: Santhosh G
RegisterNumber: 212223240152
*/

import java.util.Scanner;

public class GraphRepresentation {

    static void init(int[][] arr) {
        for (int i = 0; i < arr.length; i++)
            for (int j = 0; j < arr.length; j++)
                arr[i][j] = 0;
    }

    static void addEdge(int[][] adjMatrix, int u, int v) {
        adjMatrix[u][v] = 1;
        adjMatrix[v][u] = 1; // For undirected graph
    }

    static void printAdjMatrix(int[][] adjMatrix) {
        for (int i = 0; i < adjMatrix.length; i++) {
            for (int j = 0; j < adjMatrix.length; j++) {
                System.out.print(adjMatrix[i][j] + " ");
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int V = sc.nextInt();
        int[][] adjMatrix = new int[V][V];

        init(adjMatrix);

        int me = V * (V - 1) / 2;
        for (int i = 0; i < me; i++) {
            int e1 = sc.nextInt();
            int e2 = sc.nextInt();
            if (e1 == -1 && e2 == -1)
                break;
            addEdge(adjMatrix, e1, e2);
        }

        printAdjMatrix(adjMatrix);
        sc.close();
    }
}

```
# Output:
<img width="1149" height="475" alt="9cafac08-59cc-412e-8e7d-b5b77ff8023a" src="https://github.com/user-attachments/assets/32ca454a-8875-4e5c-b05b-4c03b3ad47f5" />


# Result:
Thus, the Java program to print the adjacency matrix of the given graph is implemented successfully.
