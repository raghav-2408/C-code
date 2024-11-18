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
