#include <stdio.h> 
#include <stdlib.h>

int main(void){
	
	system("CHCP 1253 > nul");
	
	FILE *file_1 , *file_2 ,  *file_3 ;
	
	
	int num_1, num_2, sum;
	
	file_1 = fopen("1.txt", "w");
	file_2 = fopen("2.txt", "w");
	
	if (file_1 == NULL || file_2 == NULL)
	{	
		printf("Error appending file...\a\n");
		return 1;
	}
	else 
	{
		printf("Εισάγεται έναν ακέραιο για το αρχείο 1.txt: ");
		scanf("%d", &num_1 );
		fprintf(file_1,"%d",num_1);
		
		printf("\nΕισάγεται έναν ακέραιο για το αρχείο 2.txt: ");
		scanf("%d", &num_2 );
		fprintf(file_2,"%d",num_2);
		
		fclose(file_1);
		fclose(file_2);
	}
	
	file_1 = fopen("1.txt", "r");
	file_2 = fopen("2.txt", "r");
	file_3 = fopen("3.txt", "w");
	
	if (file_1 == NULL || file_2 == NULL || file_3 == NULL)
	{	
		printf("Error appending file...\a\n");
		return 1;
	}
	else
	{
		fscanf(file_1, "%d", &num_1);
    	fscanf(file_2, "%d", &num_2);
    	
    	sum = num_1 + num_2;
		
		fprintf(file_3,"%d",sum);
  	
	}
			
	fclose(file_1);
    fclose(file_2);
    fclose(file_3);
	
	printf("\nΤο άθροισμα αποθηκεύτηκε στο αρχείο 3.txt\n");
    	
  
	
	system("PAUSE");
	return 0;
}
