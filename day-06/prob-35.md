# solution LC_2873

## while submitting in c prog what is issue ?

- we will face a overflow issue. 
- while doing calculation `(nums[i]-nums[j]) * nums[k]` exceed int max limit. So result will stored with -neg value. ( butterfly ).

<img type="content" source="image.png" alt-text="butterfly ref"/>

```c
  long long maximumTripletValue(
	int* nums, 
	int numsSize
) {
	long max_value = 0;
	int n = numsSize;
	for(int i=0; i<n; i++) {
		for(int j=i+1; j<n; j++) {
			for(int k=j+1; k<n; k++) {
                long long a = nums[i];
                long long b = nums[j];
                long long c = nums[k];
                long long triplet = (a-b)*c; 
				if( triplet > max_value)
					max_value = triplet;
			}
		}
	}    

	return max_value < 0 ? 0 : max_value;
}
```