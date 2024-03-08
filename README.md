# tik-tak-toa-in-c
it's my firs c game in github
#include<stdio.h>
#include<conio.h>
 void tak();
 void system();
 
 int win();
 	char arr[] = {'0','1','2','3','4','5','6','7','8','9'};
 void  main()
 { 
   int player=1,input;
	int status=-1;
	 tak();
   while(status==-1)
    {
    	 player =(player%2==0)? 2 : 1 ;
       char mark=(player==1)?'x':'o';
        printf("enter a number for player %d ",player);
        scanf("%d",&input);
	      if(input<1 || input>9) {
	 	         printf("invalid");}  
      arr[input]= mark;	
      tak();
	
		int result = win();
		if(result==1)	{
		 printf("player %d is winer\n",player);
		 return; 	}
		else if(result==0)	{
		 printf("draw");
		 return; }
		 	player++;
	 	}
	      	}
 
 void tak()
 {
 	system("cls");
 	printf("===TIC TAC TOE===\n \n");
 	
 	printf("      |    |     \n");
  	printf("    %c | %c  |%c   \n",arr[1], arr[2],arr[3]);
 	printf("______|____|_____\n");
 	printf("      |    |     \n");
 	printf("    %c | %c  | %c \n",arr[4],arr[5],arr[6]);
	printf("______|____|_____\n");
 	printf("      |    |     \n");
 	printf("   %c  | %c  | %c  \n ",arr[7],arr[8],arr[9]);
 }
 int win()
 {
 	if(arr[1] == arr[2] && arr[2] == arr[3])
	  {
 	 return 1;
	  }
		if(arr[4] == arr[5] && arr[5] == arr[6]){
	return 1;}
 		if( arr[7] == arr[8] && arr[8] == arr[9]){
 	return 1;}
 		if( arr[1] == arr[4] && arr[4] == arr[7]){
	return 1;}
 		if ( arr[2] == arr[5] && arr[5] == arr[8]){
	return 1;}
		if( arr[3] == arr[6] && arr[6] == arr[9]){
	return 1;}
		if( arr[1] == arr[5] && arr[5] == arr[9]){
 	return 1;}
 		if(arr[7]==arr[5] && arr[5]==arr[3]){
 	return 1;}
 	int count=0,i;
 	for ( i=0;i<=9;i++)
	{
		if (arr[i]=='X' || arr[i]=='O')
		 {
		   count++;
			  }
			  	 }
		  if(count==9)
		  {
		  	return 0;
			  }
 	return -1;
 }
