# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE:
## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.
## Algorithm
1. Define a Node class containing customer details (such as Name or Ticket ID) and a reference pointer (next) to the next customer in the queue.
2. Initialize a Queue class with two pointers, front and rear, both initially set to null to represent an empty ticket counter line.
3. Implement the Enqueue operation to add a customer to the back of the line. Create a new node; if the queue is empty, set both front and rear to this node. Otherwise, point rear.next to the new node and update rear to the new node.
4. Implement the Dequeue operation to serve the customer at the front of the line. If the queue is empty, display an underflow message. Otherwise, advance the front pointer to front.next and free or return the served customer details. If front becomes null, set rear to null.
5. Create a main driver menu using a loop to simulate the ticket counter. Allow users to choose from operations like adding a customer (Enqueue), serving a customer (Dequeue), displaying the current line, or exiting the simulation.
 

## Program:
```
/*
Program to functioning of a ticket counter that operates on a First-In-First-Out (FIFO)
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.Scanner;

// Rename your file to CustomerNode.java if using this structure
public class CustomerNode {
    String customerName;
    int ticketId;
    CustomerNode next;

    public CustomerNode(String customerName, int ticketId) {
        this.customerName = customerName;
        this.ticketId = ticketId;
        this.next = null;
    }

    // Main method added directly here so Java can find it instantly
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        TicketCounterQueue counter = new TicketCounterQueue();
        int choice;
        int idCounter = 101; 

        System.out.println("=== Ticket Counter Simulation ===");
        
        do {
            System.out.println("\n1. Customer Joins Line (Enqueue)");
            System.out.println("2. Serve Next Customer (Dequeue)");
            System.out.println("3. Display Waiting Line");
            System.out.println("4. Exit Simulation");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();
            scanner.nextLine(); 

            switch (choice) {
                case 1:
                    System.out.print("Enter Customer Name: ");
                    String name = scanner.nextLine();
                    counter.enqueue(name, idCounter++);
                    break;
                case 2:
                    counter.dequeue();
                    break;
                case 3:
                    counter.displayQueue();
                    break;
                case 4:
                    System.out.println("Exiting Ticket Counter Simulation. Thank you!");
                    break;
                default:
                    System.out.println("Invalid choice! Please try again.");
            }
        } while (choice != 4);

        scanner.close();
    }
}

// Internal Queue Helper Class
class TicketCounterQueue {
    private CustomerNode front, rear;

    public TicketCounterQueue() {
        this.front = null;
        this.rear = null;
    }

    public void enqueue(String name, int id) {
        CustomerNode newNode = new CustomerNode(name, id);
        if (this.rear == null) {
            this.front = newNode;
            this.rear = newNode;
            System.out.println("Customer " + name + " (ID: " + id + ") joined the line.");
            return;
        }
        this.rear.next = newNode;
        this.rear = newNode;
        System.out.println("Customer " + name + " (ID: " + id + ") joined the line.");
    }

    public void dequeue() {
        if (this.front == null) {
            System.out.println("Ticket counter line is empty! No customers to serve.");
            return;
        }
        CustomerNode temp = this.front;
        this.front = this.front.next;
        if (this.front == null) {
            this.rear = null;
        }
        System.out.println("Served Customer: " + temp.customerName + " (Ticket ID: " + temp.ticketId + ")");
    }

    public void displayQueue() {
        if (this.front == null) {
            System.out.println("No one is currently waiting in line.");
            return;
        }
        System.out.print("Current Line: ");
        CustomerNode current = front;
        while (current != null) {
            System.out.print("[" + current.customerName + ", ID: " + current.ticketId + "] -> ");
            current = current.next;
        }
        System.out.println("NULL");
    }
}

```
## Output:


<img width="161" height="342" alt="image" src="https://github.com/user-attachments/assets/8c2f320b-55ab-4b29-a77d-66b85c0b6f5d" />



## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
