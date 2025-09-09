# solution 

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* replaceElements(
	int* arr, 
	int arrSize, 
	int* returnSize
) {
	int max = -1;
	int* ans = (int*) calloc(arrSize, sizeof(int));

   for(int i=arrSize-1; i>=0; i--) {	
   		ans[i] = max;
   		if(arr[i] > max)
   			max = arr[i];
   }
   *returnSize = arrSize;
   return ans;
}
```