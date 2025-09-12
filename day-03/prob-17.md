# solution 

```c
void duplicateZeros(int* arr, int arrSize) {
    int n = arrSize;
    for(int i=0; i<n; i++){
      if(arr[i]==0){
        for(int j=n-1; j>(i+1); j--)
          nums[j] = nums[j-1];
        nums[i+1] = 0;
        i = i+2;
      }
    }
}
```
