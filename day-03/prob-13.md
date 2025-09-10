# solution 

```c 
int* applyOperations(
	int* nums, int numsSize, int* returnSize
) {
	int n = numsSize;
	for(int i=0; i<n-1; i++) {
		if(nums[i]==nums[i+1]) {
			nums[i] = nums[i] * 2;
			nums[i+1] = 0;
		}
	}
	int k=0;
	for(int i=0; i<n; i++) {
		if(nums[i] != 0) 
			nums[k++] = nums[i];
	}
	for(int i=k; i<n; i++)
		nums[i] = 0;
	*returnSize = numsSize;
	return nums;
}
```