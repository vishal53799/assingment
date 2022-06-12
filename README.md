# assingment -1
//Q1
#include <stdio.h>
#include <string.h>
 
int main()
{
    char s[30],c='*';  
    int  i,j,k=0,n;
 
    printf("Enter  the string : ");
    scanf("%[^\n]",&s); 
    for(i=0;s[i];i++)
    {
    	if(!(s[i]==c))
    	{
    		for(j=i+1;s[j];j++)
            {
            	if(s[i]==s[j])
            	   s[j]=c;
        	
		    }
    		
		}
    
   //Q2
   #include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <ctype.h>

unsigned int isFirstOccurance(char *string, char target, unsigned int index){
	for(int i = 0; string[i]; i++)
		if(tolower(string[i]) == tolower(target))
			return index == i;
	return 0;
}

int main(){
	char string[32];
	unsigned int freqs[32] = {};
	scanf("%[^\n]", string);
	for(int i = 0; string[i]; i++)
		if(isFirstOccurance(string, string[i], i))
		printf("%c", tolower(string[i]));
}

//Q3
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <ctype.h>

int cmp(const void *a, const void *b){
	return *(char*)a - *(char*)b;
}

int main(){
	char string[32];
	scanf("%[^\n]", string);
	qsort(string, strlen(string), sizeof(char), cmp);
	for(int i = 0; string[i]; i++)
		if(string[i] != string[i+1] && !isspace(string[i]))
			printf("%c", string[i]);
}


//Q4
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <ctype.h>

unsigned int occurances(char *string, char target){
	unsigned int count = 0;
	for(int i = 0; string[i]; i++)
		if(string[i] == target)
			count++;
	return count;
}

unsigned int isFirstOccurance(char *string, char target, unsigned int index){
	for(int i = 0; string[i]; i++)
		if(string[i] == target)
			return index == i;
	return 0;
}

int main(){
	char string[32];
	unsigned int freqs[32] = {};
	scanf("%[^\n]", string);
	for(int i = 0; string[i]; i++)
		if(isFirstOccurance(string, string[i], i))
		printf("Character \"%c\" = %d\n", string[i], occurances(string, string[i]));
}


//Q5
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <ctype.h>

unsigned int occurances(char *string, char target){
	unsigned int count = 0;
	for(int i = 0; string[i]; i++)
		if(tolower(string[i]) == tolower(target))
			count++;
	return count;
}

unsigned int isFirstOccurance(char *string, char target, unsigned int index){
	for(int i = 0; string[i]; i++)
		if(tolower(string[i]) == tolower(target))
			return index == i;
	return 0;
}

int main(){
	char string[32];
	unsigned int freqs[32] = {};
	scanf("%[^\n]", string);
	for(int i = 0; string[i]; i++)
		if(isFirstOccurance(string, string[i], i))
		printf("Character \"%c\" = %d\n", tolower(string[i]), occurances(string, string[i]));
}

