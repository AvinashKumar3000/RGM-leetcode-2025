# solution LC_977

```c     

int* sortedSquares(int* nums, int numsSize, int* returnSize) {
    int n = numsSize;
    int* ans = (int*) calloc(n, sizeof(int));
    for(int i=0; i<n; i++) {
    	ans[i] = nums[i]*nums[i];
    }
    for(int i=0; i<n; i++){
    	for(int j=0; j<n-1; j++){
    		 if(ans[i]>ans[j]){
    		 		int temp = ans[i];
    		 		ans[i] = ans[i+1];
    		 		ans[i+1] = temp;
    		 }
    	}
    }
    *returnSize = numsSize;
    return ans;
}
```