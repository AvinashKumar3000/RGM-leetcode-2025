# solution ( solution is updated )

```c
void duplicateZeros(int* arr, int arrSize) {
  int n = arrSize;
  for(int i=0; i<n; i++) {
    if(arr[i] == 0) {
      for(int j=n-1; j>i+1 ; j--)
         arr[j] = arr[j-1];
      if(i+1<n) {
        arr[i+1] = 0;
        i++; 
      }
    }
  }
}
```
