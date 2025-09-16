# solution LC_1991

```c
 int findMiddleIndex(int* nums, int numsSize) {
    int lft_sum = 0;
    int rht_sum = 0;
    int total = 0;
    int n = numsSize;
    for(int i=0; i<n; i++)
        total += nums[i];
    for(int i=0; i<n; i++){
        rht_sum = total - nums[i] - lft_sum;
        if(lft_sum == rht_sum)
            return i;
        lft_sum += nums[i];
    }

    return -1;
} 
```