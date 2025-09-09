# solution LC_1313

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* decompressRLElist(int* nums, int numsSize, int* returnSize) {
   	int ansSize = 0;
   	for(int i=0; i<numsSize ; i=i+2) {
   		int freq = nums[i];
   		ansSize = ansSize + freq;
   	}
   	int* ans = (int*) calloc(ansSize, sizeof(int));
   	*returnSize = ansSize;
   	int k = 0;
   	for(int i=0; i<numsSize; i+=2) {
   		int freq = nums[i];  
   		int value = nums[i+1];
   		for(int j=0; j<freq ; j++) {
   			ans[k++] = value;
   		}
   	}
   	return ans;
}
```

## solution 2

```c
int* decompressRLElist(
	int* nums, 
	int numsSize, int* returnSize
) {
   int n = 0;
   for(int i=0; i<numsSize/2; i++) {
   	 int freq = nums[2*i];
   	 n = n + freq;
   }
   int* ans = (int*) calloc( n, sizeof(int));
   int k = 0;
   for(int i =0; i<numsSize/2 ; i++) {
   		int freq = nums[2*i];
   		int val  = nums[2*i+1];
   		for(int j=0; j<freq	; j++) {
   			ans[k++] = val;
   		}
   }

   *returnSize = n;
   return ans;
}
```
