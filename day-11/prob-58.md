# 1576. Replace All ?'s to Avoid Consecutive Repeating Characters

```c
char* modifyString(char* s) {
	int n = strlen(s);
    char arr[] = {'a','b','c'};
    for(int i=0; i<n; i++){
		if(s[i]=='?'){
		    for(int j=0; j<3; j++){
		    	if(i>0 && s[i-1]==arr[j])
		    		continue;
		    	if(i<n-1 && s[i+1]==arr[j])
		    		continue;
		    	s[i] = arr[j];
		    }
        }
	}
	return s;
}
```