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
     {
     int i;
     for(i=0;i<s;i++)
     {
     printf("\n enter data for record #%d",i+1);
     printf("\n enter account_no:");
     scanf("%d",&list[i].account_no);
     fflush(stdin);
     printf("enter name:");
     gets(list[i].name);
     list[i].balance=0;
     }
     }
     void display(struct customer list[80],int s)
     {
     int i;
     printf("\n A/c no\tname\tbalance\n");
     for(i=0;i<s;i++)
     {
     printf("%d\t%s\t%d\n",list[i].account_no,list[i].name,list[i].balance);
     }
     }
     int search(struct customer list[80],int s,int number)
     {
     int i;
     for(i=0;i<s:i++)
     {
     if(list[i].account_no=number)
     {
     return i;
     }
     }
     return-1;
     }
     void deposit(struct customer list [],int s,int number,int amt)
     {
     int i=search(list,s,number);
     if(i==-1)
     {
     printf("record not found");
     }
     else
     {
     list[i].balance+=amt;
     }
     }
     void withdraw(struct customer list[],int s,int number,int amt)
     {
     int i=search(list,s,number);
     if(i==-1)
     {
     printf("record not found\n");
     }
     else if(list[i].balance<amt)
     {
     printf("insufficient balance\n");
     }
     else
     {
     list[i].balance-=amt;
     }
     }
