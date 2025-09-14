# solution LC_1389

```c  
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* createTargetArray(
    int* nums, 
    int numsSize, 
    int* index, 
    int indexSize, 
    int* returnSize
) {
    int n = numsSize;
    int* ans = (int*) calloc(n, sizeof(int));
    for(int i=0; i<n; i++) {
        ans[i] = -1;
    }

    for(int i=0; i<n; i++) {
        int val = nums[i];
        int idx = index[i];
        if( ans[idx] == -1 )
            ans[idx] = val;
        else {
            for(int j=n-1; j>idx; j--) {
                ans[j] = ans[j-1];
            }
            ans[idx] = val;
        }
    }

    *returnSize = n;
    return ans;
}
```