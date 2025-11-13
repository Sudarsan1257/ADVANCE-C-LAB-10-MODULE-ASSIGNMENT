# ADVANCE-C-LAB-10-MODULE-ASSIGNMENT
## EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST. 
## Aim: 
To write a C program to search a given element in the given linked list.

## Algorithm:

Define the structure for a node in a linked list.
Define the search function to find a specific character in the linked list.
Initialize the head of the linked list as needed.
Call the search function and perform other linked list operations as needed.
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node in the linked list
struct Node {
    char data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the end of the linked list
void insertNode(struct Node** head, char data) {
    struct Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}

// Function to search for a specific character in the linked list
int searchElement(struct Node* head, char key) {
    struct Node* temp = head;
    int position = 1;
    while (temp != NULL) {
        if (temp->data == key) {
            return position;  // Element found
        }
        temp = temp->next;
        position++;
    }
    return -1;  // Element not found
}

// Function to display the linked list
void displayList(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Initialize linked list with some characters
    insertNode(&head, 'A');
    insertNode(&head, 'B');
    insertNode(&head, 'C');
    insertNode(&head, 'D');
    insertNode(&head, 'E');

    printf("Linked List: ");
    displayList(head);

    char key;
    printf("Enter the element to search: ");
    scanf(" %c", &key);

    int result = searchElement(head, key);
    if (result != -1) {
        printf("Element '%c' found at position %d.\n", key, result);
    } else {
        printf("Element '%c' not found in the linked list.\n", key);
    }

    return 0;
}

```

## Output:
<img width="577" height="269" alt="image" src="https://github.com/user-attachments/assets/1654909c-772b-455f-b541-26ad94bde637" />


## Result:
Thus, the program to search a given element in the given linked list is verified successfully.

## EXP NO:17 PROGRAM TO INSERT A NODE IN A LINKED LIST. 
## Aim: To write a C program to insert a node in a linked list.
## Algorithm:

Define the structure for a node in a linked list
Define the insert function to insert a new node with character data at the end of the linked list.
Initialize the head of the linked list as needed.
Call the insert function and perform other linked list operations as needed.
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node in the linked list
struct Node {
    char data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a new node with character data at the end of the linked list
void insertNode(struct Node** head, char data) {
    struct Node* newNode = createNode(data);

    // If the list is empty, make the new node the head
    if (*head == NULL) {
        *head = newNode;
        return;
    }

    // Otherwise, traverse to the end of the list
    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    // Link the new node at the end
    temp->next = newNode;
}

// Function to display the linked list
void displayList(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;  // Initialize the head of the linked list

    // Insert nodes into the linked list
    insertNode(&head, 'A');
    insertNode(&head, 'B');
    insertNode(&head, 'C');
    insertNode(&head, 'D');

    // Display the linked list
    printf("Linked List after insertion: ");
    displayList(head);

    return 0;
}

```

## Output:
<img width="603" height="287" alt="image" src="https://github.com/user-attachments/assets/6c4fb0e7-2cea-4255-8ed0-d23f88f99e26" />

## Result:
Thus, the program to insert a node in a linked list is verified successfully.

## EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
## Aim: To write a C program to traverse a doubly linked list.

## Algorithm:

Initialize a temporary pointer (temp) to the head of the list.
Use a while loop to traverse the list until the end (temp == NULL) is reached.
Inside the loop, print the data of the current node.
Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node in the doubly linked list
struct Node {
    char data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the end of the doubly linked list
void insertNode(struct Node** head, char data) {
    struct Node* newNode = createNode(data);

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    temp->next = newNode;
    newNode->prev = temp;
}

// Function to traverse and display the doubly linked list
void traverseList(struct Node* head) {
    struct Node* temp = head;

    printf("Traversing the doubly linked list:\n");
    while (temp != NULL) {
        printf("%c <-> ", temp->data);
        temp = temp->next;  // Move to the next node
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Insert nodes into the doubly linked list
    insertNode(&head, 'A');
    insertNode(&head, 'B');
    insertNode(&head, 'C');
    insertNode(&head, 'D');

    // Traverse and display the list
    traverseList(head);

    return 0;
}

```

## Output:
<img width="601" height="236" alt="image" src="https://github.com/user-attachments/assets/debef238-000a-471f-accc-1b489e05f077" />

## Result:
Thus, the program to traverse a doubly linked list is verified successfully.

## EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
## Aim:
To write a C program to insert an element in doubly linked list

## Algorithm:

Create a new node (newNode) and allocate memory for it.
Set the data of the new node to the provided value.
If the list is empty, set the new node as the head.
If the list is not empty, traverse the list to find the last node.
Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node in the doubly linked list
struct Node {
    char data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a new node at the end of the doubly linked list
void insertNode(struct Node** head, char data) {
    struct Node* newNode = createNode(data);

    // If the list is empty, set the new node as the head
    if (*head == NULL) {
        *head = newNode;
        return;
    }

    // Otherwise, traverse to the last node
    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    // Link the new node at the end
    temp->next = newNode;
    newNode->prev = temp;
}

// Function to display the doubly linked list
void displayList(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%c <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;  // Initialize the head of the list

    // Insert elements into the doubly linked list
    insertNode(&head, 'A');
    insertNode(&head, 'B');
    insertNode(&head, 'C');
    insertNode(&head, 'D');

    // Display the list
    displayList(head);

    return 0;
}

```

## Output:
<img width="601" height="293" alt="image" src="https://github.com/user-attachments/assets/317b30fa-90ff-484f-b959-c47b186d5854" />


## Result: 
Thus, the program to insert an element in doubly linked list is verified successfully.

## EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

## Aim:
To write a C function that deletes a given element from a linked list.

## Algorithm:

Check if the Linked List is Empty: o If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
Traverse the Linked List: o Start from the head node and iterate through the list to find the node that contains the given element (data).
Handle Deletion of the First Node: o If the element to be deleted is found in the head node:  Update the head of the linked list to point to the next node (i.e., head = head->next).  Free the memory allocated to the node to be deleted.  Exit the function.
Traverse and Delete from the Middle or End: o If the element is not in the head node, continue traversing the list by checking each node’s next pointer. o When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next). o Free the memory allocated to the node to be deleted.
Handle the Case when the Element is Not Found: o If the element is not found in any node, print a message indicating the element is not present in the list.
End the Function.
## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node in the linked list
struct Node {
    char data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert a node at the end of the linked list
void insertNode(struct Node** head, char data) {
    struct Node* newNode = createNode(data);

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}

// Function to delete a given element from the linked list
void deleteElement(struct Node** head, char key) {
    // Check if the list is empty
    if (*head == NULL) {
        printf("The linked list is empty. Nothing to delete.\n");
        return;
    }

    struct Node* temp = *head;
    struct Node* prev = NULL;

    // Handle deletion of the first node
    if (temp != NULL && temp->data == key) {
        *head = temp->next;  // Update head
        free(temp);          // Free memory
        printf("Element '%c' deleted from the list.\n", key);
        return;
    }

    // Traverse and delete from middle or end
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    // If element not found
    if (temp == NULL) {
        printf("Element '%c' not found in the list.\n", key);
        return;
    }

    // Unlink the node and free memory
    prev->next = temp->next;
    free(temp);
    printf("Element '%c' deleted from the list.\n", key);
}

// Function to display the linked list
void displayList(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Insert elements into the linked list
    insertNode(&head, 'A');
    insertNode(&head, 'B');
    insertNode(&head, 'C');
    insertNode(&head, 'D');

    printf("Linked List before deletion: ");
    displayList(head);

    // Delete an element
    deleteElement(&head, 'C');

    printf("Linked List after deletion: ");
    displayList(head);

    // Try deleting an element not in the list
    deleteElement(&head, 'X');

    return 0;
}

```

## Output:

<img width="578" height="244" alt="image" src="https://github.com/user-attachments/assets/8cbb1555-bd08-4b1a-a771-e688fdfd86b5" />


## Result: 
Thus, the function that deletes a given element from a linked list is verified successfully.
