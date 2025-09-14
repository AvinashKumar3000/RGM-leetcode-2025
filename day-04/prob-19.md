# solution LC_896

```c    
bool isMonotonic(int* nums, int numsSize) {
    bool asc = true;
    bool dsc = true;

    for(int i=0; i<numsSize-1; i++) {
    	if( nums[i] > nums[i+1] )
    		asc = false;
    	if( nums[i] < nums[i+1] )
    		dsc = false;
    }

    return asc || dsc;
}
```

```python
class Solution:
    def isMonotonic(self, nums: List[int]) -> bool:
        asc , desc = True, True
        n = len(nums)
        for i in range(n-1):
            if nums[i] > nums[i+1]:  
                asc  = False
            if nums[i] < nums[i+1]:  
                desc = False
        return asc or desc


```
