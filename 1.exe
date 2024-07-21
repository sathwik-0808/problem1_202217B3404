#include <stdio.h>
#include <stdlib.h>
 
#define MAX_SIZE 100
 
typedef struct {
    int data[MAX_SIZE];
    int count;
} List;
 
void insert(List *list, int element, int position);
void delete(List *list, int element);
void display(List *list);
int search(List *list, int element);
int main() {
    List list;
    list.count = 0;
 
    int choice, element, position;
 
    while (1) {
        printf("\n1. Insert\n2. Delete\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
 
        switch (choice) {
            case 1:
                printf("Enter the element to insert: ");
                scanf("%d", &element);
                printf("Enter the position to insert the element (1-based index): ");
                scanf("%d", &position);
                insert(&list, element, position);
                break;
            case 2:
                printf("Enter the element to delete: ");
                scanf("%d", &element);
                delete(&list, element);
                break;
            case 3:
                display(&list);
                break;
            case 4:
                exit(0);
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }
 
    return 0;
}
void insert(List *list, int element, int position) {
    if (list->count == MAX_SIZE) {
        printf("List is full. Cannot insert element.\n");
        return;
    }
 
    if (position < 1 || position > list->count + 1) {
        printf("Invalid position. Please enter a position between 1 and %d.\n", list->count + 1);
        return;
    }
 
    for (int i = list->count; i >= position; i--) {
        list->data[i] = list->data[i - 1];
    }
 
    list->data[position - 1] = element;
    list->count++;
    printf("Element inserted successfully.\n");
}
void delete(List *list, int element) {
    if (list->count == 0) {
        printf("List is empty. Cannot delete element.\n");
        return;
    }
 
    int index = search(list, element);
    if (index == -1) {
        printf("Element not found in the list.\n");
        return;
    }
 
    for (int i = index; i < list->count - 1; i++) {
        list->data[i] = list->data[i + 1];
    }
 
    list->count--;
    printf("Element deleted successfully.\n");
}
void display(List *list) {
    if (list->count == 0) {
        printf("List is empty.\n");
        return;
    }
 
    printf("List elements: ");
    for (int i = 0; i < list->count; i++) {
        printf("%d ", list->data[i]);
    }
    printf("\n");
}
int search(List *list, int element) {
    for (int i = 0; i < list->count; i++) {
        if (list->data[i] == element) {
            return i;
        }
    }
    return -1;
}