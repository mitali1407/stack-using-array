# stack-using-array

Stack is a linear Data Structure. It can perform two operations: Push and Pop
PUSH function in the code is used to insert an element to the top of stack, POP function used to remove the element from the top of stack.

Adding an element onto the stack (push operation)
Adding an element into the top of the stack is referred to as push operation. Push operation involves following two steps.

Increment the variable Top so that it can now refere to the next memory location.
Add element at the position of incremented top. This is referred to as adding new element at the top of the stack.
Stack is overflown when we try to insert an element into a completely filled stack therefore, our main function must always avoid stack overflow condition.

Deletion of an element from a stack (Pop operation)
Deletion of an element from the top of the stack is called pop operation. The value of the variable top will be incremented by 1 whenever an item is deleted from the stack. The top most element of the stack is stored in an another variable and then the top is decremented by 1. the operation returns the deleted value that was stored in another variable as the result.

The underflow condition occurs when we try to delete an element from an already empty stack.

![image](https://user-images.githubusercontent.com/110607289/221881530-7dcb9bf1-eb8c-4b41-a0bf-fe86703c1a51.png)


The following code is used:
#include <stdio.h>
#include <stdlib.h> 
void push();
void pop();
void display();

int top=-1;
int array[10];

int main()
{

int choice=1;
	while (choice==1 || choice==2 || choice==3)
		{
			printf(" \n Enter the no. of function to be performed \n 1.Push 2. Pop 3. Display 4.Exit \n");
			scanf("%d",&choice);
			if (choice==1)
			{
				push();
			}
			else if (choice==2)
			{
				pop();
			}
			else if (choice==3)
			{
				display();
			}
			else
			{
				break;
			}
		}
		
}
void push()
{
	int data;
	if (top==9)
	{
		printf("Overflow");
	}
	else
	{
		printf("Enter data : \n");
		scanf("%d",&data);
		top=top+1;
		array[top]=data;
		printf("\n The updated Array is \n");
		display();
	}
    	
}
void pop()
{
	if (top==-1)
	{
		printf("Underflow");
	}
	else
	{
	top=top-1;	
	}	
		
}
void display()
{
	if (top==-1)
	{
		printf("Stack is empty");
	}
	else
	{
		int i;
		for (i=0;i<=top;i++)
		{
			printf(" \n %d \n", array[top-i]);	
		}
	}
	
	
}



