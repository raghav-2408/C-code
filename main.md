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
