NAME : PRIYADHARSHINI G
REG NO : 212224230209
## EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

void search(struct node *head, int key) {
    struct node *temp = head;
    while (temp != NULL) {
        if (temp->data == key) {
            printf("Element %d found!\n", key);
            return;
        }
        temp = temp->next;
    }
    printf("Element %d not found.\n", key);
}

int main() {
    struct node *head = NULL, *second = NULL, *third = NULL;

    head = malloc(sizeof(struct node));
    second = malloc(sizeof(struct node));
    third = malloc(sizeof(struct node));

    head->data = 10; head->next = second;
    second->data = 20; second->next = third;
    third->data = 30; third->next = NULL;

    search(head, 20);
    search(head, 40);

    return 0;
}
```

Output:

<img width="326" height="75" alt="image" src="https://github.com/user-attachments/assets/c3f22e11-de88-40a8-9c1c-9e1d6a55b09c" />


Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
## EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *next;
};

void insert(struct node **head, int val) {
    struct node *new = malloc(sizeof(struct node)), *temp = *head;
    new->data = val;
    new->next = NULL;
    if (*head == NULL) { *head = new; return; }
    while (temp->next) temp = temp->next;
    temp->next = new;
}

void display(struct node *head) {
    while (head) { printf("%d ", head->data); head = head->next; }
}

int main() {
    struct node *head = NULL;
    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    display(head);
}
```

Output:

<img width="155" height="46" alt="image" src="https://github.com/user-attachments/assets/ce8564d9-e8b9-4a67-a7a0-b74f2d727e97" />


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
## EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *prev, *next;
};

void traverse(struct node *head) {
    while (head) {
        printf("%d ", head->data);
        head = head->next;
    }
}

int main() {
    struct node *n1 = malloc(sizeof(struct node));
    struct node *n2 = malloc(sizeof(struct node));
    struct node *n3 = malloc(sizeof(struct node));

    n1->data = 10; n1->prev = NULL; n1->next = n2;
    n2->data = 20; n2->prev = n1;   n2->next = n3;
    n3->data = 30; n3->prev = n2;   n3->next = NULL;

    traverse(n1);
}
```

Output:


<img width="136" height="33" alt="image" src="https://github.com/user-attachments/assets/94492599-e64e-4d2c-bd6a-6ba0015f1faf" />



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



## EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};

void insertEnd(struct Node **head, int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL) {
        newNode->prev = NULL;
        *head = newNode;
        return;
    }

    struct Node *temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

void display(struct Node *head) {
    struct Node *temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;

    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);

    printf("Before inserting new element:\n");
    display(head);

    insertEnd(&head, 40);

    printf("After inserting new element (40):\n");
    display(head);

    return 0;
}
```

Output:

<img width="399" height="126" alt="image" src="https://github.com/user-attachments/assets/fd21415e-8d66-4bf3-8629-49ac65dd2043" />



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




## EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST


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

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

void deleteNode(struct Node **head, int key) {
    struct Node *temp = *head, *prev = NULL;

    if (temp == NULL) {
        printf("List is empty.\n");
        return;
    }

    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        printf("Element %d deleted.\n", key);
        return;
    }

    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element %d not found.\n", key);
        return;
    }

    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted.\n", key);
}

void display(struct Node *head) {
    struct Node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL, *second = NULL, *third = NULL;

    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));

    head->data = 10; head->next = second;
    second->data = 20; second->next = third;
    third->data = 30; third->next = NULL;

    printf("Before deletion:\n");
    display(head);

    deleteNode(&head, 20);

    printf("After deletion:\n");
    display(head);

    return 0;
}
```

Output:

<img width="256" height="149" alt="image" src="https://github.com/user-attachments/assets/fab54efc-0761-4cb0-af95-bd331978fb5b" />






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





