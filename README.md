#include "stdio.h"
#include "conio.h"
#include "windows.h"



char b[10][11]={
	{"***#######"},
	{"##*#######"},
	{"##*****###"},         
	{"#####*####"},
	{"#####*####"},
	{"#####****#"},
	{"########*#"},
	{"######***#"},
	{"######*###"},
	{"######***E"}};
	
	
	
	
	void a(int x,int y)
	{
		COORD c; 
		c.X=x;
		c.Y=y;
		printf("X=%d,Y=%d\n",x,y);
		SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE),c);
	}
	
	void c()
	{
		for(int i=0;i<10;i++)
			puts(b[i]);
	}
	
	
	
	int x,y;
	int main()
	{
		
		while(1)
		{
			system("cls");
			c();
			a(x,y);
			char t=getch();
			if(t=='w')
			{
				if((y-1)>=0 && (b[y-1][x]=='*' || b[y-1][x]=='E'))
					y--;
			}
			else if(t=='s')
			{
				if((y+1)<11 && (b[y+1][x]=='*' || b[y+1][x]=='E'))
					y++;
			}
			
			else if(t=='a')
			{
				if((x-1)>=0 && (b[y][x-1]=='*' || b[y][x-1]=='E'))
					x--;
			}
			
			else if(t=='d')
			{
				if((x+1)<11 && (b[y][x+1]=='*' || b[y][x+1]=='E'))
					x++;
			}
			
			
			if(b[y][x]=='E')
				break;
			
		}
		printf("\n");
		printf("恭喜你走出了迷宫！\n");
		return 0;
	}
	
	
	

