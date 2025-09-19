# solution 

```c    
char* restoreString(
  char* s, int* indices, int indicesSize
) {
  int i, n = indicesSize;
  char* ans= (char*) calloc(n+1 , sizeof(char));
  for(i=0; i<n; i++){
    int index = indices[i];
    int ch = s[i];
    ans[index] = ch;
  }
  ans[i] = '\0';
  return ans;
}
```    