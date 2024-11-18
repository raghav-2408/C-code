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
