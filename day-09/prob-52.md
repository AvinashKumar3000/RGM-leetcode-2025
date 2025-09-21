# solution LC_541

```c
char* reverseStr(char* s, int k) {
 	int n = strlen(s);
 	int last_index = n-1;
 	for( int i=0; i<n; i=i+2*k ) {
 		int left = i;
 		int right = i+k-1;
 		if( right > last_index )
 			right = last_index; 
 		while(left < right){
 			char temp = s[left];
 			s[left] = s[right];
 			s[right] = temp;
 			left++;
 			right--;
 		}
 	}   
 	return s;
}
```