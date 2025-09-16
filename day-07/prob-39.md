# solution

```c    
int countHillValley(
    int* nums, 
    int numsSize
) {
    int n = numsSize;
    int count = 0;
    int prev = nums[0];
    for(int i=1; i<n-1; i++){  // ignore first and last 
        if(nums[i]==nums[i+1])
            continue;
        int lft = prev;
        int rht = nums[i+1];
        if( lft > nums[i] && rht > nums[i] )
            count++;
        if( lft < nums[i] && rht < nums[i] )
            count++;
        prev = nums[i];
    }    
    return count;
}
```