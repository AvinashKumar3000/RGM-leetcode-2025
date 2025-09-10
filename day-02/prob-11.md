# solution 

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* decode(
	int* encoded, 
	int encodedSize, 
	int first, 
	int* returnSize) {
 	   int* ans = (int*) calloc(encodedSize + 1, sizeof(int));
 	   ans[0] = first;
 	   int k = 0;
 	   for(int i=0; i<encodedSize; i++) {
 	   		int result = ans[k] ^ encoded[i];
            k++;
            ans[k] = result;
 	   }
 	   
 	   *returnSize = encodedSize + 1;
 	   return ans;
}
```