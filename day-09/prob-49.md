# solution 


```c
char* interpret(char* command){
  char* cmd = command;
  char* ans = (char*) calloc(100, sizeof(char));
  int n = strlen(command);
  int k = 0;
  for(int i=0; i<n; i++){
      if( cmd[i]=='G' ) {
        ans[k++] = 'G';
      } else if( cmd[i]=='(' && cmd[i+1]==')' ) {
        ans[k++] = 'o';
      } else if( cmd[i]=='(' && cmd[i+1]=='a' ) {
        ans[k++] = 'a';
        ans[k++] = 'l';
      }
  } 
  ans[k] = '\0';
  return ans;
}
```
