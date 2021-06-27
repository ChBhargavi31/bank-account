#include<stdio.h>
struct customer
{
int account_no;
char name[80];
int balance;
};
void accept(struct customer[],int);
void display(struct customer[],int);
int search(struct customer[],int,int);
void deposit(struct customer[],int,int,int);
void withdraw(struct customer[],int,int,int);
int main()
{
struct customer data[20];
int n,choice,account_no,amount,index;
printf("banking system\n");
printf("number of customer records you want to enter?:");
scanf("%d",&n);
accept(data,n);
do
{
printf("\n banking system menu:");
printf("press 1 to display all records\n");
printf("press 2 to search a record\n");
printf("press 3 to deposit amount\n");
printf("press 4 to withdraw amount\n");
printf("press 0 to exit\n");
printf("enter choice(0-4):");
scanf("%d",&choice);
switch(choice)
{
case 1:
      display(data,n);
      break;
case 2:
     printf("enter account number to search :");
     scanf("%d",&account_no);
     index=search(data,n,account_no);
     if(index==-1)
     {
     printf("record not found:");
     }
     else
     {
     printf("A/c number:%d\nname:%s\nBalance:%d:");
     data[index].account_no,data[index].name,data[index].balance);
     }
     break;
case 3:
     printf("enter account number:");
     scanf("%d",&account_no);
     printf("enter amount to deposit:");
     scanf("%d",&amount);
     deposit(data,n,account_no,amount);
     break;
case 4:
     printf("enter account number:");
     scanf("%d",&account_no);
     printf("enter amount to withdraw:");
     scanf("%d",&amount);
     withdraw(data,n,account_no,amount);
     }
     }
     while(choice!=0);
     return 0;
     }
     void accept(struct customer list[80],int s)
     {
     int i;
     for(i=0;i<s;i++)
