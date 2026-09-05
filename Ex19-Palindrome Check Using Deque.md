# Ex19 Palindrome Check Using Deque
## DATE:
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

<img width="595" height="226" alt="image" src="https://github.com/user-attachments/assets/1aefdc9d-089e-4b0b-b0e4-53731671c860" />



<img width="580" height="202" alt="image" src="https://github.com/user-attachments/assets/1820e55b-3449-49b2-a0a6-9807437db7bd" />


## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
