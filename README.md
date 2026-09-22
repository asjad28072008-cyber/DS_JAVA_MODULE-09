# Ex16 Check for Balanced Parentheses Using Stack
## DATE: 08.09.2026
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Initialize an empty stack to store opening brackets.
2. Iterate through each character of the input string from left to right.
3. Push the character onto the stack if it is an opening bracket (, {, or [.Pop the top element from the stack if a closing bracket ), }, or ] is encountered, and check if it matches the corresponding opening bracket.
4. If the stack is empty or they do not match, the expression is unbalanced (return false).
5. Verify if the stack is completely empty after checking all characters. If empty, return true (balanced); otherwise, return false (unbalanced).


## Program:
```
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```

import java.util.Stack;
import java.util.Scanner;

public class BalancedParentheses {

    public static boolean isBalanced(String expr) {
        // Step 1: Initialize the stack
        Stack<Character> stack = new Stack<>();

        // Step 2: Iterate through the string
        for (int i = 0; i < expr.length(); i++) {
            char ch = expr.charAt(i);

            // Step 3: Push opening brackets
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
                continue;
            }

            // Step 4: Check closing brackets
            if (ch == ')' || ch == '}' || ch == ']') {
                // If stack is empty, there is no matching opening bracket
                if (stack.isEmpty()) {
                    return false;
                }

                char check = stack.pop();
                switch (ch) {
                    case ')':
                        if (check != '(') return false;
                        break;
                    case '}':
                        if (check != '{') return false;
                        break;
                    case ']':
                        if (check != '[') return false;
                        break;
                }
            }
        }

        // Step 5: Check if stack is empty
        return stack.isEmpty();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter an expression: ");
        String expression = scanner.nextLine();

        if (isBalanced(expression)) {
            System.out.println("The parentheses are Balanced.");
        } else {
            System.out.println("The parentheses are Not Balanced.");
        }
        
        scanner.close();
    }
}

```

## Output:

<img width="457" height="253" alt="image" src="https://github.com/user-attachments/assets/a3f870d8-89a8-4b43-9e42-9bea0d1f9a91" />




## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.





















# Ex16 Check for Balanced Parentheses Using Stack
## DATE: 08.09.2026
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Initialize an empty stack to store opening brackets.
2. Iterate through each character of the input string from left to right.
3. Push the character onto the stack if it is an opening bracket (, {, or [.Pop the top element from the stack if a closing bracket ), }, or ] is encountered, and check if it matches the corresponding opening bracket.
4. If the stack is empty or they do not match, the expression is unbalanced (return false).
5. Verify if the stack is completely empty after checking all characters. If empty, return true (balanced); otherwise, return false (unbalanced).


## Program:
```
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```

import java.util.Stack;
import java.util.Scanner;

public class BalancedParentheses {

    public static boolean isBalanced(String expr) {
        // Step 1: Initialize the stack
        Stack<Character> stack = new Stack<>();

        // Step 2: Iterate through the string
        for (int i = 0; i < expr.length(); i++) {
            char ch = expr.charAt(i);

            // Step 3: Push opening brackets
            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
                continue;
            }

            // Step 4: Check closing brackets
            if (ch == ')' || ch == '}' || ch == ']') {
                // If stack is empty, there is no matching opening bracket
                if (stack.isEmpty()) {
                    return false;
                }

                char check = stack.pop();
                switch (ch) {
                    case ')':
                        if (check != '(') return false;
                        break;
                    case '}':
                        if (check != '{') return false;
                        break;
                    case ']':
                        if (check != '[') return false;
                        break;
                }
            }
        }

        // Step 5: Check if stack is empty
        return stack.isEmpty();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter an expression: ");
        String expression = scanner.nextLine();

        if (isBalanced(expression)) {
            System.out.println("The parentheses are Balanced.");
        } else {
            System.out.println("The parentheses are Not Balanced.");
        }
        
        scanner.close();
    }
}

```

## Output:

<img width="457" height="253" alt="image" src="https://github.com/user-attachments/assets/a3f870d8-89a8-4b43-9e42-9bea0d1f9a91" />




## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.



















# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE: 08.09.2026
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


<img width="1105" height="717" alt="image" src="https://github.com/user-attachments/assets/167c9f7c-daf5-48c0-b502-f617ec1bcd44" />




## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.

























# Ex19 Palindrome Check Using Deque
## DATE: 08.09.2026
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm
1. Input: Read the input string (message) from the user.
2. Preprocess: Filter out all non-alphanumeric characters and convert the remaining characters to lowercase.
3. Initialize Deque: Insert each character of the preprocessed string into a double-ended queue (deque).
4. Compare Characters: Repeatedly remove and compare characters from both the front and rear of the deque simultaneously while the deque size is greater than 1.
5. Output: If a mismatch is found, terminate and declare it is not a palindrome. If the deque becomes empty or has one character left with all matches successful, declare it is a palindrome.
 

