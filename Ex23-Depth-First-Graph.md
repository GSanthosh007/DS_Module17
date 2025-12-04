# Ex23 Depth First Graph
## DATE:
## AIM:
To compose a Java method `createNode` to construct nodes for depth-first traversal (DFS) of a graph.

## Algorithm
1. **Allocate Memory**: Create a new instance of the Node class.  
2. **Initialize Vertex**: Set the `vertex` field of the new node to the value `v`.  
3. **Initialize Next Pointer**: Set the `next` pointer of the new node to `null`.  
4. **Return Node**: Return the reference to the newly created node.  
5. **End Function**: Complete the method execution.

## Program:
```java
/*
Program to traverse the graph below in the depth first fashion
Developed by: Santhosh G
RegisterNumber: 212223240152
*/

class Node {
    int vertex;
    Node next;

    Node(int v) {
        this.vertex = v;
        this.next = null;
    }
}

public class DFSGraph {

    static Node createNode(int v) {
        return new Node(v);
    }

    public static void main(String[] args) {
        Node node = createNode(1);
        System.out.println("Node created with vertex: " + node.vertex);
    }
}
```

## Output:
<img width="456" height="683" alt="4055623f-4e9c-4730-bbf2-b70ab63e58a4" src="https://github.com/user-attachments/assets/0ad551fd-64a5-47af-a831-f3f895fb1079" />


# Result:
Thus, the Java method createNode for DFS traversal of a graph is implemented successfully.
