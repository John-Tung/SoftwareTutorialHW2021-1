# Please upload your Homework

### Upload your code here
#include <stdio.h>

int value = 0;
int base = 10;
int targetBase = 2;
char result[100];
int condition = 0;

void check_valid(int value, int base){
	if(base == 2 || base == 10 || base == 16){
	}
	else{
		printf("Error! invalid system \n");
	}
}



void convertion(int value, char baseChars[] ,int Base,char result[])
    {
		for(int i = 0; value > 0; i++)
        {
			for (int j = i; j>0; j--){
				result[j] = result[j-1]; 
			}
			result[0] =  baseChars[value % Base];
            value = value / Base;
        } 
		
    }
void check_condition(int base, int targetBase){
	//6 condition
	if(base == 2 && targetBase == 10){   //condition1: 2 ->10 
		condition = 1;
	}
	else if(base == 2 && targetBase == 16){   //condition2: 2 ->16 
		condition = 2;
	}
	
}


int main() {
	//request basic input
	printf("Please enter a set of number: \n");
	scanf("%d",&value);
	printf("Please enter the current number system: \n");
	scanf("%d",&base);
	//input checking
	check_valid(value, base);	
	printf("Please enter the target number system: \n");
	scanf("%d",&targetBase);

	//convertion
	check_condition(base,targetBase);
	printf("%d /n",condition);
	//switch(condition){
		//condition 1 : 10->2;
		//case 1:
	//}
	
	char binaryBaseChars[] = { '0', '1' };
	convertion(value,binaryBaseChars, targetBase, result);
	printf("%s",result);
    return 0;
}
