# tic-tac-toe

#include<stdio.h>



void breakcondition1();
void breakcondition2();
void winner();
void score();
void user1();
void user2();
int check();
void pattern();
void moves();
void select();



///Variables Decleration.
int c1=0,c2=0,i,a,n,i1;
int scorex=0,scorey=0,scorex1,scorey1;
char ch[9],ars,u1,u2;



///Main Function.
int main()
{
    int choice;
//    clrscr();
    point:
    select();
    for(i1=0;i1<9;i1++)
{
    ch[i1]=' ';
}
pattern();
for (a=0;a<1;a++)
{
n=a%2;
moves();
//getch();
}
//clrscr();
score();
wro:
    printf("\n1.To play again\n2.For Exit\n");
    printf("\nDo you want to play again\n");
    scanf("%d",&choice);
    switch(choice)
    {
	case 1:
//	    clrscr();
	    goto point;
	case 2:
	    printf("Hope you Enjoyed\n");
	    break;
	default:
	   printf("Wrong input\n");
	    goto wro;
}
//replay();
//getch();
return 0;
}




void select()
{
    point:
//    clrscr();
    printf("\nFor user 1\n");
    printf("Select which symbol you want 'x' or '0'\n");
    scanf("%c",&u1);
    if((u1=='x')||(u1=='X'))
	u2='0';
    else if((u1=='0')||(u1=='O'))
	u2='X';
    else
    {
	printf("\nWrong Input\n");
	goto point;
    }
//    clrscr();
}




///condition for break by user 1
void breakcondition1()
{
    if((ch[0]!=' ')&&(ch[1]!=' ')&&(ch[2]!=' ')&&(ch[3]!=' ')&&(ch[4]!=' ')&&(ch[5]!=' ')&&(ch[6]!=' ')&&(ch[7]!=' ')&&(ch[8]!=' ')&&(ch[9]!=' '))
    {
	printf("\ndraw\n");
    }
    else
    {
	check();
	user2();
    }
}




///condition for break by user 2
void breakcondition2()
{
if((ch[0]!=' ')&&(ch[1]!=' ')&&(ch[2]!=' ')&&(ch[3]!=' ')&&(ch[4]!=' ')&&(ch[5]!=' ')&&(ch[6]!=' ')&&(ch[7]!=' ')&&(ch[8]!=' ')&&(ch[9]!=' '))
{
    printf("\ndraw\n");
}
 else
    {
	check();
	user1();
    }
}




///For the printing of pattern.
void pattern()
{
    printf("\t\t    |    |   \n");
    printf("\t\t 1  |  2 |  3\n");
    printf("\t\t____|____|____\n");
    printf("\t\t    |    |  \n");
    printf("\t\t 4  |  5 |  6\n");
    printf("\t\t____|____|____\n");
    printf("\t\t    |    |  \n");
    printf("\t\t 7  |  8 |  9\n");
    printf("\t\t    |    |  \n");
}




///move by user 1
void user1()
{
     check();
     printf("\nenter location\n");
     scanf("%d",&i);
	 if((i<1)||(i>10))
	 {
	     printf("\nenter correct location\n");
	     user1();
	 }

	 else if(ch[i-1]==' ')
	 {
	    ch[i-1]=u1;
	 }
	 else
	 {
     printf("\nlocation already filled\n");
	 user1();
	 }
    printf("\t\t    |    |   \n");
   printf("\t\t %c  |  %c |  %c\n",ch[0],ch[1],ch[2]);
    printf("\t\t____|____|____\n");
    printf("\t\t    |    |  \n");
   printf("\t\t %c  |  %c |  %c\n",ch[3],ch[4],ch[5]);
    printf("\t\t____|____|____\n");
    printf("\t\t    |    |  \n");
   printf("\t\t %c  |  %c |  %c\n",ch[6],ch[7],ch[8]);
    printf("\t\t    |    |  \n");

    check();
    if(c1==0)
    {
	breakcondition1();
    }
    else
    {
	winner();
    }
}




///move by user2
void user2()
{
    check();
    printf("\nenter location\n");
	scanf("%d",&i);
	if((i<1)||(i>10))
	 {
	     printf("\nenter correct location\n");
	     user2();
	 }

	 else if(ch[i-1]==' ')
	 {
	    ch[i-1]=u2;
	 }
	 else
	 {
	 printf("\nlocation already filled\n");
	 user2();
	 }

    printf("\t\t    |    |   \n");
   printf("\t\t %c  |  %c |  %c\n",ch[0],ch[1],ch[2]);
    printf("\t\t____|____|____\n");
    printf("\t\t    |    |  \n");
   printf("\t\t %c  |  %c |  %c\n",ch[3],ch[4],ch[5]);
    printf("\t\t____|____|____\n");
    printf("\t\t    |    |  \n");
   printf("\t\t %c  |  %c |  %c\n",ch[6],ch[7],ch[8]);
    printf("\t\t    |    |  \n");
    check();
    if(c1==0)
    {
	breakcondition2();
    }
    else
    {
	    winner();
    }
}




///Adjust the moves of players.
void moves()
{
if(n==0)
{
    user1();
}
else
{
 user2();

}
}




///Check for the winner condition.
int  check()
     {
	if(((ch[0]==ch[3])&&(ch[3]==ch[6])&&(ch[0]!=' '))||((ch[1]==ch[4])&&(ch[4]==ch[7])&&(ch[1]!=' '))||((ch[2]==ch[5])&&(ch[5]==ch[8])&&(ch[2]!=' ')))
	{
	    c1=1;
	}
	else if(((ch[0]==ch[1])&&(ch[1]==ch[2])&&(ch[1]!=' '))||((ch[3]==ch[4])&&(ch[4]==ch[5])&&(ch[4]!=' '))||((ch[6]==ch[7])&&(ch[7]==ch[8])&&(ch[8]!=' ')))
	{
	    c1=2;
	}
	else if(((ch[0]==ch[4])&&(ch[4]==ch[8])&&(ch[0]!=' '))||((ch[2]==ch[4])&&(ch[4]==ch[6])&&(ch[4]!=' ')))
	{
	c1=3;
	}
	else
	{
	    c1=0;
	}
     return c1;
     }




