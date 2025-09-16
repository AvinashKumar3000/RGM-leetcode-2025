# solution 

```c
int pivotIndex(int* nums, int numsSize) {
    int lft = 0;
    int rht = 0;
    int total = 0;
    int n = numsSize;
    for(int i=0; i<n; i++){
      total += nums[i];
    }

    for(int i=0; i<n; i++){
       rht = total - nums[i] - lft;
       if(lft==rht)
           return i;
       lft = lft + nums[i];
    }
    
    return -1;
}
```
