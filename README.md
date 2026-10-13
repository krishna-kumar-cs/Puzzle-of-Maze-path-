# Puzzle-of-Maze-path-
find total ways of a maze using c programming 
#include<stdio.h>
#include<stdlib.h>
int maze(int cr,int cc,int er,int ec){
    int rightways = 0;
    int downways = 0;
    if(cr==er && cc==ec) return 1;
    if(cr==er){
      rightways += maze(cr,cc+1,er,ec);
    }
    if(cc==ec){
      downways += maze (cr+1,cc,er,ec);
    }
    if(cr<er && cc<ec){
      rightways += maze(cr,cc+1,er,ec);
      downways += maze(cr+1,cc,er,ec);
    }
    int totalways = rightways + downways ;
    return totalways ;
   }   
    
    
int main()
{    
   int n,m;
   printf("Enter number of rows\n");
   scanf("%d",&n);
   printf("Enter number of column\n");
   scanf("%d",&m);
   int no0fways = maze(1,1,n,m);
   printf("the total ways are of puzzle\n -> %d",no0fways);
   
     return 0;
}