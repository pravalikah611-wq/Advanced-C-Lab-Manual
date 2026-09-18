

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display()
{
    struct Node *p = head;

    if (p == NULL)
    {
        printf("Stack is empty");
        return;
    }

    printf("Stack elements are:\n");

    while (p != NULL)
    {
        printf("%d ", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 30;
    newNode->next = head;
    head = newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 20;
    newNode->next = head;
    head = newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 10;
    newNode->next = head;
    head = newNode;

    display();

    return 0;
}

Output:

<img width="1722" height="728" alt="image" src="https://github.com/user-attachments/assets/846e2a3d-d869-4f86-84f1-22e88e2ba6ae" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void pop()
{
    struct Node *temp;

    if (head == NULL)
    {
        printf("Stack is empty");
        return;
    }

    temp = head;
    printf("Popped element = %d", head->data);
    head = head->next;
    free(temp);
}

int main()
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 30;
    newNode->next = head;
    head = newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 20;
    newNode->next = head;
    head = newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 10;
    newNode->next = head;
    head = newNode;

    pop();

    return 0;
}


Output:

<img width="1850" height="772" alt="image" src="https://github.com/user-attachments/assets/58b2360b-de9a-4807-b5b5-1f028b69c5c4" />


Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void display()
{
    struct Node *temp = front;

    if (front == NULL)
    {
        printf("Queue is empty");
        return;
    }

    printf("Queue elements are:\n");

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 10;
    newNode->next = NULL;
    front = rear = newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 20;
    newNode->next = NULL;
    rear->next = newNode;
    rear = newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));
    newNode->data = 30;
    newNode->next = NULL;
    rear->next = newNode;
    rear = newNode;

    display();

    return 0;
}

Output:

<img width="1905" height="763" alt="image" src="https://github.com/user-attachments/assets/e6ac20ce-0496-44c8-b117-258f39ca5c75" />

Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *next;
};

struct node *front = NULL, *rear = NULL;

void enqueue(int value)
{
    struct node *p;

    p = (struct node *)malloc(sizeof(struct node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

void display()
{
    struct node *temp = front;

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter element: ");
        scanf("%d", &value);
        enqueue(value);
    }

    printf("Queue elements are: ");
    display();

    return 0;
}

Output:

<img width="1897" height="776" alt="image" src="https://github.com/user-attachments/assets/b3e551b4-0053-4a77-b2b4-6bd9de8c23a2" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *next;
};

struct node *front = NULL, *rear = NULL;

void enqueue(int value)
{
    struct node *p;

    p = (struct node *)malloc(sizeof(struct node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

void peek()
{
    if (front == NULL)
    {
        printf("Queue is empty");
    }
    else
    {
        printf("Peek element is: %d", front->data);
    }
}

int main()
{
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter element: ");
        scanf("%d", &value);
        enqueue(value);
    }

    peek();

    return 0;
}

Output:


<img width="1912" height="865" alt="image" src="https://github.com/user-attachments/assets/d7a1513b-8687-43ee-8f06-af66c748ef09" />



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


