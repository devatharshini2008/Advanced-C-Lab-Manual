EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
~~~
#include <stdio.h>

#define MAX 100

int stack[MAX];
int top = -1;

void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
    }
}

void pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
    } else {
        printf("Deleted element: %d\n", stack[top]);
        top--;
    }
}

void display() {
    int i;

    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements are:\n");
        for (i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

int main() {
    int n, i, value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        push(value);
    }

    display();

    return 0;
}
~~~

Output:

<img width="575" height="422" alt="image" src="https://github.com/user-attachments/assets/863f721c-4358-43b1-90ec-063e84007252" />

Result:

Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
~~~
#include <stdio.h>

#define MAX 100

float stack[MAX];
int top = -1;

void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
        printf("Element pushed: %.2f\n", value);
    }
}

int main() {
    float value;

    printf("Enter the element to push: ");
    scanf("%f", &value);

    push(value);

    printf("Stack element is: %.2f\n", stack[top]);

    return 0;
}
~~~


Output:

<img width="661" height="266" alt="image" src="https://github.com/user-attachments/assets/b26b8740-a96b-4278-a814-e74171dd224e" />


Result:

Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
~~~
#include <stdio.h>

#define MAX 100

int queue[MAX];
int front = 0;
int rear = -1;

void display() {
    int i;

    if (rear < front) {
        printf("Queue is empty\n");
    } else {
        printf("Queue elements are:\n");
        for (i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

int main() {
    int n, i;

    printf("Enter the number of queue elements: ");
    scanf("%d", &n);

    if (n > MAX) {
        printf("Queue size exceeded\n");
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &queue[i]);
        rear++;
    }

    display();

    return 0;
}
~~~
Output:

//paste your output here


Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

~~~
#include <stdio.h>

#define MAX 100

float queue[MAX];
int front = 0;
int rear = -1;

void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
    } else {
        rear++;
        queue[rear] = value;
        printf("Element inserted: %.2f\n", value);
    }
}

int main() {
    int n, i;
    float value;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        enqueue(value);
    }

    printf("\nQueue elements are:\n");

    for (i = front; i <= rear; i++) {
        printf("%.2f ", queue[i]);
    }

    return 0;
}
~~~

Output:

<img width="567" height="415" alt="image" src="https://github.com/user-attachments/assets/c4447216-777c-4705-aaa8-61587f3b947a" />


Result:

Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

~~~
#include <stdio.h>

#define MAX 100

int queue[MAX];
int front = -1;
int rear = -1;

void deleteElement() {
    if (front == -1) {
        printf("Queue is empty\n");
    } else {
        printf("Deleted element: %d\n", queue[front]);
        front++;

        if (front > rear) {
            front = -1;
            rear = -1;
        }
    }
}

int main() {
    int n, i;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    if (n > MAX) {
        printf("Queue size exceeded\n");
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &queue[i]);
    }

    front = 0;
    rear = n - 1;

    printf("\nQueue elements before deletion:\n");
    for (i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }

    printf("\n\n");
    deleteElement();

    if (front != -1) {
        printf("\nQueue elements after deletion:\n");
        for (i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
    } else {
        printf("Queue is empty\n");
    }

    return 0;
}
~~~

Output:

<img width="520" height="436" alt="image" src="https://github.com/user-attachments/assets/6042e43c-1caf-44bc-9f70-010a8ef25b6a" />


Result:

Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
