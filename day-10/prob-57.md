# solution 3330. Find the Original Typed String I

```c
int possibleStringCount(char* word) {
    int count = 1;
    int n = strlen(word);
    for(int i=0; i<n-1; i++){
    	if(word[i]==word[i+1])
    		count++;
    }
    return count;
}
```
