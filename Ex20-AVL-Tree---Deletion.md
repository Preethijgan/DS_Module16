# Ex20 AVL Tree - Deletion
## DATE:
## AIM:
To write a C function to delete an element from an AVL Tree.
## Algorithm
1.	Search for the node to delete starting fromthe root.
2.	Delete the node using standard BST rules.
3.	Updatethe height of the affected nodes.
4.	Calculate the balance factor of each updated node.
5.	Perform rotations if the node is unbalanced.
6.	Continue until the tree is balanced again


## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by:  Preethi J
RegisterNumber: 212223220080 
*/
```
```
node * Delete(node *T,int x)
{
node *p; if(T==NULL)
{
return NULL;
}
else
if(x > T->data) // insert in right subtree
{
T->right=Delete(T->right,x); if(BF(T)==2)
{
if(BF(T->left)>=0) T=LL(T);
else T=LR(T);
}}
else
if(x<T->data)
{
T->left=Delete(T->left,x);
if(BF(T)==-2) //Rebalance during windup
{
if(BF(T->right)<=0) T=RR(T);
else T=RL(T);
}}
else
 
{
//data to be deleted is found if(T->right!=NULL)
{ //delete its inorder succesor p=T->right;
while(p->left!= NULL) p=p->left;
T->data=p->data;
T->right=Delete(T->right,p->data); if(BF(T)==2)//Rebalance during windup
{
if(BF(T->left)>=0) T=LL(T);
else T=LR(T);}}
else
return(T->left);
}
T->ht=height(T); return(T);
}



```
## Output:
![image](https://github.com/user-attachments/assets/439aa1ad-028a-4120-846d-9056b1f1951e)




## Result:
Thus, the C program to delete an element from an AVL Tree is implemented successfully.
