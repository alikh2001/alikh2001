- 👋 Hi, I’m @alikh2001
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
alikh2001/alikh2001 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
//quetion number 3:- design develop and implement a men driven program in c for the following in stack of int.//
//1)push element stack 
//2)pop an element stack from the stack
//3)demostrate how stack can be used to chack palindrome
//4)demanstrate overslow,underflow
//5)display states of a stack

#include<stdio.h>
#include<stdlib.h>
#define SIZE 4
int stk[SIZE],rev[SIZE],top=-1;
void push()
{
int item;
if(top==SIZE-1)
{
printf("Stack Overflow");
}
else
{
printf("Enter the Element to Push\n");
scanf("%d",&item);
top++;
stk[top]= item;
}
}
void pop()
{
if(top==1)
{ 
printf("Stack Underflow");
}
else
{
printf("Poped element is %d", stk [top]);
top--;
}
}
void display()
{
int i;
if(top==-1)
{
printf("Stack is Empty");
}
else
{
printf("Elements in STACK are \n");
for(i=0;i<=top;i++)
{
printf("%d\t",stk[i]);
}
}
}
void palindrome()
{
int i,count=-1,j=1;
if(top==-1)
{
printf("stack is empty");
}
else
{
for(i=top;i>=0;i--)
{
j++;
rev[j]=stk[i];
}
for(i=0;i<=top;i++)
{
if(stk[i]==rev[i])
{
count++;
}
}

if(count==top)
{
printf("\tStack is Palindrome");
}
else
{
printf("\tStack is not Palindrome"); 
}
}
}
int main()
{
int choice;
while(1)
{
printf("\n\n---MENU---"); 
printf("\n1.Push"); 
printf("\n2.Pop"); 
printf("\n3.Display"); 
printf("\n4.Palindrome"); 
printf("\n5.exit"); 
printf("\nEnter your choice:\t"); 
scanf("%d",&choice);
switch(choice)
{
case 1: push(); 
break;
case 2: pop(); 
break;
case 3: display();
break;
case 4: palindrome();
break;
case 5: exit(0);
break;
default :printf("\tInvalid Chioce");
}
}
return 0;
}
