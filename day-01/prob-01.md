# solution 

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* shuffle(int* nums, int numsSize, int n, int* returnSize){
	int x,y;
	int* ans = (int*) calloc(2*n, sizeof(int));

	int j=0;
	for(int i=0; i<n;i++) {
		x = i;
		y = i+n;
		ans[j++] = nums[x];
		ans[j++] = nums[y];
	}    
	*returnSize = 2*n;
	return ans;
}

```
