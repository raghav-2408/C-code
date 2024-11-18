# shuffle the strings ( shuffled[index[i]] = str[i] )

```c
// Online C compiler to run C program online
#include <stdio.h>

int main() {
    char s[256] = "codeleet";
    int indices[] = {4,5,6,7,0,2,1,3};
    
    char shuffled[100]; 
    
    for(int i=0; i<8; i++){
        shuffled[indices[i]] = s[i]; 
    }
    
    printf("%s", shuffled);
    return 0;
}
```


# Score of a string

```
Input: s = "hello"

Output: 13

Explanation:

The ASCII values of the characters in s are: 'h' = 104, 'e' = 101, 'l' = 108, 'o' = 111. So, the score of s would be |104 - 101| + |101 - 108| + |108 - 108| + |108 - 111| = 3 + 7 + 0 + 3 = 13.
```

```c
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>

int main() {
    char str[100] = "hello";
    
    int sum = 0, j = 0;
    
    for(int i=1; i<5; i++){
        sum += abs(str[j++] - str[i]);
    }
    
    printf("%d", sum);
    return 0;
}
```


# string conversion  (ctype.h)

```c
// Online C compiler to run C program online
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[100] = "HellO";
    
    int i=0;
    while (str[i] != '\0'){
        str[i] = tolower(str[i]);
        i++;
    }
    printf("%s", str);
    return 0;
}
```


```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[100] = "HellO";
    int ch;
    scanf("%d", &ch);
    int i = 0;
    
    switch(ch){
        case 1 : while (str[i] != '\0'){
                    str[i] = tolower(str[i]);
                    i++;
                }
                break;
        case 2 : 
                while (str[i] != '\0'){
                    str[i] = toupper(str[i]);
                    i++;
                }
                break;
        default : printf("Invalid choice");
                return 1;
        }
    
    printf("%s", str);
    return 0;
}
```


# reverse a string (both chars and whole string)

# Chars

```c
void reverseString(char* s, int sSize) {
    int start = 0, end = sSize - 1;

    while(start < end){
        char temp = s[start];
        s[start] = s[end];
        s[end] = temp;
        start++;
        end--;
    }
    printf("%s", s);
}
```

# String 

```c
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

void reverseString(char* str, int len){
    char rev[len+1];
    int j = 0;
    for(int i=len-1; i>=0; i--){
        rev[j++] = str[i];
    }
    printf("%s", rev);
}

int main() {
    char str[] = {'h', 'e', 'l', 'l', 'o'};
    int N = strlen(str);
    reverseString(str, N);
    return 0;
}
```

# check all A's comes before B's

```c
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>
#include <stdbool.h>

bool checkA(char* str, int len){
    int j = 0;
    bool flag = false;
    char foundB;
    for(int i=0; i<len; i++){
        if (str[i] == 'b' || str[i] == 'B'){
            foundB = true;
        }
        if((str[i] == 'A' && foundB) || (str[i] == 'a' && foundB)){
            return false;
        }
    }
    return true;
}

int main() {
    char str[] = "abb";
    int N = strlen(str);
    if(checkA(str, N)){
        printf("true");
    }else{
        printf("false");
    }
    return 0;
}
```

