# solution LC_905

```c     
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* sortArrayByParity(
    int* nums, 
    int numsSize, 
    int* returnSize
) {
    int* ans = (int*) calloc(numsSize, sizeof(int));
    int k = 0; 
    for(int i=0; i<numsSize; i++){
    		if(nums[i]%2==0)
    			ans[k++] = nums[i];
    }

    for(int i=0; i<numsSize; i++){
        if(nums[i]%2!=0)
    			ans[k++] = nums[i];
    }

    *returnSize = numsSize;
    return ans;
}
```