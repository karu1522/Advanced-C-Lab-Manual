# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.

## Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:
```c
#include <stdio.h>

#define SIZE 5

int stack[SIZE];
int top = -1;

void push(int x)
{
    if (top == SIZE - 1)
        printf("Stack Overflow!\n");
    else
        stack[++top] = x;
}

void pop()
{
    if (top == -1)
        printf("Stack Underflow!\n");
    else
        top--;
}

void peek()
{
    if (top == -1)
        printf("Stack is Empty!\n");
    else
        printf("Top element = %d\n", stack[top]);
}

void display()
{
    if (top == -1)
        printf("Stack is Empty!\n");
    else {
        printf("Stack elements: ");
        for (int i = top; i >= 0; i--)
            printf("%d ", stack[i]);
        printf("\n");
    }
}

int main()
{
    int choice, value;

    while (1)
    {
        printf("\n1.Push\n2.Pop\n3.Peek\n4.Display\n5.Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice)
        {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;

            case 2:
                pop();
                break;

            case 3:
                peek();
                break;

            case 4:
                display();
                break;

            case 5:
                return 0;

            default:
                printf("Invalid Choice!\n");
        }
    }
}
```



## Output:
<img width="287" height="333" alt="image" src="https://github.com/user-attachments/assets/861c7422-cd76-46c9-a32e-a9047e415348" />



## Result:
Thus, the program to display stack elements using an array is verified successfully.
 

# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.

## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:
```c
#include <stdio.h>
#define SIZE 5
float stack[SIZE];
int top = -1;

void push(float value)
{
    if (top == SIZE - 1)
        printf("Stack Overflow!\n");
    else {
        stack[++top] = value;
        printf("%.2f pushed into stack.\n", value);
    }
}

int main(){
    float val;
    printf("Enter a value: ");
    scanf("%f", &val);
    push(val);
}
```


## Output:
<img width="231" height="69" alt="image" src="https://github.com/user-attachments/assets/ba0427d7-c5a1-4551-a453-6508b2ed4eb9" />




## Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
## Aim:
To write a C program to display queue elements using array

## Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:
```c
#include <stdio.h>
#define SIZE 5
int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int x){
    if (rear == SIZE - 1)
        printf("Queue Overflow!\n");
    else {
        if (front == -1) 
            front = 0;
        queue[++rear] = x;
    }
}

void display(){
    if (front == -1 || front > rear)
        printf("Queue is Empty!\n");
    else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
        printf("\n");
    }
}

int main(){
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
}
```

## Output:
<img width="275" height="50" alt="image" src="https://github.com/user-attachments/assets/cbfd4b55-c2a7-4976-997c-a026929dadfa" />


## Result:
Thus, the program to display queue elements using array is verified successfully.


 
# EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:
```c
#include <stdio.h>
#define SIZE 5
float queue[SIZE];
int front = -1, rear = -1;

void enqueue(float value){
    if (rear == SIZE - 1)
    {
        printf("Queue Overflow!\n");
    }

    if (front == -1)
        front = 0;

    queue[++rear] = value;
    printf("%.2f inserted into queue.\n", value);
}

int main(){
    float val;
    printf("Enter value: ");
    scanf("%f", &val);
    enqueue(val);
}
```

## Output:
<img width="282" height="70" alt="image" src="https://github.com/user-attachments/assets/c21488cb-3f83-4c9a-86cc-c4a439582346" />



## Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



## Program:
```c
#include <stdio.h>
#define SIZE 5
int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int x){
    if (rear == SIZE - 1)
        printf("Queue Overflow!\n");
    else {
        if (front == -1)
            front = 0;
        queue[++rear] = x;
    }
}

void dequeue(){
    if (front == -1){
        printf("Queue Underflow! Queue is empty.\n");
        return;
    }

    printf("Deleted element: %d\n", queue[front]);

    front++;

    if (front > rear)
        front = rear = -1;
}

int main(){
    enqueue(10);
    enqueue(20);
    enqueue(30);
    dequeue();
    dequeue();
    dequeue();
    dequeue();
}
```

## Output:
<img width="369" height="116" alt="image" src="https://github.com/user-attachments/assets/ba59715a-e633-4d4c-af0e-dc9ec4c84c4d" />



## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
