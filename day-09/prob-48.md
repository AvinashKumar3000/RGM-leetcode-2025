# solution 

```c
char* finalString(char* s) { 
  char* ans = (char*) calloc(100, sizeof(char));
  int n = strlen(s);
  int k = 0;
  for(int i=0; i<n; i++){
    if(s[i] == 'i'){
      for(int j=0; j<(k/2); j++){
        int temp = ans[j];
        ans[j] = ans[k-j-1];
        ans[k-j-1] = temp;
      }
    }else{
      ans[k++] = s[i];
    }
  }
  ans[k] = '\0';
  return ans;
}
```