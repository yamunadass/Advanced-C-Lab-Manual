# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.
## Algorithm:
   * Step 1.	Include Necessary Header Files
   * Step 2.	Declare Global Variables
   * Step 3.	Define the Display Function
   * Step 4.	Main Function (or Other Relevant Code)
   * Step 5.	Initialize the stack and top as needed.
   * Step 6.	Perform stack operations (push, pop, etc.).
   * Step 7.	Use the display function to visualize the stack's contents
 
## Program:
```C
#include <stdio.h>

#define MAX 5  // Define the maximum size of the stack

int stack[MAX];
int top = -1;  // Initialize stack with top at -1, indicating the stack is empty

// Function to display stack elements
void display() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
}

// Function to push an element onto the stack
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
    }
}

// Function to pop an element from the stack
void pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
    } else {
        printf("Popped element: %d\n", stack[top]);
        top--;
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    push(40);
    push(50);

    // Display the stack elements
    display();

    // Pop an element
    pop();

    // Display the stack after pop
    display();

    return 0;
}

```
## Output:

![image](https://github.com/user-attachments/assets/5249ec82-36e4-414f-aad5-98a0db005474)


## Result:
Thus, the program to display stack elements using an array is verified successfully.
 

# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.
## Algorithm:
   * Step 1.	Declare global variables for the stack size, top index, and the stack itself.
   * Step 2.	Define the push function to add a floating-point number to the stack.
   * Step 3.	Initialize the stack size, top index, and the stack itself.
   * Step 4.	Call the push function as needed.
 
## Program:
```C
#include <stdio.h>

#define MAX 5  // Define the maximum size of the stack

float stack[MAX];  // Stack to hold floating-point numbers
int top = -1;  // Initialize stack with top at -1, indicating the stack is empty

// Function to push an element onto the stack
void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");  // Stack is full
    } else {
        top++;  // Increment the top index
        stack[top] = value;  // Push the element onto the stack
        printf("Element %.2f pushed onto the stack\n", value);
    }
}

int main() {
    float value;

    // Pushing some elements onto the stack
    printf("Enter a number to push onto the stack: ");
    scanf("%f", &value);
    push(value);

    printf("Enter another number to push onto the stack: ");
    scanf("%f", &value);
    push(value);

    printf("Enter another number to push onto the stack: ");
    scanf("%f", &value);
    push(value);

    // Display the final stack state
    printf("Stack after pushing elements:\n");
    for (int i = top; i >= 0; i--) {
        printf("%.2f ", stack[i]);
    }
    printf("\n");

    return 0;
}


```

## Output:

![image](https://github.com/user-attachments/assets/86c86a40-5211-40ad-b499-34389f545fa3)





## Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
## Aim:
To write a C program to display queue elements using array

## Algorithm:
   * Step 1.	Declare global variables for the queue, rear, front, and iteration
   * Step 2.	Define the display function to print the elements of the queue.
   * Step 3.	Initialize the queue, rear, and front as needed.
   * Step 4.	Call the display function and perform other queue operations as needed.
 
## Program:
```C
#include <stdio.h>

#define MAX 5  // Define the maximum size of the queue

int queue[MAX];
int front = -1, rear = -1;

// Function to display the elements of the queue
void display() {
    if (front == -1) {
        printf("Queue is empty\n");  // If front is -1, the queue is empty
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);  // Print each element in the queue
        }
        printf("\n");
    }
}

// Function to enqueue an element into the queue
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");  // Queue is full
    } else {
        if (front == -1) {  // If the queue is empty
            front = 0;
        }
        rear++;  // Move rear to the next position
        queue[rear] = value;
        printf("Enqueued %d to the queue\n", value);
    }
}

// Function to dequeue an element from the queue
void dequeue() {
    if (front == -1) {
        printf("Queue Underflow\n");  // Queue is empty
    } else {
        printf("Dequeued %d from the queue\n", queue[front]);
        front++;  // Move front to the next position
        if (front > rear) {  // If queue is empty after dequeue
            front = rear = -1;
        }
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);

    display();  // Display the elements of the queue

    dequeue();  // Dequeue one element
    display();  // Display the elements of the queue after dequeue

    return 0;
}


```
## Output:
![image](https://github.com/user-attachments/assets/4db78658-368f-4b7f-8d58-c31e9ebaba51)



## Result:
Thus, the program to display queue elements using array is verified successfully.


 
# EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
   * Step 1.	Declare global variables for the size, rear, front, and the queue itself.
   * Step 2.	Define the enqueue function to add a float to the queue.
   * Step 3.	Initialize the rear, front, and size of the queue as needed.
   * Step 4.	Call the enqueue function as needed.

## Program:
```C
#include <stdio.h>

#define MAX 5  // Define the maximum size of the queue

int queue[MAX];
int front = -1, rear = -1;

// Function to insert an element into the queue
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");  // If the queue is full
    } else {
        if (front == -1) {  // If the queue is empty
            front = 0;
        }
        rear++;  // Move rear to the next position
        queue[rear] = value;
        printf("Inserted %d into the queue\n", value);
    }
}

// Function to display the elements of the queue
void display() {
    if (front == -1) {
        printf("Queue is empty\n");  // If the queue is empty
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);  // Print each element in the queue
        }
        printf("\n");
    }
}

int main() {
    enqueue(10);  // Insert element 10 into the queue
    enqueue(20);  // Insert element 20 into the queue
    enqueue(30);  // Insert element 30 into the queue

    display();  // Display the elements of the queue

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/33a4cb02-cf6a-4d2d-9a29-0f8b83653d73)


## Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

## Aim:

To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:
   * Step 1.	Check if the Queue is Empty
    	- If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
   * Step 2.	Delete the Front Element
     - If the queue is not empty, the element at the front index is deleted.
     - Increment the front pointer by 1 to remove the element and point to the next element in the queue.
   * Step 3.	Check if the Queue Becomes Empty After Deletion:
     - After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
   * Step 4.	End the Function.



## Program:
```C
#include <stdio.h>

#define MAX 5  // Define the maximum size of the queue

int queue[MAX];
int front = -1, rear = -1;

// Function to delete an element from the queue
void dequeue() {
    if (front == -1) {
        printf("Queue Underflow\n");  // If the queue is empty
    } else {
        printf("Deleted %d from the queue\n", queue[front]);  // Print and delete the front element
        front++;  // Move the front pointer to the next element

        // Check if the queue is empty after deletion
        if (front > rear) {
            front = rear = -1;  // Reset the queue to empty
        }
    }
}

// Function to insert an element into the queue
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");  // If the queue is full
    } else {
        if (front == -1) {  // If the queue is empty
            front = 0;
        }
        rear++;  // Move rear to the next position
        queue[rear] = value;
        printf("Inserted %d into the queue\n", value);
    }
}

// Function to display the elements of the queue
void display() {
    if (front == -1) {
        printf("Queue is empty\n");  // If the queue is empty
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);  // Print each element in the queue
        }
        printf("\n");
    }
}

int main() {
    enqueue(10);  // Insert element 10 into the queue
    enqueue(20);  // Insert element 20 into the queue
    enqueue(30);  // Insert element 30 into the queue

    display();  // Display the elements of the queue

    dequeue();  // Delete an element from the queue
    display();  // Display the elements of the queue again

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/b3d2b9d5-47e3-4eac-98d6-4f93f4de70d7)



## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
