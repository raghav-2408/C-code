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
