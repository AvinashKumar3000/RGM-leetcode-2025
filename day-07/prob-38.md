# solution

```c
int countPairs(int* nums, int numsSize, int k) {
    int count = 0;
    int n = numsSize;
    for(int i=0; i<n; i++){ 
      for(int j=i+1; j<n; j++){
        if( nums[i] == nums[j] && (i*j)%k==0 )
          count++;
      }
    }
    return count;
}
```