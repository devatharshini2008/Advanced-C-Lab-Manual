EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct node {
    char data;
    struct node *next;
};

int search(struct node *head, char key) {
    int position = 1;

    while (head != NULL) {
        if (head->data == key)
            return position;

        head = head->next;
        position++;
    }

    return -1;
}

int main() {
    struct node *head = NULL, *newNode, *temp;
    int n, i, position;
    char key;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        newNode = (struct node *)malloc(sizeof(struct node));

        printf("Enter character %d: ", i + 1);
        scanf(" %c", &newNode->data);

        newNode->next = NULL;

        if (head == NULL) {
            head = newNode;
        } else {
            temp = head;
            while (temp->next != NULL)
                temp = temp->next;

            temp->next = newNode;
        }
    }

    printf("Enter the character to search: ");
    scanf(" %c", &key);

    position = search(head, key);

    if (position != -1)
        printf("Element found at position %d\n", position);
    else
        printf("Element not found\n");

    temp = head;
    while (temp != NULL) {
        struct node *deleteNode = temp;
        temp = temp->next;
        free(deleteNode);
    }

    return 0;
}
~~~

Output:

<img width="492" height="340" alt="image" src="https://github.com/user-attachments/assets/1d7ce203-ed37-45e0-8258-c4e32c4d34f3" />


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
~~~
#include <stdio.h>
#include <stdlib.h>

struct node {
    char data;
    struct node *next;
};

void insert(struct node **head, char data) {
    struct node *newNode;
    struct node *temp;

    newNode = (struct node *)malloc(sizeof(struct node));
    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
    } else {
        temp = *head;

        while (temp->next != NULL)
            temp = temp->next;

        temp->next = newNode;
    }
}

void display(struct node *head) {
    while (head != NULL) {
        printf("%c ", head->data);
        head = head->next;
    }
    printf("\n");
}

int main() {
    struct node *head = NULL;
    int n, i;
    char data;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter character %d: ", i + 1);
        scanf(" %c", &data);
        insert(&head, data);
    }

    printf("Linked list after insertion:\n");
    display(head);

    return 0;
}
~~~

Output:

<img width="542" height="380" alt="image" src="https://github.com/user-attachments/assets/20c7d624-0465-4329-8d54-62d153de55fc" />
 
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

~~~
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *prev;
    struct node *next;
};

int main() {
    struct node *head = NULL;
    struct node *temp;
    struct node *newNode;
    int n, i, value;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        newNode = (struct node *)malloc(sizeof(struct node));

        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);

        newNode->data = value;
        newNode->prev = NULL;
        newNode->next = NULL;

        if (head == NULL) {
            head = newNode;
        } else {
            temp = head;

            while (temp->next != NULL)
                temp = temp->next;

            temp->next = newNode;
            newNode->prev = temp;
        }
    }

    printf("Doubly linked list elements are:\n");

    temp = head;

    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");

    return 0;
}
~~~

Output:

<img width="600" height="327" alt="image" src="https://github.com/user-attachments/assets/ca02e014-1f7c-47aa-9ef5-e94c23a4a8dd" />


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
~~~
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *prev;
    struct node *next;
};

struct node *insert(struct node *head, int value) {
    struct node *newNode;
    struct node *temp;

    newNode = (struct node *)malloc(sizeof(struct node));

    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    if (head == NULL) {
        return newNode;
    }

    temp = head;

    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;

    return head;
}

void display(struct node *head) {
    struct node *temp = head;

    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");
}

int main() {
    struct node *head = NULL;
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        head = insert(head, value);
    }

    printf("Doubly linked list after insertion:\n");
    display(head);

    return 0;
}
~~~

Output:

<img width="585" height="317" alt="image" src="https://github.com/user-attachments/assets/3dfab0ca-6271-485c-b6db-b93de892bb11" />


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
~~~
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

void deleteElement(struct node **head, int value) {
    struct node *temp;
    struct node *prev;

    if (*head == NULL) {
        printf("Linked list is empty\n");
        return;
    }

    temp = *head;

    if (temp->data == value) {
        *head = temp->next;
        free(temp);
        printf("Element deleted successfully\n");
        return;
    }

    prev = temp;
    temp = temp->next;

    while (temp != NULL) {
        if (temp->data == value) {
            prev->next = temp->next;
            free(temp);
            printf("Element deleted successfully\n");
            return;
        }

        prev = temp;
        temp = temp->next;
    }

    printf("Element not found\n");
}

void display(struct node *head) {
    while (head != NULL) {
        printf("%d ", head->data);
        head = head->next;
    }

    printf("\n");
}

int main() {
    struct node *head = NULL;
    struct node *newNode;
    struct node *temp;
    int n, i, value, deleteValue;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        newNode = (struct node *)malloc(sizeof(struct node));

        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);

        newNode->data = value;
        newNode->next = NULL;

        if (head == NULL) {
            head = newNode;
        } else {
            temp = head;

            while (temp->next != NULL)
                temp = temp->next;

            temp->next = newNode;
        }
    }

    printf("Linked list before deletion:\n");
    display(head);

    printf("Enter the element to delete: ");
    scanf("%d", &deleteValue);

    deleteElement(&head, deleteValue);

    printf("Linked list after deletion:\n");
    display(head);

    return 0;
}
~~~

Output:

<img width="732" height="395" alt="image" src="https://github.com/user-attachments/assets/98602635-dd56-4347-adfd-efdc24d49d73" />


Result:

Thus, the function that deletes a given element from a linked list is verified successfully.





