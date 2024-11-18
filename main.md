# Linked List

```C
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>

struct Node{
    int data;
    struct Node *next;
};

struct Node* head = NULL;

void insert(int data){
    struct Node* newnode = (struct Node*) malloc(sizeof(struct Node));
    
    newnode->data = data;
    newnode->next = NULL;
    
    if (head == NULL){
        head = newnode;
    }
    else{
    struct Node* temp = head;
    while(temp->next!=NULL){
        temp = temp->next;
    }
    temp->next = newnode;
    }
}

void display(struct Node* head){
    struct Node* temp = head;
    
    while(temp!=NULL){
        printf("%d ->", temp->data);
        temp = temp->next;
    }
    
    printf("NULL");
}

int main() {
    insert(30);
    insert(20);
    display(head);
    return 0;
    
}
```


# Reverse a Linked list

```c
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>

struct Node{
    int data;
    struct Node *next;
};

struct Node* head = NULL;

void insert(int data){
    struct Node* newnode = (struct Node*) malloc(sizeof(struct Node));
    
    newnode->data = data;
    newnode->next = NULL;
    
    if (head == NULL){
        head = newnode;
    }
    else{
    struct Node* temp = head;
    while(temp->next!=NULL){
        temp = temp->next;
    }
    temp->next = newnode;
    }
}

void display(struct Node* head){
    struct Node* temp = head;
    
    while(temp!=NULL){
        printf("%d ->", temp->data);
        temp = temp->next;
    }
    
    printf("NULL");
}

struct Node* reverseLL(struct Node* head){
    struct Node* p = NULL;
    struct Node* curr = head;
    struct Node* next = NULL;
    
    while(curr!=NULL){
        next = curr->next;
        curr->next = p;
        p = curr;
        curr = next;
    }
    return p;
}

int main() {
    insert(10);
    insert(20);
    insert(30);
    head = reverseLL(head);
    display(head);
    return 0;
    
}

```

# Palindrone and its lenght, ASCII

```c
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], rev[100];
    
    scanf("%s", str);
    int N1 = strlen(str);
    
    for(int i=0; i<N1; i++){
        rev[i] = str[N1 - i -1];
    }
    
    int isPal = 1;
    
    for(int i=0; i<N1; i++){
        if (str[i] != rev[i]){
            isPal = 0;
            break;
        }
    }
    
    if (isPal){
        printf("%d", N1);
    }else{
        printf("%d", str[0]);
    }
    return 0;
}
```
# Remove duplicates from the sorted array

```c
// Online C compiler to run C program online
#include <stdio.h>

int main() {
    int arr[100];
    int N, j = 0;
    scanf("%d", &N);
    
    for(int i=0; i<N; i++){
        scanf("%d", &arr[i]);
    }
    
    for(int i=1; i<N; i++){
        if(arr[j] != arr[i]){
            j++;
            arr[j] = arr[i]; // move to the next unique element;
        }
    }
    
    for(int i=0; i<=j; i++){
        printf("%d ", arr[i]);
    }
    return 0;
}
```

# Remove duplicated from the unsorted array

```c
#include <stdio.h>

void bubbleSort(int arr[], int N) {
    for (int i = 0; i < N - 1; i++) {
        for (int j = 0; j < N - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap arr[j] and arr[j+1]
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main() {
    int arr[100], N, j = 0;

    // Read the number of elements
    printf("Enter the number of elements: ");
    scanf("%d", &N);
    
    // Read elements of the array
    printf("Enter the elements of the array:\n");
    for(int i = 0; i < N; i++) {
        scanf("%d", &arr[i]);
    }
    
    // Step 1: Sort the array using bubble sort
    bubbleSort(arr, N);

    // Step 2: Remove duplicates from the sorted array
    for (int i = 1; i < N; i++) {
        if (arr[j] != arr[i]) {
            j++;
            arr[j] = arr[i]; // Move the next unique element forward
        }
    }

    // Print the array with unique elements
    printf("Array after removing duplicates:\n");
    for (int i = 0; i <= j; i++) {
        printf("%d ", arr[i]);
    }
    
    return 0;
}
```



# Unique occurrences or not

```

Code
Testcase
Test Result
Test Result
1207. Unique Number of Occurrences
Easy
Topics
Companies
Hint
Given an array of integers arr, return true if the number of occurrences of each value in the array is unique or false otherwise.

 

Example 1:

Input: arr = [1,2,2,1,1,3]
Output: true
Explanation: The value 1 has 3 occurrences, 2 has 2 and 3 has 1. No two values have the same number of occurrences.
```

```c
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>
#include <stdbool.h>

bool uniqueOccurrences(int arr[], int N){
    int count[100] = {0};
    int freq[100] = {0};
    
    for(int i=0; i<N; i++){
        count[arr[i]]++;
    }
    
    for(int i=0; i<100; i++){
        if (count[i] > 0){
            // if that frequence has already been seen.
            if(freq[count[i]] > 0){
                return false;
            }
            freq[count[i]]=1;
        }
    }
    return true;
}

int main() {
    int N;
    scanf("%d", &N);
    int arr[N];
    
    for(int i=0; i<N; i++){
        scanf("%d", &arr[i]);
    }
    
    if(uniqueOccurrences(arr, N)){
        printf("true");
    }else{
        printf("false");
    }
    return 0;
}

```

# first unique occurring character :

```c
// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

char firstUniqueOccurrence(char str[], int N){
    int count[256] = {0};

    for(int i=0; i<N; i++){
        count[str[i]]++;
    }
    
    for(int i=0; i<N; i++){
        if (count[str[i]] == 1){
            return str[i];
        }
    }
    return '\0';
}

int main() {
    char str[100];
    scanf("%s", str);
    int len = strlen(str);
    
    char res = firstUniqueOccurrence(str, len);
    
    if(res != '\0'){
        printf("%c", res);
    }else{
        printf("No more chars");
    }
    return 0;
}

```
