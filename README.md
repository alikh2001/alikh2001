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
Q-1)Declare a calendar as an array of 7 ement's to represent 7 days of a weeks. each element of the anay in a structure having a field's
1) Name of the day
2) Date of the day
3) Description of the activity for particular day.
#include<stdio.h>
#include<string.h>
//difine a structer to represnt a day
struct Day{
int date;
char activity[100];
};
//function to creat the calender
void creat(struct Day calender[7]){
for(int i=0;i<7;i++){
printf("Enter detel for %\n",calender[i].name);
printf("Date:");
scanf("%d",&calender[i].date);
printf("Activity:");
scanf("%[\n]",calender[i].activity);
}
}
//function to read data from the keyboard
voi read(struct Day calender[7]0{
fILE*file=fopen("calender.txt","r");
if(file=NULL){
printf("Error opening the file./n");
return;
}
for(int i =0;i<7;i++){
printf("%s(date:%d):%s\n",calender[i].name,calender[i].date/calender[i].activity);
}
}
int main(){
struct Day calender[7];
   Initialize the names of the days
   strcpy calender[0].name,"Monday");
   strcpy calender[1].name,"tuesday");
   strcpy calender[2].name,"wednesday");
   strcpy calender[3].name,"thursday");
   strcpy calender[4].name,"friday");
   strcpy calender[5].name,"saturday");
   strcpy calender[6].name,"sunday");
   int choice;
   printf("1.creat calender\N");
   printf("2Read calender from File\n");
   printf("Enter your choice:);
   scanf("%d',&choice);
   switch(choice0[
   case 1:
   creat(calender);
   break;
   case 2;
   read(calender);
   break:
   defult:
   printf("Invalid choice.\n");
   return 0;
   }

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

   
//Q-2)Design and implement a Program in c for the following operations on strings.
//i) read a string 
//ii) read a Paltem string (PTR) 
//iii) read a replacement string (REP) Perform Patter mana-
//ging operations find and replace all occurance's Pattern string in the main sting with the replacement string. report suitable message in case pattern string not exist

#include<stdio.h>
#include<string.h>
int main()
{
int i=0,j=0,k=0,c=0,m=0,flag=0;
char str[100],pat[20],rep[20],rstr[100];
printf("Enter any string :\t");
gets(str);
printf("Enter character to replace:\t");
gets(pat); 
printf("Enter character to replace '%s'with:\t",pat);
gets(rep); 
printf("\n String before replacing\n \%s\n",str);
while(str[i]!='\0')
{
if(str[m]==pat[j])
{ 
j++;m++;
if(pat[j]=='\0') 
{
flag=1; 
for(k=0;rep[k]!='\0';k++,c++)
{
rstr[c]=rep[k]; 
}
i=m;j=0;
}
}
else
{
rstr[c]=str[i];
c++; i++; m=i; j=0;
}
rstr[c]='\0'; 
if(flag== 1)
{
printf("String after replacing\n %s \n",rstr);
}
else
{
printf("Not found");
}
}
return 0;
}

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

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

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

//Q-4)Design, develop and implement a Program in c for Converting an infix expression to Postfix expression Program should oom for both paren theses and non Parenthesre with operators +,-,*,/,%, along cuith alpha //numeric operations.

#include<stdio.h>
#include<string.h>
#include<conio.h>
int F(char symbol)
{
switch(symbol)
{
case '+':
case '-': return 2;
case '*':
case '/':
case '%': return 4;
case '^':
case '$': return 5;
case '(': return 0;
case '#': return-1;
default : return 8;
}
}
int G(char symbol)
{
switch(symbol)
{
case '+':
case '-': return 1;
case '*':
case '/':
case '%': return 3;
case '^':
case '$': return 6;
case '(': return 9;
case ')': return 0;
default : return 7;
}
}
void infix_postfix(char infix[],char postfix[])
{
int top =-1,i,j;
char symbol,s[30];
s[++top]='#';
j=0;
for(i=0;i<strlen(infix);i++)
{
symbol=infix[i];
while(F(s[top])>G(symbol))
{
postfix[j++]=s[top--];
}
if(F(s[top])!=G(symbol))
s[++top]=symbol;
else
top--;
} 
while(s[top]!= '#')
{
postfix[j++]=s[top--];
}
postfix[j]='\0';
}
int main()
{
char infix[20],postfix[20]; 
printf("Enter the Infix Expression:\n"); 
scanf("%s", infix); infix_postfix(infix,postfix); 
printf("The Post Expression is:\n"); printf("%s\n",postfix);
getch();
}

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

//Q-5)Develop and implement a program in c for counting an infix expression to Prefix expression Program should with for both Paranchaled and non partanthesis expression with operation '+','-','','/','%'& pow() operators //along with alphanumeric operands.

#include<stdio.h>
#include<math.h>
#include<string.h>
#include<conio.h>
double compute(char symbol,double op1,double op2)
{
	switch(symbol)
	{
		case'+': return(op1+op2);
		case'-': return(op1-op2);
		case'*': return(op1*op2);
		case'/': return(op1/op2);
		case'%': return(abs(op1)%abs(op2));
		case'^': return pow(op1,op2);
	}
	return 0;
}
int main()
{
	double s[20];
	double res;
	double op1;
	double op2;
	int top;
	int i;
	char postfix[20];
	char symbol;
	printf("enter the postfix expression\n");
	scanf("%s",postfix);
	top=-1;
	for (i=0;i<strlen(postfix);i++)
	{
		symbol=postfix[i];
		if(isdigit(symbol))
		{
			s[++top]=symbol-'0';
		}
		else
		{
			op2=s[top--];
			op1=s[top--];
			res=compute(symbol,op1,op2);
			s[++top]=res;
		}
	}
	     res=s[top--];
	     printf("the result is %f\n",res);
	     return 0;
 }

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

// Q-6)Design develop and implentent a menu draven. Program in c, for the following operations on corular quede of characters Carray implementation of queue
//with maximum size max
//a) insert an element on to circular queue
//b) delete an exement from a caraular queue demonstrate overflow and underflow situations. on cardar queue
//d). display the states of Grcular queue
//e) exit

#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
#define size 5
int item,queue[size];
int front=-1,rear=-1;
void add()
{
if(front==(rear+1)%size)
{
printf("\n The circular Queue is full");
}
else
{
printf("\nEnter the element:");
scanf("%d",&item);
if(front==-1)
{
front=rear=0;
}
else
{ 
rear=(rear+1)%size;
}
queue[rear]=item;
}
}
void del()
{ 
if(front==-1)
{
printf("\n The Queue is empty\n");
}
else
{
item= queue[front]; 
if(front==rear)
front=rear=-1;
else
front=(front+1)%size;
printf("\n The deleted item %d", item);
}
} 
void disp()
{
int i; 
if(front==-1)
{
printf("\nThe Queue is empty");
return;
}
i=front; 
while(i!=rear)
{ 
printf("%d\t",queue[i]);
i=(i+1)%size;
} 
printf("%d\t",queue[i]);
}
int main()
{
int choice;
for(;;)
{
printf("\n MENU ");
printf("\n1.Insert\n2. Delet\n3. Display\n4.Exit");
printf("\nEnter your choice:\t");
scanf("%d",&choice);
switch(choice)
{
case 1:add(); 
break; 
case 2:del(); 
break; 
case 3:disp(); 
break; 
case 4:exit(0); 
break; 
default:printf("Invalid choice"); 
}
}
return 0;
}
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

7.	singly linklist

#include<stdio.h>
#include<stdlib.h>
#include<string.h>

typedef struct node {
    int usn;
    char name[20];
    char branch[20];
    int semester;
    char phone[20];
    struct node *link;
} NODE;

NODE* getnode() {
    NODE* X = malloc(sizeof(NODE)); 
    if (X == NULL) {
printf("out of memory\n");
exit(0);
    }
    return X;
}

NODE* insert_front(int usn, char name[], char branch[], int semester, char phone[], NODE* first) {
    NODE* temp = getnode();
    temp->usn = usn;
strcpy(temp->name, name);
strcpy(temp->branch, branch);
    temp->semester = semester;
strcpy(temp->phone, phone);
    temp->link = first;
    return temp;
}

NODE* insert_rear(int usn, char name[], char branch[], int semester, char phone[], NODE* first) {
    NODE* temp = getnode();
    temp->usn = usn;
strcpy(temp->name, name);
strcpy(temp->branch, branch);
    temp->semester = semester;
strcpy(temp->phone, phone);
    temp->link = NULL;
    if (first == NULL)
        return temp;
    NODE* cur = first;
    while (cur->link != NULL) 
        cur = cur->link;
    cur->link = temp;
    return first;
}

NODE* delete_front(NODE* first) {
    if (first == NULL) {
printf("student list is empty\n");
        return NULL;
    }
    NODE* temp = first;
printf("delete student record: USN=%d\n", temp->usn);
    first = first->link;
    free(temp);
    return first;
}

NODE* delete_rear(NODE* first) {
    if (first == NULL) {
printf("student list is empty\n");
        return NULL;
    }
    NODE* cur = first;
    NODE* prev = NULL;
    while (cur->link != NULL) {
prev = cur;
        cur = cur->link;
    }
printf("delete student record: USN=%d\n", cur->usn);
    if (prev == NULL)
        first = NULL;
    else
prev->link = NULL;
    free(cur);
    return first;
}

void display(NODE* first) {
    int count = 0;
    if (first == NULL) {
printf("student list is empty\n");
        return;
    }
    NODE* cur = first;
    while (cur != NULL) {
printf("%d\t%s\t%s\t%d\t%s\n", cur->usn, cur->name, cur->branch, cur->semester, cur->phone);
        cur = cur->link;
        count++;
    }
printf("number of students=%d\n", count);
}

name, branch, int main() {
    NODE* first = NULL;
    int choice, usn, semester;
    char name[20], branch[20], phone[20];
    while (1) {
printf("1.insert_front 2.insert_rear 3.delete_front 4.delete_rear 5.display 6.exit\n");
printf("Enter the choice: ");
scanf("%d", &choice);
        switch (choice) {
            case 1:
printf("USN: "); scanf("%d", &usn);
printf("Name: "); scanf("%s", name);
printf("Branch: "); scanf("%s", branch);
printf("Semester: "); scanf("%d", &semester);
printf("Phone: "); scanf("%s", phone);
                first = insert_front(usn, name, branch, semester, phone, first);
                break;
            case 2:
printf("USN: "); scanf("%d", &usn);
printf("Name: "); scanf("%s", name);
printf("Branch: "); scanf("%s", branch);
printf("Semester: "); scanf("%d", &semester);
printf("Phone: "); scanf("%s", phone);
                first = insert_rear(usn, semester, phone, first);
                break;
            case 3:
                first = delete_front(first);
                break;
            case 4:
                first = delete_rear(first);
                break;
            case 5:
                display(first);
                break;
            case 6:
exit(0);
            default:
printf("Invalid choice\n");
        }        }
    return 0;
}


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


8  doubly linked list
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct Enode {
    char ssn[50];
    char name[20];
    char dept[5];
    char destination[10];
    int salary;
    int phno;
    struct Enode *next;
};

struct Enode *head = NULL, *tail = NULL;

void create(char[], char[], char[], char[], int, int);
void display();
void insert(char[], char[], char[], char[], int, int, int);
void delete(int);

int main() {
    int choice;
    char s[15], n[20], dpt[5], des[10];
    int sal, p;

printf("1. Create\n2. Display\n3. Insert at beginning\n4. Insert at end\n5. Delete at beginning\n6. Delete at end\n7. Exit\n");

    while (1) {
printf("\nEnter your choice: ");
scanf("%d", &choice);

        switch (choice) {
            case 1:
printf("Enter the required data (emp no, name, dept, desig, sal, phone): ");
scanf("%s%s%s%s%d%d", s, n, dpt, des, &sal, &p);
create(s, n, dpt, des, sal, p);
                break;
            case 2:
display();
                break;
            case 3:
            case 4:
printf("Enter the required data (emp no, name, dept, desig, sal, phone): ");
scanf("%s%s%s%s%d%d", s, n, dpt, des, &sal, &p);
insert(s, n, dpt, des, sal, p, choice);
                break;
            case 5:
            case 6:
                delete(choice);
                break;
            case 7:
exit(0);
            default:
printf("Invalid choice!\n");
        }     }
    return 0;    }

void create(char s[], char n[], char dpt[], char des[], int sal, int p) {
    struct Enode *newNode = (struct Enode*)malloc(sizeof(struct Enode));
strcpy(newNode->ssn, s);
strcpy(newNode->name, n);
strcpy(newNode->dept, dpt);
strcpy(newNode->destination, des);
newNode->salary = sal;
newNode->phno = p;
newNode->next = NULL;

    if (head == NULL) {
        head = newNode;
        tail = newNode;
    } else {
        tail->next = newNode;
	        tail = newNode;
    }     }

void display() {
    struct Enode *temp = head;
printf("Employee details:\n");
    while (temp != NULL) {
printf("%s\t%s\t%s\t%s\t%d\t%d\n", temp->ssn, temp->name, temp->dept, temp->destination, temp->salary, temp->phno);
        temp = temp->next;
    }    }

void insert(char s[], char n[], char dpt[], char des[], int sal, int p, int choice) {
    struct Enode *newNode = (struct Enode*)malloc(sizeof(struct Enode));
strcpy(newNode->ssn, s);
strcpy(newNode->name, n);
strcpy(newNode->dept, dpt);
strcpy(newNode->destination, des);
newNode->salary = sal;
newNode->phno = p;
newNode->next = NULL;

    if (choice == 3) {
newNode->next = head;
        head = newNode;
    } else if (choice == 4) {
        tail->next = newNode;
        tail = newNode;
    }   }

void delete(int choice) {
    if (head == NULL)
        return;

    struct Enode *temp = head;
    if (choice == 5) {
        head = head->next;
        free(temp);
    } else if (choice == 6) {
        if (head == tail) {
            free(head);
            head = NULL;
            tail = NULL;
            return;
        }

        while (temp->next != tail) {
            temp = temp->next;
            }
        free(tail);
        tail = temp;
        tail->next = NULL;
    }     }


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


10  Binary search tree
#include <stdio.h>
#include <stdlib.h>

struct BST {
    int data;
    struct BST *lchild;
    struct BST *rchild;
};

typedef struct BST *NODE;

NODE create(int value) {
    NODE temp = malloc(sizeof(struct BST));
    temp->data = value;
    temp->lchild = NULL;
    temp->rchild = NULL;
    return temp;
}

void insert(NODE root, int value) {
    if (value < root->data) {
        if (root->lchild == NULL)
            root->lchild = create(value);
        else
            insert(root->lchild, value);
    } else {
        if (root->rchild == NULL)
            root->rchild = create(value);
        else
            insert(root->rchild, value);
    }   }

void search(NODE root, int key) {
    while (root != NULL && root->data != key) {
        if (key < root->data)
            root = root->lchild;
        else
            root = root->rchild; }

    if (root == NULL)
printf("\nKey element is not found in the BST");
    else
printf("\nKey element is present in BST");}

void inorder(NODE root) {
    if (root != NULL) {
inorder(root->lchild);
printf("%d ", root->data);
inorder(root->rchild); }}

int main() {
    int ch, key, i, n, value;
    NODE root = NULL;
    while (1) {
printf("\n---BST MENU---");
printf("\n1.Create a BST");
printf("\n2.Inorder Traversal");
printf("\n3.Search");
printf("\n4.Exit");
printf("\nEnter your choice: ");
scanf("%d", &ch);
        switch (ch) {
            case 1:
printf("\nEnter the number of elements: ");
scanf("%d", &n);
printf("Enter elements:\n");
                for (i = 0; i < n; i++) {
scanf("%d", &value);
                    if (root == NULL)
                        root = create(value);
                    else
insert(root, value);
                }
                break;
            case 2:
                if (root == NULL)
printf("\nTree Is Not Created");
                else {
printf("\nInorder display: ");
inorder(root);  }
                break;
            case 3:
                if (root == NULL)
printf("\nTree Is Not Created");
                else {
printf("\nEnter the element to search: ");
scanf("%d", &key);
search(root, key);
                }
                break;
            case 4:
exit(0);
            default:
printf("\nPlease enter valid choice:");
        }     }
    return 0;}


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


11   Graph of cities
#include <stdio.h>
#include <stdlib.h>

#define MAX 50

int a[MAX][MAX], n, visited[MAX];
int q[MAX], front = -1, rear = -1;
int s[MAX], top = -1, count = 0;

void bfs(int v) {
    visited[v] = 1;
    q[++rear] = v;
    while (front != rear) {
        int cur = q[++front];
        for (int i = 1; i <= n; i++) {
            if (a[cur][i] == 1 && visited[i] == 0) {
                q[++rear] = i;
                visited[i] = 1;
printf("%d ", i);
            } }   }    }

void dfs(int v) {
    visited[v] = 1;
    s[++top] = v;
    for (int i = 1; i <= n; i++) {
   if (a[v][i] == 1 && visited[i] == 0) {
printf("%d ", i);
dfs(i); }   }    }

int main() {
    int ch, start;
printf("\nEnter the number of vertices in graph: ");
scanf("%d", &n);
printf("\nEnter the adjacency matrix:\n");
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= n; j++) {
scanf("%d", &a[i][j]);
        }   }
    for (int i = 1; i <= n; i++) visited[i] = 0;
printf("\nEnter the starting vertex: ");
scanf("%d", &start);
printf("\n1. BFS: Print all nodes reachable from a given starting node");
printf("\n2. DFS: Print all nodes reachable from a given starting node");
printf("\n3. Exit"); 
printf("\nEnter your choice: ");
scanf("%d", &ch);
switch(ch) {
        case 1:
printf("\nNodes reachable from starting vertex %d are: ", start);
bfs(start);
            for (int i = 1; i <= n; i++) {
                if (visited[i] == 0) printf("\nThe vertex that is not reachable is %d", i);
            }
            break;
        case 2:
printf("\nNodes reachable from starting vertex %d are:\n", start);
dfs(start);
            break;
        case 3:
exit(0);
        default:
printf("\nPlease enter a valid choice.");
    }
    return 0;}


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


12 Employee hash table
#include<stdio.h>
#include<stdlib.h>
int n, m, count = 0;
int *ht;

void insert(int key) {
    int index = key % m;
    while (ht[index] != -1) index = (index + 1) % m;
ht[index] = key;
    count++;}

void display() {
printf("\nHash Table contents are:\n");
    for (int i = 0; i < m; i++) printf("T[%d] --> %d\n", i, ht[i]);}

int main() {
printf("\nEnter the number of employee records (N): ");
scanf("%d", &n);
printf("\nEnter the two-digit memory locations (m) for hash table: ");
scanf("%d", &m);
ht = (int*)malloc(m * sizeof(int));
    for (int i = 0; i < m; i++) ht[i] = -1;
printf("\nEnter the four-digit key values (K) for %d Employee Records: \n", n);
    for (int i = 0; i < n; i++) {
        int key;
scanf("%d", &key);
        if (count == m) {
printf("\nHash table is full. Cannot insert the record %d key", i + 1);
break; }
        insert(key); }
display();
    return 0;}
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
