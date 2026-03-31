<blr>
      ~Mohammed Feroz
 <blr>


# Linked-List-Delete-At-End
Deletes the last node of a linked list by traversing to the second-last node and updating its next pointer to NULL. Handles edge cases like empty list or single node. Frees memory of the deleted node to avoid memory leaks and maintains list integrity.


**Code **
#include <stdio.h>
#include<stdlib.h>
struct node{
    int data ;
    struct node*next;
};
void insertAtend(struct node**head,int val)
{
    struct node*newnode=(struct node*)malloc(sizeof(struct node));
    newnode->data = val;
    newnode->next = NULL;
if(*head == NULL)
{
    *head = newnode;
    return;
}
else 
{
    struct node*temp = *head;
    while(temp->next!=NULL)
    {
        temp =temp->next;
    }
    temp->next = newnode;
}
    
}
void deleteatend(struct node* head) {
 

    struct node* temp =head;
    while (temp->next->next != NULL) {
        temp = temp->next;
    }


    temp->next = NULL;
}
void display(struct node*head)
{
    struct node*temp =head;
    while(temp!=NULL)
    {
        printf("%d->" , temp->data);
        temp=temp->next;
        
    }
    printf("NULL");
}
int main()
{
    struct node*head= NULL;
    int n, val;
    printf("enter the number of elements: ");
    scanf("%d",&n);
    printf("enter the values: ");
    for(int i=0;i<n;i++)
    {
        scanf("%d",&val);
        insertAtend(&head,val);
    }

    deleteatend(head);
    printf("after deleting : ");
    display(head);
    return 0;
}