## Program:
```
/*
Program to checks whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.ArrayDeque;
import java.util.Deque;
import java.util.Scanner;

public class PalindromeCheck {

    public static boolean isPalindrome(String message) {
        // Step 1: Initialize a deque for characters
        Deque<Character> deque = new ArrayDeque<>();

        // Step 2: Clean the input (keep alphanumeric only and lowercase)
        for (int i = 0; i < message.length(); i++) {
            char ch = message.charAt(i);
            if (Character.isLetterOrDigit(ch)) {
                deque.addLast(Character.toLowerCase(ch));
            }
        }

        // Step 3: Compare characters from both ends
        while (deque.size() > 1) {
            char front = deque.removeFirst();
            char rear = deque.removeLast();

            if (front != rear) {
                return false; // Character mismatch
            }
        }

        return true; // Passed all checks
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Step 4: Get input from the user
        System.out.print("Enter a message to check: ");
        String userInput = scanner.nextLine();

        // Step 5: Check and print results
        if (isPalindrome(userInput)) {
            System.out.println("Result: The message IS a palindrome.");
        } else {
            System.out.println("Result: The message IS NOT a palindrome.");
        }

        scanner.close();
    }
}

```

## Output:



<img width="472" height="242" alt="image" src="https://github.com/user-attachments/assets/67a63694-6f9c-412d-9083-80509dd146c2" />


## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.






















# Ex20 Sorting an Array using Merge Sort Algorithm
## DATE: 08.09.2026
## AIM:
To design a program that sorts a given array of integers in ascending order without using built-in sorting functions, achieving O(n log n) time complexity and minimal space usage.
## Algorithm
1. Find the midpoint of the array to divide it into two halves: a left subarray and a right subarray.
2. Recursively sort the left subarray by repeatedly calling the merge sort function until subarrays of size 1 are reached.
3. Recursively sort the right subarray in the same manner until subarrays of size 1 are reached.
4. Merge the two sorted subarrays back together by comparing elements from each side and placing them in ascending order into a temporary array.
5. Copy the sorted elements from the temporary array back into the original array to complete the sorting process.
 

## Program:
```
/*
Program tosorts a given array of integers in ascending order without using built-in sorting functions
RegisterNumber:  212225240091
*/
```

```
import java.util.Scanner;

public class MergeSort {

    // Main function that sorts array[left...right] using merge()
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            // Find the middle point
            int mid = left + (right - left) / 2;

            // Sort first and second halves
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            // Merge the sorted halves
            merge(arr, left, mid, right);
        }
    }

    // Merges two subarrays of arr[].
    // First subarray is arr[left..mid]
    // Second subarray is arr[mid+1..right]
    public static void merge(int[] arr, int left, int mid, int right) {
        // Find sizes of two subarrays to be merged
        int n1 = mid - left + 1;
        int n2 = right - mid;

        // Create temporary arrays
        int[] leftArr = new int[n1];
        int[] rightArr = new int[n2];

        // Copy data to temporary arrays
        for (int i = 0; i < n1; ++i) {
            leftArr[i] = arr[left + i];
        }
        for (int j = 0; j < n2; ++j) {
            rightArr[j] = arr[mid + 1 + j];
        }

        // Merge the temporary arrays back into arr[left..right]
        int i = 0, j = 0;
        int k = left; // Initial index of merged subarray

        while (i < n1 && j < n2) {
            if (leftArr[i] <= rightArr[j]) {
                arr[k] = leftArr[i];
                i++;
            } else {
                arr[k] = rightArr[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements of leftArr[] if any
        while (i < n1) {
            arr[k] = leftArr[i];
            i++;
            k++;
        }

        // Copy remaining elements of rightArr[] if any
        while (j < n2) {
            arr[k] = rightArr[j];
            j++;
            k++;
        }
    }

    // Utility function to print the array
    public static void printArray(int[] arr) {
        for (int val : arr) {
            System.out.print(val + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Take array size from user
        System.out.print("Enter the number of elements: ");
        int n = scanner.nextInt();

        int[] arr = new int[n];

        // Take array elements from user
        System.out.println("Enter " + n + " integers:");
        for (int i = 0; i < n; i++) {
            arr[i] = scanner.nextInt();
        }

        System.out.println("\nGiven Array:");
        printArray(arr);

        // Call mergeSort on the entire array
        mergeSort(arr, 0, arr.length - 1);

        System.out.println("\nSorted Array:");
        printArray(arr);

        scanner.close();
    }
}

```

## Output:


<img width="672" height="276" alt="image" src="https://github.com/user-attachments/assets/a6603e36-4b2c-41a0-bccf-0f2ac5f0f083" />


## Result:
The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
