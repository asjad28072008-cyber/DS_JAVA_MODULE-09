# Ex16 Check for Balanced Parentheses Using Stack
## DATE:
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

<img width="697" height="272" alt="image" src="https://github.com/user-attachments/assets/abc8d597-5921-40c9-a5bd-a1beb771ec93" />


<img width="607" height="192" alt="image" src="https://github.com/user-attachments/assets/0e0c24f6-f532-4b10-b751-d8a87149665e" />


## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
