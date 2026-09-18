EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct node
{
    char data;
    struct node *next;
};

void search(struct node *head, char key)
{
    struct node *temp = head;
    int position = 1;

    while (temp != NULL)
    {
        if (temp->data == key)
        {
            printf("Element found at position %d\n", position);
            return;
        }

        temp = temp->next;
        position++;
    }

    printf("Element not found\n");
}

int main()
{
    struct node *head = NULL;
    struct node *newnode, *temp;
    int n, i;
    char key;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        newnode = (struct node *)malloc(sizeof(struct node));

        printf("Enter character: ");
        scanf(" %c", &newnode->data);

        newnode->next = NULL;

        if (head == NULL)
        {
            head = newnode;
        }
        else
        {
            temp = head;

            while (temp->next != NULL)
            {
                temp = temp->next;
            }

            temp->next = newnode;
        }
    }

    printf("Enter character to search: ");
    scanf(" %c", &key);

    search(head, key);

    return 0;
}

Output:
<img width="1883" height="876" alt="image" src="https://github.com/user-attachments/assets/61eb7f69-7245-4dc7-b5b6-6bdbf0d8d9dd" />




Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct node
{
    char data;
    struct node *next;
};

void insert(struct node **head, char value)
{
    struct node *newnode;
    struct node *temp;

    newnode = (struct node *)malloc(sizeof(struct node));

    newnode->data = value;
    newnode->next = NULL;

    if (*head == NULL)
    {
        *head = newnode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newnode;
    }
}

void display(struct node *head)
{
    struct node *temp = head;

    printf("Linked List: ");

    while (temp != NULL)
    {
        printf("%c ", temp->data);
        temp = temp->next;
    }

    printf("\n");
}

int main()
{
    struct node *head = NULL;
    int n, i;
    char value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter character: ");
        scanf(" %c", &value);

        insert(&head, value);
    }

    display(head);

    return 0;
}
Output:

<img width="1917" height="862" alt="image" src="https://github.com/user-attachments/assets/c707a17b-adfa-4fe8-b033-1d37e0f41402" />


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *prev;
    struct node *next;
};

void traverse(struct node *head)
{
    struct node *temp = head;

    printf("Doubly Linked List: ");

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");
}

int main()
{
    struct node *head = NULL;
    struct node *newnode, *temp;
    int n, i;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        newnode = (struct node *)malloc(sizeof(struct node));

        printf("Enter data: ");
        scanf("%d", &newnode->data);

        newnode->prev = NULL;
        newnode->next = NULL;

        if (head == NULL)
        {
            head = newnode;
        }
        else
        {
            temp = head;

            while (temp->next != NULL)
            {
                temp = temp->next;
            }

            temp->next = newnode;
            newnode->prev = temp;
        }
    }

    traverse(head);

    return 0;
}
Output:

<img width="1813" height="878" alt="image" src="https://github.com/user-attachments/assets/2e7079a8-84ad-40e8-96c2-588f3c140141" />



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *prev;
    struct node *next;
};

void insert(struct node **head, int value)
{
    struct node *newNode;
    struct node *temp;

    newNode = (struct node *)malloc(sizeof(struct node));

    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        newNode->prev = temp;
        temp->next = newNode;
    }
}

void display(struct node *head)
{
    struct node *temp = head;

    printf("Doubly Linked List: ");

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");
}

int main()
{
    struct node *head = NULL;
    int n, i, value;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter element: ");
        scanf("%d", &value);

        insert(&head, value);
    }

    display(head);

    return 0;
}
Output:

<img width="1845" height="750" alt="image" src="https://github.com/user-attachments/assets/12454120-a9ac-4103-8b58-1477b3695c24" />


Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *next;
};

void deleteElement(struct node **head, int value)
{
    struct node *current;
    struct node *prev;

    if (*head == NULL)
    {
        printf("Linked List is empty\n");
        return;
    }

    current = *head;
    prev = NULL;

    while (current != NULL)
    {
        if (current->data == value)
        {
            if (prev == NULL)
            {
                *head = current->next;
            }
            else
            {
                prev->next = current->next;
            }

            free(current);
            printf("Element deleted successfully\n");
            return;
        }

        prev = current;
        current = current->next;
    }

    printf("Element not found\n");
}

void display(struct node *head)
{
    struct node *temp = head;

    printf("Linked List: ");

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");
}

int main()
{
    struct node *head = NULL;
    struct node *newNode;
    struct node *temp;
    int n, i, value, deleteValue;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        newNode = (struct node *)malloc(sizeof(struct node));

        printf("Enter element: ");
        scanf("%d", &value);

        newNode->data = value;
        newNode->next = NULL;

        if (head == NULL)
        {
            head = newNode;
        }
        else
        {
            temp = head;

            while (temp->next != NULL)
            {
                temp = temp->next;
            }

            temp->next = newNode;
        }
    }

    printf("\nBefore deletion:\n");
    display(head);

    printf("Enter element to delete: ");
    scanf("%d", &deleteValue);

    deleteElement(&head, deleteValue);

    printf("After deletion:\n");
    display(head);

    return 0;
}

Output:

<img width="1902" height="723" alt="image" src="https://github.com/user-attachments/assets/31602961-16d0-4bcf-be6f-4de3e78eccbd" />





Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





