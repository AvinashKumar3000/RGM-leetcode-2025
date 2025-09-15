# solution LC_1534

```c
  int abs(int x){
    if(x<0) return -x;
    return x;
}

int countGoodTriplets(
    int* arr, 
    int arrSize, 
    int a, 
    int b, 
    int c
){
    int count = 0;
    int n = arrSize;
    for(int i=0; i<n; i++){
        for(int j=i+1; j<n; j++){
            for(int k=j+1; k<n; k++){
                if(
                    abs(arr[i] - arr[j]) <= a &&
                    abs(arr[j] - arr[k]) <= b &&
                    abs(arr[i] - arr[k]) <= c
                ) count++;
            }
        }
    }
    return count;
}
```