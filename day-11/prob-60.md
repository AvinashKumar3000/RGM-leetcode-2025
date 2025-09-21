# LC_771  jewels and stones

```c
int numJewelsInStones(char* jewels, char* stones) {
    int n1 = strlen(jewels);
    int n2 = strlen(stones);
    int c=0;
    for(int i=0; i<n1; i++){
        for(int j=0; j<n2; j++){
            if(jewels[i]==stones[j])
                c++;
        }
    }
    return c;
}
```