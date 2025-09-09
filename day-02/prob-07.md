# solution 

```c
bool isFound(int* arr, int n, int key) {
	for(int i=0; i<n; i++) {
		if(arr[i]==key) 
			return true;
	}
	return false;
}

int findFinalValue(int* nums, int numsSize, int original) {
   	while( isFound(nums, numsSize, original) ) {
   		original = 2 * original;
   	}
   	return original;
}
```