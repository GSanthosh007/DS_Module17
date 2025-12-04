# Ex22 Breadth First Graph
## DATE: 
## AIM:
To write a Java method to display the contents of a queue for Breadth-First Traversal (BFS) of a graph.

## Algorithm
1. Check if the queue is empty using `isEmpty()`. If true, print "Queue is empty".  
2. If not empty, print "Queue contains ".  
3. Initialize an index variable to the front of the queue.  
4. Iterate from front to rear of the queue, printing each element.  
5. End after printing all elements.

## Program:
```java
/*
Program to traverse graph using BFS
Developed by: Santhosh G
RegisterNumber: 212223240152
*/

class Queue {
    int front, rear, size;
    int capacity;
    int[] items;

    Queue(int capacity) {
        this.capacity = capacity;
        front = 0;
        rear = -1;
        size = 0;
        items = new int[capacity];
    }

    boolean isEmpty() {
        return size == 0;
    }

    void enqueue(int item) {
        if (size == capacity) return;
        rear = (rear + 1) % capacity;
        items[rear] = item;
        size++;
    }

    int dequeue() {
        if (isEmpty()) return -1;
        int item = items[front];
        front = (front + 1) % capacity;
        size--;
        return item;
    }

    void printQueue() {
        if (isEmpty()) {
            System.out.println("Queue is empty");
        } else {
            System.out.print("Queue contains ");
            for (int i = 0; i < size; i++) {
                System.out.print(items[(front + i) % capacity] + " ");
            }
            System.out.println();
        }
    }
}

public class BFSGraph {
    public static void main(String[] args) {
        Queue q = new Queue(10);
        q.enqueue(1);
        q.enqueue(2);
        q.enqueue(3);

        q.printQueue(); // Display queue contents
    }
}
```

# Output:
<img width="786" height="418" alt="2b138084-4d39-4b8a-ad86-c5eddfe57997" src="https://github.com/user-attachments/assets/456fc8ff-e28b-41bc-af55-3c8ed072d86b" />


# Result:
Thus, the Java method to print the queue contents for BFS traversal of a graph is implemented successfully.
