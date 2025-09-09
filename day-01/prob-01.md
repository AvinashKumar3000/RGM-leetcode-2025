# solution LC_1480

```c
int* runningSum(
    int* nums,   
    int numsSize, 
    int* returnSize
) {
    int sum = 0;
    for(int i=0; i<numsSize; i++){
        sum = sum + nums[i];
        nums[i] = sum;
    }
    *returnSize = numsSize;
    return nums;
}
```