

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
~~~
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display() {
    struct Node *p = head;

    if (p == NULL) {
        printf("Stack is empty\n");
        return;
    }

    printf("Stack elements are:\n");

    while (p != NULL) {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main() {
    struct Node *p;
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        p = (struct Node *)malloc(sizeof(struct Node));

        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);

        p->data = value;
        p->next = head;
        head = p;
    }

    display();

    return 0;
}
~~~

Output:

<img width="527" height="347" alt="image" src="https://github.com/user-attachments/assets/8c8fd969-1bde-48f0-952a-4663806087f9" />


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
~~~
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void pop() {
    struct Node *p;

    if (head == NULL) {
        printf("Stack is empty\n");
    } else {
        p = head;
        printf("Popped element: %d\n", p->data);
        head = head->next;
        free(p);
    }
}

int main() {
    struct Node *p;
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        p = (struct Node *)malloc(sizeof(struct Node));

        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);

        p->data = value;
        p->next = head;
        head = p;
    }

    printf("\nStack before pop:\n");

    p = head;
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }

    printf("\n");

    pop();

    printf("Stack after pop:\n");

    p = head;
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }

    printf("\n");

    return 0;
}
~~~

Output:

<img width="586" height="362" alt="image" src="https://github.com/user-attachments/assets/efe14947-1291-41f1-b3d0-22868f655236" />


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

~~~
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;

void display() {
    struct Node *p = front;

    if (p == NULL) {
        printf("Queue is empty\n");
        return;
    }

    printf("Queue elements are:\n");

    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }

    printf("\n");
}

int main() {
    struct Node *p, *rear = NULL;
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        p = (struct Node *)malloc(sizeof(struct Node));

        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);

        p->data = value;
        p->next = NULL;

        if (front == NULL) {
            front = p;
            rear = p;
        } else {
            rear->next = p;
            rear = p;
        }
    }

    display();

    return 0;
}
~~~

Output:

<img width="502" height="280" alt="image" src="https://github.com/user-attachments/assets/66dd5544-0c02-47ac-b951-0de255ddf65b" />

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
~~~
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value) {
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL) {
        front = p;
        rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void display() {
    struct Node *p = front;

    printf("Queue elements are:\n");

    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }

    printf("\n");
}

int main() {
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);
    }

    display();

    return 0;
}
~~~
Output:

<img width="552" height="265" alt="image" src="https://github.com/user-attachments/assets/95c40e9a-bd97-4b12-b426-832f01573084" />

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

~~~
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value) {
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL) {
        front = p;
        rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void peek() {
    if (front == NULL) {
        printf("Queue is empty\n");
    } else {
        printf("Peek element: %d\n", front->data);
    }
}

int main() {
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);
    }

    peek();

    return 0;
}
~~~

Output:

<img width="547" height="275" alt="image" src="https://github.com/user-attachments/assets/a7e4bfd3-8611-4af6-859b-779da4f9a1a7" />


Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


