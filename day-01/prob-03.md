# solution LC_1732

```c
int largestAltitude(int* gain, int gainSize) {
    int sum = 0, max = 0;
    for(int i=0; i<gainSize; i++){
        sum = sum + gain[i];
        if(sum > max) 
            max = sum;       
    }
    return max;
}
```