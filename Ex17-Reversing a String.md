# Ex17 Reversing a String Using Stack Data Structure
## DATE:
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm
1. Start the program and read the input string from the user.
2. Create and initialize an empty stack to store characters.
3. Iterate through each character of the input string from index 0 to length-1 and push each character onto the stack.
4. Pop characters from the stack one by one and append them to a new string builder until the stack becomes empty.
5. Display the reversed string as the final output and terminate the program.


## Program:
```
/*
Program to reverses an input string using a stack
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.Scanner;
import java.util.Stack;

public class StringReversal {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Read input string from the user
        System.out.print("Enter a string to reverse: ");
        String input = scanner.nextLine();
        
        // Initialize a stack of characters
        Stack<Character> stack = new Stack<>();
        
        // Step 1: Push all characters of the string into the stack
        for (int i = 0; i < input.length(); i++) {
            stack.push(input.charAt(i));
        }
        
        // Step 2: Pop characters from the stack to reverse the string
        StringBuilder reversedString = new StringBuilder();
        while (!stack.isEmpty()) {
            reversedString.append(stack.pop());
        }
        
        // Output the result
        System.out.println("Reversed string: " + reversedString.toString());
        
        scanner.close();
    }
}

```

## Output:

<img width="640" height="255" alt="image" src="https://github.com/user-attachments/assets/79c30421-7ba0-42d4-b904-e8dca0250143" />



## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
