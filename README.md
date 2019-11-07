# standard-codes
coding questions and answers 

IN C LANGUAGE

Given a linked list of N nodes. The task is to check if the the linked list has a loop. Linked list can contain self loop.

Input:
First line of input contains number of testcases T. For each testcase, first line of input contains length of linked list and next line contains the data of linked list.

Output:
For each testcase, print "True", if linked list contains loop, else print "False".

User Task:
The task is to complete the function detectloop() which contains reference to the head as only argument. This function should return 1 if linked list contains loop, else return 0.

Constraints:
1 <= T <= 50
1 <= N <= 300

Example:
Input:
2
3
1 3 4
2
4
1 8 3 4
0

Output:
True
False

Explaination:
Testcase 1: In above test case N = 3. The linked list with nodes N = 3 is given. Then value of x=2 is given which means last node is connected with xth node of linked list. Therefore, there exists a loop. 

Testcase 2: For N = 4
x = 0 means then lastNode->next = NULL, then the Linked list does not contains any loop.



ANSWER CODE:
int detectloop(Node *head) {
    
    // your code here
    struct Node *list=head;
    if(list==NULL)
{ return 0;
}
else
{
int ct=0;
while(ct<=300)
{
if(list==NULL)
{
return 0;
}
list = list->next;
ct++;
}
return 1;
}
    
}



////////////////////////////////////////////////////////
Given a linked list consisting of L nodes and given a number N. The task is to find the Nth node from the end of the linked list.

Input:
First line of input contains number of testcase T. For each testcase, first line of input contains number of nodes in the linked list and the number N. Next line contains N nodes of linked list.

Output:
For each testcase, output the data of node which is at Nth distance from end.

User Task:
The task is to complete the function getNthFromLast() which takes two arguments: reference to head and N and you need to return Nth from end.

Constraints:
1 <= T <= 200
1 <= L <= 103
1 <= N <= 103

Example:
Input:
2
9 2
1 2 3 4 5 6 7 8 9
4 5
10 5 100 5

Output:
8
-1
Explanation:
Testcase 1: In the first example, there are 9 nodes in linked list and we need to find 2nd node from end.  2nd node from end os 8.  
Testcase 2: In the second example, there are 4 nodes in linked list and we need to find 5th from end.  Since 'n' is more than number of nodes in linked list, output is -1.

CODE:--

int getNthFromLast(Node *head, int n)
{
       Node *ptr,*last;
ptr=head;
last=head;
int len = 0;
while(last!=NULL)
{
last=last->next;
len++;
}
if(n>len)
return -1;

int respos = len - n;
while(respos!=0)
{
ptr=ptr->next;
respos--;
}
return (ptr->data);
}
