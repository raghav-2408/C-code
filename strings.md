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
