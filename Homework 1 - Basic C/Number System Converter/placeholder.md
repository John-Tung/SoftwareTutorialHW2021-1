# Please upload your Homework

### Upload your code here
#include <stdio.h>

void IntToString(int value, char baseChars[] ,int Base,char result[])
    {
        do
        {
            result = baseChars[value % Base] + result;
            value = value / Base;
        } 
        while (value > 0);
    }




int main() {
    printf("Hello, world!");
	int value = 0;
	scanf("%d",&value);
	char result[100];
	IntToString(value, new char[] { '0', '1' }, 2, result);
	printf("s",result);
    return 0;
}