///Who is the Winner check.
     void winner()
     {
     if((c1==1)||(c1==2)||(c1==3))
     {
     if(((ch[0]==ch[3])&&(ch[3]==ch[6])&&(ch[0]=='x'))||((ch[1]==ch[4])&&(ch[4]==ch[7])&&(ch[1]=='x'))||((ch[2]==ch[5])&&(ch[5]==ch[8])&&(ch[2]=='x')))
	{
	printf("winner=x");
	}
	else if(((ch[0]==ch[1])&&(ch[1]==ch[2])&&(ch[1]=='x'))||((ch[3]==ch[4])&&(ch[4]==ch[5])&&(ch[4]=='x'))||((ch[6]==ch[7])&&(ch[7]==ch[8])&&(ch[8]=='x')))
	{
	printf("winner=x");
	}
	else if(((ch[0]==ch[4])&&(ch[4]==ch[8])&&(ch[0]=='x'))||((ch[2]==ch[4])&&(ch[4]==ch[6])&&(ch[4]=='x')))
	{
	printf("winner=x");
	}
	else if(((ch[0]==ch[3])&&(ch[3]==ch[6])&&(ch[0]=='0'))||((ch[1]==ch[4])&&(ch[4]==ch[7])&&(ch[1]=='0'))||((ch[2]==ch[5])&&(ch[5]==ch[8])&&(ch[2]=='0')))
	{
	printf("winner=0");
	}
	else if(((ch[0]==ch[1])&&(ch[1]==ch[2])&&(ch[1]=='0'))||((ch[3]==ch[4])&&(ch[4]==ch[5])&&(ch[4]=='0'))||((ch[6]==ch[7])&&(ch[7]==ch[8])&&(ch[8]=='0')))
	{
	printf("winner=0");
	}
	else if(((ch[0]==ch[4])&&(ch[4]==ch[8])&&(ch[0]=='0'))||((ch[2]==ch[4])&&(ch[4]==ch[6])&&(ch[4]=='0')))
	{
	printf("winner=0");
	}
	else if((ch[0]==ch[1])&&(ch[0]==ch[2])&&(ch[0]==ch[3])&&(ch[0]==ch[4])&&(ch[0]==ch[5])&&(ch[0]==ch[6])&&(ch[0]==ch[7])&&(ch[0]==ch[8]&&(ch[0]!=' ')))
	{
	printf("draw");
	}
	}
	score();
}


    void score()
    {
      //  clrscr();
     printf("\n\t\t\t*******SCORE*******\n");
	 if(((ch[0]==ch[3])&&(ch[3]==ch[6])&&(ch[0]=='x'))||((ch[1]==ch[4])&&(ch[4]==ch[7])&&(ch[1]=='x'))||((ch[2]==ch[5])&&(ch[5]==ch[8])&&(ch[2]=='x')))
	 {
	 scorex1=50;
	 scorey1=0;
	 }
	 else if(((ch[0]==ch[1])&&(ch[1]==ch[2])&&(ch[1]=='x'))||((ch[3]==ch[4])&&(ch[4]==ch[5])&&(ch[4]=='x'))||((ch[6]==ch[7])&&(ch[7]==ch[8])&&(ch[8]=='x')))
	 {
	  scorex1=50;
	  scorey1=0;
	 }
	 else if(((ch[0]==ch[4])&&(ch[4]==ch[8])&&(ch[0]=='x'))||((ch[2]==ch[4])&&(ch[4]==ch[6])&&(ch[4]=='x')))
	 {
	  scorex1=50;
	  scorey1=0;
	 }
	 else if(((ch[0]==ch[3])&&(ch[3]==ch[6])&&(ch[0]=='0'))||((ch[1]==ch[4])&&(ch[4]==ch[7])&&(ch[1]=='0'))||((ch[2]==ch[5])&&(ch[5]==ch[8])&&(ch[2]=='0')))
	{
	 scorex1=0;
	 scorey1=50;
	}
	else if(((ch[0]==ch[1])&&(ch[1]==ch[2])&&(ch[1]=='0'))||((ch[3]==ch[4])&&(ch[4]==ch[5])&&(ch[4]=='0'))||((ch[6]==ch[7])&&(ch[7]==ch[8])&&(ch[8]=='0')))
	{
	 scorex1=0;
	 scorey1=50;
	}
	else if(((ch[0]==ch[4])&&(ch[4]==ch[8])&&(ch[0]=='0'))||((ch[2]==ch[4])&&(ch[4]==ch[6])&&(ch[4]=='0')))
	{
	 scorex1=0;
	 scorey1=50;
	}
	else if((ch[0]==ch[1])&&(ch[0]==ch[2])&&(ch[0]==ch[3])&&(ch[0]==ch[4])&&(ch[0]==ch[5])&&(ch[0]==ch[6])&&(ch[0]==ch[7])&&(ch[0]==ch[8]&&(ch[0]!=' ')))
	{
	 scorex1=0;
	 scorey1=0;
	}
	scorex=scorex+scorex1;
	scorey=scorey+scorey1;
	printf("\t\t\tX=%d\t\tY=%d\n",scorex,scorey);
	 scorex1=0;
	 scorey1=0;

}
