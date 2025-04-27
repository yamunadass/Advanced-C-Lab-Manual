# EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
   * Step 1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
   * Step 2.	Declare a global variable head representing the starting node of the linked list.
   * Step 3.	Define a function display to print the elements of the linked list.
   * Step 4.	Declare a pointer p and initialize it with the head of the linked list.
   * Step 5.	Use a while loop to traverse the linked list
   * Step 6.	Print the data of the current node.
   * Step 7.	Move to the next node using the next pointer.
 
## Program:
```C
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the structure for a node
struct Node {
    int data;
    struct Node* next;
};

// Step 2: Declare global head pointer
struct Node* head = NULL;

// Function to push an element onto the stack
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed\n");
        return;
    }
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

// Step 3: Define the display function
void display() {
    struct Node* p = head;
    
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements are:\n");
    // Step 5: Traverse and print
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main() {
    // Pushing some elements to the stack
    push(10);
    push(20);
    push(30);
    push(40);

    // Display stack elements
    display();

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/5ee63bba-32fb-4561-ad30-248c21a0293d)


## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



# EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
   * Step 1.	Check for Empty Stack
   * Step 2.	If head is equal to NULL, Print "Stack is empty."
   * Step 3.	Else Proceed to the next step.
   * Step 4.	Set head to point to the next node in the stack.
 
## Program:
```C
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the structure for a node
struct Node {
    int data;
    struct Node* next;
};

// Global head pointer
struct Node* head = NULL;

// Function to push an element onto the stack
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed\n");
        return;
    }
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

// Function to pop an element from the stack
void pop() {
    // Step 1 & 2: Check if stack is empty
    if (head == NULL) {
        printf("Stack is empty. Cannot pop.\n");
        return;
    }

    // Step 4: Pop the element
    struct Node* temp = head;
    printf("Popped element: %d\n", temp->data);
    head = head->next;
    free(temp);
}

// Function to display stack elements
void display() {
    struct Node* p = head;
    
    if (p == NULL) {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements are:\n");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main() {
    // Push some elements
    push(10);
    push(20);
    push(30);
    push(40);

    // Display current stack
    display();

    // Pop elements
    pop();
    pop();

    // Display updated stack
    display();

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/74d9fe1d-2911-45a9-8407-d4655d1c40cd)




## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
# EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.
## Algorithm:
   * Step 1.	Check if Queue is Empty
   * Step 2.	Display Queue Elements
   * Step 3.	Print the data of the current node pointed to by front
   * Step 4.	Update front to point to the next node.
   * Step 5.	End the display function.
 
## Program:
```C
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the structure for a node
struct Node {
    int data;
    struct Node* next;
};

// Global pointers for front and rear
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to enqueue (insert) an element into the queue
void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed\n");
        return;
    }
    newNode->data = value;
    newNode->next = NULL;
    
    if (rear == NULL) { // Queue is empty
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

// Step 2: Function to display queue elements
void display() {
    // Step 1: Check if Queue is Empty
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }

    struct Node* temp = front;
    printf("Queue elements are:\n");
    
    // Step 2-4: Traverse and print
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next; // Step 4: Update to next node
    }
    printf("\n");
}

int main() {
    // Insert some elements into the queue
    enqueue(5);
    enqueue(10);
    enqueue(15);
    enqueue(20);

    // Display the queue
    display();

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/023be544-c855-428b-bd47-80397eb88bfc)

## Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
# EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
   * Step 1.	Allocate Memory for New Node
   * Step 2.	Set Data and Next Pointer
   * Step 3.	Check if Queue is Empty
   * Step 4.	Set both front and rear to point to the new node p.
   * Step 5.	Set the next pointer of the current rear to point to the new node p.
   * Step 6.	End of Enqueue Operation
 
## Program:
```C
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the structure for a node
struct Node {
    int data;
    struct Node* next;
};

// Global pointers for front and rear
struct Node* front = NULL;
struct Node* rear = NULL;

// Step 1 to Step 6: Function to insert (enqueue) elements in the queue
void enqueue(int value) {
    // Step 1: Allocate Memory for New Node
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    if (p == NULL) {
        printf("Memory allocation failed\n");
        return;
    }

    // Step 2: Set Data and Next Pointer
    p->data = value;
    p->next = NULL;

    // Step 3: Check if Queue is Empty
    if (rear == NULL) {
        // Step 4: Set both front and rear to point to p
        front = rear = p;
    } else {
        // Step 5: Set the next pointer of the current rear to p
        rear->next = p;
        rear = p;
    }
}

// Function to display the queue (for verification)
void display() {
    struct Node* temp = front;
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements are:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();

    return 0;
}

```
## Output:

![image](https://github.com/user-attachments/assets/9f8cdbf4-a1ec-4d77-bec5-4220eecdccbd)


## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



# EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:
   * Step 1.	Check if the queue is empty:
      - If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
   * Step 2.	Access the front element:
      - If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:
```C
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the structure for a node
struct Node {
    int data;
    struct Node* next;
};

// Global pointers for front and rear
struct Node* front = NULL;
struct Node* rear = NULL;

// Function to insert (enqueue) elements into the queue
void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    if (p == NULL) {
        printf("Memory allocation failed\n");
        return;
    }
    p->data = value;
    p->next = NULL;
    
    if (rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

// Step 2: Function to peek at the front element
int peek() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return -1;  // Returning -1 as an indicator of empty queue
    } else {
        return front->data;
    }
}

// Function to display queue elements
void display() {
    struct Node* temp = front;
    if (temp == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements are:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    enqueue(5);
    enqueue(15);
    enqueue(25);

    display();

    // Peek the front element
    int front_element = peek();
    if (front_element != -1)
        printf("Peek (Front Element) of Queue: %d\n", front_element);

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/53813477-e8ae-47d2-bb12-5e17e0e22c36)

## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


