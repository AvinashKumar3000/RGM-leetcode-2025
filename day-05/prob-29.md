# solution 

```python
class Solution:
    def transformArray(self, nums: List[int]) -> List[int]:
        n = len(nums)
        even_count = 0
        odd_count = 0
        for i in range(n):
            if nums[i]%2==0:
                even_count += 1
            else:
                odd_count += 1
        res = []
        for i in range(even_count):
            res.append(0)
        for i in range(odd_count):
            res.append(1)
        return res


        
```

```c    
int* transformArray(
  int* nums, 
  int numsSize, 
  int* returnSize
) {
	int n = numsSize;
	int* ans = (int*) calloc(n, sizeof(int));
	int even_count = 0;
	int odd_count = 0;
	for(int i=0; i<n; i++) {
		if(nums[i]%2==0)
			even_count++;
		else
			odd_count++;
	}
	int k=0;
	for(int i=0; i<even_count; i++) 
		 ans[k++] = 0;
	for(int i=0; i<odd_count; i++) 
		 ans[k++] = 1;
	*returnSize = n;
	return ans;   
}
```
