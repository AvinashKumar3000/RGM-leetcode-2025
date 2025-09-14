# solution LC_922

```c  
int* sortArrayByParityII(
    int* nums, 
    int numsSize, 
    int* returnSize
) {
    int odd_idx = 1;
    int even_idx = 0;
    int* ans = (int*) calloc(numsSize, sizeof(int));
    for(int i=0; i<numsSize; i++) {
    	  if(nums[i]%2==0){
    	  	 ans[even_idx] = nums[i];
    	  	 even_idx += 2;
    	  }else{
    	  	 ans[odd_idx] = nums[i];
    	  	 odd_idx += 2;
    	  }
    }
    *returnSize = numsSize;
    return ans;
}
```