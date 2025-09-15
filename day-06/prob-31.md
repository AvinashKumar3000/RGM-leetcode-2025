# solution LC_2475

```c
  int unequalTriplets(int* nums, int numsSize) {
    int c = 0;
    int n = numsSize;
    for(int i=0; i<n; i++) {
        for(int j=i+1; j<n; j++) {
            for(int k=j+1; k<n; k++) {
                if ( 
                    nums[i]!=nums[j] &&
                    nums[j]!=nums[k] &&
                    nums[i]!=nums[k]
                ) c++;
            }
        }
    }
    return c;
}
```