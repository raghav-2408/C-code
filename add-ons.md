# Reverse an array 

```c
// Online C compiler to run C program online
#include <stdio.h>

int main() {
    int arr[10] = {1, 2, 3, 45, 1, 34};
    int ind[] = {6, 5, 4, 3, 2, 1};
    
    int temp[5];
    
    for(int i=0; i<6; i++){
        temp[ind[i]] = arr[i]; // wo element hi temp ke liye index hoga
    }
    
    for(int i=1; i<=6; i++){
        printf("%d ", temp[i]);
    }
    return 0;
}
```
