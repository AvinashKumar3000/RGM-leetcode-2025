# solution 1

## simple and using extra array ( temp )

```c    
void reverseString(char* s, int sSize) {
    int n = sSize;
    int temp[n];
    int k = 0;
    for(int i=n-1; i>=0; i--)
        temp[k++] = s[i];
    for(int i=0; i<n; i++)
        s[i] = temp[i];
}
```

## solution ( left and right pointer )

```c
void reverseString(char* s, int sSize) {
    int n = sSize;
    int left = 0;
    int right = n-1;
    while(left < right) {
        int temp = s[left];
        s[left] = s[right];
        s[right] = temp;
        left++;
        right--;
    }
}
```

## solution ( formula ( n-i-1 ) )

```c
void reverseString(char* s, int sSize) {
    int n = sSize;
    for(int i=0; i<(n/2); i++){
        int temp = s[i];
        s[i] = s[n-i-1];
        s[n-i-1] = temp;
    }
}
```
