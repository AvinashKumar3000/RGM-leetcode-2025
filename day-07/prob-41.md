# solution 

```c
int* twoSum(
  int* nums, 
  int numsSize, 
  int target, 
  int* returnSize
) {
  int n = numsSize;
  *returnSize = 2;
  int* ans = (int*) calloc(2, sizeof(int));
  for(int i=0; i<n; i++){
    for(int j=i+1; j<n; j++){
      if(nums[i]+nums[j]==target){
          ans[0] = i;
          ans[1] = j;
          return ans;
      }
    }
  }
  return ans;
}
```
