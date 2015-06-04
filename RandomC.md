## Random C code ##

### Linked list ###
this code creates a linked list and loads it with the index of the for loop. "createNewList" creates a new list with the data values swapped from the first list.

```
#include<stdlib.h>
#include<stdio.h>

struct my_list {
	int value;
	struct my_list * next;
};

typedef struct my_list item;

item* createNewList(item* current);
void print_list(item *current);

int main() {
	item * current, * head;
	int i;
	
	head = NULL;
	/* Loads data into list*/
	for(i=1;i<=10;i++) {
		current = (item *)malloc(sizeof(item));
		current->value = i;
		current->next  = head;
		head = current;
	}

	print_list(current);
	head = createNewList(current);
	current = head;
	print_list(current);
	return 0;
}

/* Creates new list with swapped data and returns the head of newly created list */
item* createNewList(item* current) {
	
	item * head, * reverse;
	head = NULL;
	
	while(current) {		
		reverse = (item *)malloc(sizeof(item));
		reverse->value = current->value;
		reverse->next = head;
		current = current->next;
		head = reverse;
	}
	current = reverse;
	return head;
}

/* Prints list */
void print_list(item *current){
	while(current) {
		printf("%d\n", current->value);
		current = current->next;
	}
}
```