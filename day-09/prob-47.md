# solution 1108. Defanging an IP Address

```c
char* defangIPaddr(char* address){
  int n = strlen(address);
  char* ans = (char*)calloc(100,sizeof(char));
  int k = 0;
  for(int i=0; i<n; i++){
    if(address[i]=='.'){
      ans[k++] = '[';
      ans[k++] = '.';
      ans[k++] = ']';
    }else{
      ans[k++] = address[i];
    }
  }
  ans[k] = '\0';
  return ans;
}
```
