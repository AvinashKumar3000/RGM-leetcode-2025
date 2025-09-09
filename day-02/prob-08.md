# solution 

```c
int busyStudent(int* startTime, int startTimeSize, int* endTime, int endTimeSize, int queryTime) {
    int c = 0;
    for(int i = 0; i<startTimeSize; i++) {
        if( startTime[i] <= queryTime &&  endTime[i] >= queryTime ){
            c++;
        }
    }
    return c;
}
```

## another solution 

```c
int busyStudent(
	int* startTime, 
	int startTimeSize, 
	int* endTime, 
	int endTimeSize, 
	int queryTime
) {
	int n = startTimeSize;
	int count = 0;
	for(int i=0; i<n; i++) {
		int s = startTime[i];
		int e = endTime[i];
		if( s <= queryTime && e >= queryTime )
			count++;
	} 
    return count;
}
```
