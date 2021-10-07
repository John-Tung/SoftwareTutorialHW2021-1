# Please upload your Homework

### Upload your code here
#include <stdio.h>
#include <string.h>

int value = 0;
int base = 10;
int targetBase = 2;
int length = 0;
int condition = 0;
char input_str[100];
char result[100];
char binaryBaseChars[] = { '0', '1' };
char decBaseChars[] ={ '0', '1', '2', '3', '4', '5', '6', '7', '8', '9'};
char hexBaseChars[] ={ '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
                         'A', 'B', 'C', 'D', 'E', 'F'};

void check_valid(int base){
	
	if(base == 2 || base == 10 || base == 16){
	}
	else{
		printf("Error! invalid system \n");
	}
	if (base ==2){
		printf("HI %d",length);
		for(int i = 0; i<length; i++){
			if (input_str[i]<= 48 || input_str[i]>=49){
				printf("Error!That set of number is not a valid number. \n");
				break;
			}
		}
	}
	if(base== 10){
		for(int i = 0; i<length; i++){
			if (input_str[i]<= 48 || input_str[i]>=57){
				printf("Error!That set of number is not a valid number. \n");
				break;
			}
		}
	} 
	if(base == 16){
		for(int i = 0; i<length; i++){
			if (input_str[i]>= 48 || input_str[i]<=57){}
			else if (input_str[i]>= 65 || input_str[i]<=70){}
			else {
				printf("Error!That set of number is not a valid number. \n");
				break;
			}
		}	
	}
	
}

int power(int num, int power){
	int temp = 1;
	for(int i = 0; i < power; i++){
		temp *= num; 
	}
	num = temp;
	return num;
}


void string2value(int base){
	//int length = sizeof(input_str)/sizeof(input_str[0]);
	int temp_value;
	for(int i = 0; i<length; i++){
		if (input_str[i]>= 48 || input_str[i]<=57){
			temp_value = input_str[i] - 48;
		}
		else if (input_str[i]>= 65 || input_str[i]<=70){
			temp_value = input_str[i] - 55;
		}
		else {
			printf("Error!That set of number is not a valid number. \n");
		}
		value += temp_value*power(base,length-1-i);
		//printf("%d \n",value);
	}
		
}

void convertion(char baseChars[] ,int targetBase)
    {
		for(int i = 0; value > 0; i++)
        {
			for (int j = i; j>0; j--){
				result[j] = result[j-1]; 
			}
			result[0] =  baseChars[value % targetBase];
            value = value / targetBase;
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
		
	else if(base == 10 && targetBase == 2){   //condition3: 10 ->2 
		condition = 3;
	}

	else if(base == 10 && targetBase == 16){   //condition4: 10 ->16 
		condition = 4;
	}
		
	else if(base == 16 && targetBase == 2){   //condition5: 16 ->2 
		condition = 5;
	}
	else if(base == 16 && targetBase == 10){   //condition6: 16 ->10 
		condition = 6;
	}
}



int main() {
	//request basic input
	printf("Please enter a set of number: \n");
	scanf("%s",input_str);
	printf("Please enter the current number system: \n");
	scanf("%d",&base);
	//input checking
	length = strlen(input_str);
	check_valid(base);
	string2value(base);
	
	printf("Please enter the target number system: \n");
	scanf("%d",&targetBase);

	//convertion
	check_condition(base,targetBase);
	//printf("%d \n",condition);
	switch(condition){
		case 1:
			convertion(decBaseChars, targetBase);
			break;
		case 2:
			convertion(hexBaseChars, targetBase);
			break;
		case 3:
			convertion(binaryBaseChars, targetBase);
			break;
		case 4:
			convertion(hexBaseChars, targetBase);
			break;
		case 5:
			convertion(binaryBaseChars, targetBase);
			break;
		case 6:
			convertion(decBaseChars, targetBase);
			break;
	}
	
	printf("%s",result);
    return 0;
}
