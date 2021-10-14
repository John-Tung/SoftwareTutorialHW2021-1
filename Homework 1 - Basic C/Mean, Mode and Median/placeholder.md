// Upload your Homework here
// Please upload your code here

#include <stdio.h>
#include<string.h>
#include <stdlib.h>

int input_arr[10] ;
int length = 0;
float mean = 0;
int mode = 0;
float median = 0;

void swap(int *a,int *b) {
      int temp =0;
      temp =*a; 
      *a=*b; 
      *b=temp;
    }

void sort(int a[],int n) { 
  int temp =0;
   for(int i = 0; i < length-1;i++) {
      for(int j = 0;j < length-i-1;j++) {
         if(input_arr[j] > input_arr[j+1])
            swap(&input_arr[j],&input_arr[j+1]);
      }
   }
}

void find_mean(){
  float temp_sum = 0;  
  for(int i = 0; i<length; i++){
    //printf("%d \n", input_arr[i]);
    temp_sum += input_arr[i];
  }
  mean = temp_sum/length;
} 

void find_mode() {
   int maxCount = 0;

   for (int i = 0; i < length; ++i) {
      int count = 0;

      for (int j = 0; j < length; ++j) {
         if (input_arr[j] == input_arr[i])
         count++;
      }

      if (count > mode) {
         maxCount = count;
         mode = input_arr[i];
      }
   }
}


void find_median(){
  sort(input_arr,length);
   
  int n = (length+1) / 2 - 1; 
  median = input_arr[n];
}

//const char *input_str[100][10];

int main(void) {
  printf("Enter a number to append to the number set. Enter '/' to stop appending. \n");

  char str[10];
  int i = 0;
  do{
    scanf("%s", str);
    if( *str == '/'){break;} 
    input_arr[i]= atoi(str);
    i++;  
    length++;
    //printf("%d \n",input_arr[i]);
  }while(*str != '/');
  
    
    
  //convert value
  find_mean();
  find_mode();
  find_median();
  printf("arrary length : %d \n",length);
  printf("mean: %f \n",mean);
  printf("mode: %d \n",mode);
  printf("median: %f \n",median);
  //printf("%f \n %d \n %f",mean,mode,median);

  return 0;
}
