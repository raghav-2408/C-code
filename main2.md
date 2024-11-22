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


# String permutations

```c
#include <stdio.h>
#include <string.h>

// Function to swap two characters in a string
void swap(char* x, char* y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

// Function to print all permutations of a string
void permute(char* str, int left, int right) {
    // If left index is equal to right index, print the current permutation
    if (left == right) {
        printf("%s\n", str);
    } else {
        // Generate permutations by swapping characters
        for (int i = left; i <= right; i++) {
            swap((str + left), (str + i));   // Swap character at left with i
            permute(str, left + 1, right);   // Recurse for the next position
            swap((str + left), (str + i));   // Backtrack: restore the original string
        }
    }
}

int main() {
    char str[] = "abc";  // Input string
    int n = strlen(str);  // Get length of the string

    printf("All permutations of the string \"%s\" are:\n", str);
    permute(str, 0, n - 1);  // Call the permute function to generate all permutations

    return 0;
}
```


# Compress a string

```c
#include <stdio.h>
#include <string.h>

void compressString(char *str) {
    int len = strlen(str);
    
    // If the string is empty or has only one character, no compression is needed
    if (len == 0 || len == 1) {
        printf("%s\n", str);
        return;
    }

    int count = 1;
    char compressedStr[2 * len + 1];  // Maximum possible compressed size

    int j = 0; // To index the compressed string

    for (int i = 1; i <= len; i++) {
        // If current character is the same as the previous one, increase the count
        if (str[i] == str[i - 1]) {
            count++;
        } else {
            // Otherwise, add the character and its count to the compressed string
            compressedStr[j++] = str[i - 1];
            if (count > 1) {
                j += sprintf(compressedStr + j, "%d", count); // Append the count
            }
            count = 1;  // Reset the count
        }
    }
    
    compressedStr[j] = '\0';  // Null-terminate the compressed string
    printf("Compressed String: %s\n", compressedStr);
}

int main() {
    char str[] = "aaabbccccdaaa";
    
    printf("Original String: %s\n", str);
    compressString(str);

    return 0;
}
```


# Occurrences of a elements

```c
*
#include <stdio.h>

int main()
{
    int size;
    scanf("%d", &size);

    int arr[size];

    int occ[size];

    int visited = -1;

    for (int i = 0; i < size; i++)
    {
        scanf("%d", &arr[i]);
        occ[i] = 1;
    }

    for (int i = 0; i < size; i++)
    {
        if (occ[i] == visited)
        {
            continue;
        }
        for (int j = i + 1; j < size; j++)
        {
            if (arr[i] == arr[j]){
                
            occ[i]++;
            occ[j] = visited;
            }
        }
    }

    for (int i=0; i<size; i++){
        if (occ[i] != visited){
            printf("%d ", occ[i]);
        }
    }
}
```
