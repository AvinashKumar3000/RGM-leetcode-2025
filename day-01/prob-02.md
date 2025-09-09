# solution LC_485

```c
int findMaxConsecutiveOnes(int* nums, int numsSize) {
    int c = 0;
    int max = 0;
    for(int i=0; i<numsSize; i++) {
        if(nums[i]==1) c++;
        else{
            if(c > max) 
                max = c;
            c = 0;
        }
    } 
    if(c>max) 
        max = c;
    return max;
}
```