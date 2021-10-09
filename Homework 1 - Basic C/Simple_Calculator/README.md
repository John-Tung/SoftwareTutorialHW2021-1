
#include <stdio.h>
#include <stdint.h>
#include <stdbool.h>
#include <string.h>
#include <stdlib.h>
#include "define.h"

int main() {
    opening();

    // write your code here
    int i = 0;
    int j = 0;
    int num = 0;
    float result = 0.0;
    char symbol;
    char input_str[100];
    char input_num1[100];
    char input_num2[100];

    scanf("%s",input_str);

    
    
    do{
      //char c = input_str[i];
      //char *c = "a string";
      //char *c = input_str[i];
      num = input_str[i];
      printf("%d \n",num);
      if( num -'0' <= 0 ||input_str[i] -'0' >= 9){
        printf("i: %d \n",i);
        break;}
      input_num1[i] = input_str[i]; 
      printf("input : %s \n",input_num1);
      i++;

    }while(num -'0' >= 0 ||input_str[i] -'0' <= 9);
    
    symbol = input_str[i++];
    printf("symbol : %c \n", symbol);

    do{
      //char c = input_str[i];
      //char *c = "a string";
      //char *c = input_str[i];
      num = input_str[i];
      printf("%d \n",num);
      if( num -'0' <= 0 ||input_str[i] -'0' >= 9){
        printf("j: %d \n",j);
        break;}
      input_num2[j] = input_str[i]; 
      printf("input2 : %s \n",input_num2);
      i++;
      j++;
    }while(i<sizeof(input_str)/sizeof(char));

    float number_1 = atoi(input_num1);
    float number_2 = atoi(input_num2);
    //printf("Input: % d  %c  %d \n", number_1, input[1],number_2); 
    
    if(symbol == '+'){
      result = number_1+number_2;
      
    }
    else if(symbol == '-'){
      result =number_1 - number_2;

    }
    else if(symbol == '*'){
      result =number_1 * number_2;
    }
    else if(symbol == '/'){
      result = number_1 / number_2;
    }
    printf("output: % f", result);
    //end of your code

    return 0;
}
