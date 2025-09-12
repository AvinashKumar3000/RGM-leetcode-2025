# solution

```c
int removeDuplicates(int* nums, int numsSize){
    int k = 0;
    int i;
    for(i=0; i<numsSize-2; i++){
      if(nums[i]!=nums[i+2]){
        nums[k++] = nums[i];
      }
    }
    for(  ; i<numsSize; i++){
      nums[k++] = nums[i];
    }
    return k;
}
```
