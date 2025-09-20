# 917. Reverse Only Letters

```c
bool isLetter(char ch){
  if( ch>='a' && ch<='z' || ch>='A' && ch<='Z' )
    return true;
  return false; 
}
char* reverseOnlyLetters(char* s) {
  int n = strlen(s);
  int lft = 0;
  int rht = n-1;
  while(lft < rht){
    if( !isLetter(s[lft]) )
        lft++;
    else if ( !isLetter(s[rht]) )
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
