# solution 189

```c
void rotate(int* nums, int n, int k) {
  int temp[n];
  k = k%n;
  int start = (k==0) ? 0 : n-k;
  for(int i=0; i<n; i++){
    temp[i] = nums[start];
    start = (start+1)%n;
  }
  for(int i=0; i<n; i++){
    nums[i] = temp[i];
  }
} 
```