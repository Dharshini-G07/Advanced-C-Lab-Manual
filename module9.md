NAME : PRIYADHARSHINI G
REG NO : 212224230209
## EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

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
```
#include <stdio.h>
#define SIZE 5

int stack[SIZE];
int top = -1;

void push(int value) {
    if (top == SIZE - 1)
        printf("Stack Overflow\n");
    else {
        top++;
        stack[top] = value;
        printf("%d pushed to stack\n", value);
    }
}

void pop() {
    if (top == -1)
        printf("Stack Underflow\n");
    else {
        printf("%d popped from stack\n", stack[top]);
        top--;
    }
}

void display() {
    if (top == -1)
        printf("Stack is empty\n");
    else {
        printf("Stack elements:\n");
        for (int i = top; i >= 0; i--)
            printf("%d ", stack[i]);
        printf("\n");
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    display();
    pop();
    display();
    return 0;
}

```

Output:

<img width="263" height="225" alt="image" src="https://github.com/user-attachments/assets/9f350c21-d58f-4412-9e53-8726970eaef7" />


Result:
Thus, the program to display stack elements using an array is verified successfully.
 

## EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```
#include <stdio.h>
#define SIZE 5

float stack[SIZE];
int top = -1;

void push(float value) {
    if (top == SIZE - 1)
        printf("Stack Overflow\n");
    else {
        top++;
        stack[top] = value;
        printf("%.2f pushed to stack\n", value);
    }
}

int main() {
    push(10.5);
    push(20.3);
    push(30.8);
    push(40.2);
    push(50.1);
    push(60.6);
    return 0;
}
```

Output:

<img width="293" height="186" alt="image" src="https://github.com/user-attachments/assets/c6fec706-fb94-445a-989b-e5f67101c4ca" />



Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
## EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```
#include <stdio.h>
#define SIZE 5

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int value) {
    if (rear == SIZE - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%d enqueued to queue\n", value);
    }
}

void display() {
    if (front == -1)
        printf("Queue is empty\n");
    else {
        printf("Queue elements:\n");
        for (int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
        printf("\n");
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    enqueue(40);
    enqueue(50);
    display();
    return 0;
}
```

Output:

<img width="260" height="256" alt="image" src="https://github.com/user-attachments/assets/d4bf6be2-84af-4119-998d-39236e21dd2f" />



Result:
Thus, the program to display queue elements using array is verified successfully.


 
## EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```
#include <stdio.h>
#define SIZE 5

float queue[SIZE];
int front = -1, rear = -1;

void enqueue(float value) {
    if (rear == SIZE - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into queue\n", value);
    }
}

int main() {
    enqueue(10.5);
    enqueue(20.3);
    enqueue(30.7);
    enqueue(40.2);
    enqueue(50.9);
    enqueue(60.1);
    return 0;
}
```

Output:

<img width="309" height="174" alt="image" src="https://github.com/user-attachments/assets/fa58f313-4050-4b24-b812-f00ecf5c4ed5" />


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
## EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



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

```
#include <stdio.h>
#define SIZE 5

int q[SIZE], front = -1, rear = -1;

void dequeue() {
    if (front == -1)
        printf("Queue is empty\n");
    else {
        printf("%d deleted\n", q[front]);
        front++;
        if (front > rear)
            front = rear = -1;
    }
}

int main() {
    q[0] = 10; q[1] = 20; q[2] = 30;
    front = 0; rear = 2;

    dequeue();
    dequeue();
    dequeue();
    dequeue();
    return 0;
}
```

Output:

<img width="182" height="130" alt="image" src="https://github.com/user-attachments/assets/4256b9a0-6029-4f89-b3b6-67d3cee43d49" />



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
