#include<stdio.h>
#include<string.h>
#include<stdlib.h>

int main()
{
  char mes[10],emes[10],dec[10];
  int key;
  char ch;
  printf("Enter the text\n");
  scanf("%s",mes);
  printf("Enter the key\n");
  scanf("%d",&key);
  
  for(int i=0;mes[i]!='\0';i++)
  {
     ch = mes[i];
     if(ch>='a' && ch<='z')
     {
         ch = ch+key;
         if(ch>'z')
         {
         ch = ch-'z'+'a'-1;
         }
         emes[i]=ch;
     }
     else if(ch>='A' && ch<='Z')
     {
         ch = ch+key;
         if(ch>'Z')
         {
         ch = ch-'Z'+'A'-1;
         }
         emes[i]=ch;
     }
  }
   
  printf("encrypted mes: %s \n",emes);
  
   for(int i=0;mes[i]!='\0';i++)
  {
     ch = emes[i];
     if(ch>='a' && ch<='z')
     {
         ch = ch-key;
         if(ch<'a')
         {
         ch = 'z'-('a'-ch-1);
         }
         dec[i]=ch;
     }
     else if(ch>='A' && ch<='Z')
     {
         ch = ch-key;
         if(ch<'A')
         {
         ch ='Z'-('A'-ch-1) ;
         }
         dec[i]=ch;
     }
  }
   
  printf("decrypted mes: %s \n",dec);
  
}
