

# EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
};
struct Node *head = NULL;

void display() {
    struct Node *p = head;
    printf("Elements to display : ");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
}

int main() {
    struct Node *n1 = malloc(sizeof(struct Node));
    struct Node *n2 = malloc(sizeof(struct Node));
    struct Node *n3 = malloc(sizeof(struct Node));

    n1->data = 10;
    n1->next = n2;
    n2->data = 20; 
    n2->next = n3;
    n3->data = 30; 
    n3->next = NULL;
    head = n1;
    display();
}
```

## Output:
<img width="370" height="45" alt="image" src="https://github.com/user-attachments/assets/634653b0-0879-4d80-b030-e583143d0764" />



## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



# EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
};

int pop(struct Node **head) {
    if (*head == NULL) {  
        printf("Stack is empty.\n");
        return;
    }
    struct Node *temp = *head;
    printf("Popped element: %d\n", temp->data);

    *head = (*head)->next;
    free(temp);
}

int main() {
    struct Node *head = NULL;
    struct Node *newNode;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = 10;
    newNode->next = head;
    head = newNode;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = 20;
    newNode->next = head;
    head = newNode;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = 30;
    newNode->next = head;
    head = newNode;

    pop(&head);
    pop(&head);
    pop(&head);
    pop(&head); 
}
```

## Output:
<img width="240" height="111" alt="image" src="https://github.com/user-attachments/assets/2228c454-25a7-4883-a148-c26702c04042" />




## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
# EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.

## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
};

void display(struct Node *front) {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    while (front != NULL) {
        printf("%d ", front->data);
        front = front->next;
    }
}

int main() {
    struct Node *front = NULL, *rear = NULL, *newNode;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = 10;
    newNode->next = NULL;
    front = rear = newNode;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = 20;
    newNode->next = NULL;
    rear->next = newNode;
    rear = newNode;

    newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = 30;
    newNode->next = NULL;
    rear->next = newNode;
    rear = newNode;

    printf("Queue elements: ");
    display(front);
}
```

## Output:
<img width="270" height="47" alt="image" src="https://github.com/user-attachments/assets/ce3fce1e-7b1c-4252-8cf3-ce64d37c3377" />


## Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
# EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
};

void enqueue(struct Node **front, struct Node **rear, int value) {
    struct Node *p = (struct Node*)malloc(sizeof(struct Node));
    p->data = value;
    p->next = NULL;

    if (*front == NULL) {
        *front = *rear = p;
    } else {
        (*rear)->next = p;
        *rear = p;
    }
}

int main() {
    struct Node *front = NULL, *rear = NULL;

    enqueue(&front, &rear, 10);
    enqueue(&front, &rear, 20);
    enqueue(&front, &rear, 30);

    struct Node *temp = front;
    printf("Queue elements inserted : ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}
```

## Output:
<img width="392" height="45" alt="image" src="https://github.com/user-attachments/assets/d8ffd6c9-0a16-432b-bf3c-3886dd420a1f" />


## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



# EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:
```c
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
};

int peek(struct Node *front) {
    if (front == NULL) {
        printf("Queue is empty.");
        return -1;
    }
    printf("Peek element: %d", front->data);
    return front->data;
}

int main() {
    struct Node *front = NULL, *rear = NULL;

    struct Node *p1 = (struct Node*)malloc(sizeof(struct Node));
    p1->data = 10; p1->next = NULL;
    front = rear = p1;

    struct Node *p2 = (struct Node*)malloc(sizeof(struct Node));
    p2->data = 20; p2->next = NULL;
    rear->next = p2;
    rear = p2;

    peek(front);
}
```

## Output:
<img width="251" height="42" alt="image" src="https://github.com/user-attachments/assets/f1273953-30b2-4aec-873d-a98156b17219" />




## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


