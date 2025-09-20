# solution 

## 345. Reverse Vowels of a String

```c    
bool isVowel(char ch){
  char vowels[] = "aeiouAEIOU";
  int n = strlen(vowels);
  for(int i=0; i<n; i++){
    if(vowels[i]==ch) 
      return true;
  }
  return false;
}

char* reverseVowels(char* s) {
  int n = strlen(s);
  int lft = 0;
  int rht = n-1;
  while( lft < rht ) {
    if( !isVowel(s[lft]) )
      lft++;
    else if( !isVowel(s[rht]) )
      rht--;
    else{
      char temp = s[lft];
      s[lft] = s[rht];
      s[rht] = temp;
      lft++;
      rht--;
    }
  }   
  return s; 
}
```