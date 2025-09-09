# solution 1672

```c
int maximumWealth(
	int** accounts, 
	int accountsSize, 
	int* accountsColSize
) {
	int max_sum = 0;
	for(int i=0; i<accountSize; i++) {
		int* customer = accounts[i];
		int sum = 0;
		for(int j=0; j< *accountColSize ;j++) {
			sum += customer[j];
		}
		if(sum > max_sum)
			max_sum = sum;
	}
	return max_sum;
}
```