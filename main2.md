# Check isPrime

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <stdbool.h>

bool isPrime(int n){
    if (n<=1) return false;
    if (n<=3) return true;
    
    if (n%2==0 || n%3==0) return false;
    
    for(int i=5; i*i<= n ; i+=6){
        if(n%i==0 || n % (i + 2) == 0){
            return false;
        }
    }
            return true;
}

int main() {
    int n = 100;
    
    if(isPrime(n)){
        printf("Yes");
    }else{
        printf("no");
    }
    return 0;
}
```


# Balanced paranthesis

```c
#include <stdio.h>
#include <stdbool.h>

#define MAX 100

// Function to check if the string has balanced parentheses
bool isValid(char* s) {
    char stack[MAX];
    int top = -1; // Stack pointer

    for (int i = 0; s[i] != '\0'; i++) {
        char current = s[i];

        // Push opening brackets onto the stack
        if (current == '(' || current == '{' || current == '[') {
            stack[++top] = current;
        }
        // For closing brackets, check if it matches the top of the stack
        else if (current == ')' || current == '}' || current == ']') {
            if (top == -1) return false; // Stack is empty, no matching opening bracket
            char topChar = stack[top--];
            if ((current == ')' && topChar != '(') ||
                (current == '}' && topChar != '{') ||
                (current == ']' && topChar != '[')) {
                return false; // Mismatched brackets
            }
        }
    }

    // If stack is empty, all brackets are matched correctly
    return top == -1;
}

int main() {
    char s[100];
    printf("Enter the string: ");
    scanf("%s", s);

    if (isValid(s)) {
        printf("True\n");  // The string is valid
    } else {
        printf("False\n"); // The string is not valid
    }

    return 0;
}
```
