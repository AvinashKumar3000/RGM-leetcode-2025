# solution 

## 242. Valid Anagram

```c    
bool isAnagram(char* s, char* t) {
 	int freq[26];
 	int n1 = strlen(s);
 	for(int i=0; i<n1; i++){
 		char ch = s[i];
 		freq[ch-'a']++;
 	}   
 	int n2 = strlen(t);
 	for(int i=0; i<n2; i++){
 		char ch = t[i];
 		freq[ch-'a']--;
 	}   
 	for(int i=0; i<26; i++){
 		if ( freq[i]!=0 ) 
 			return false;
 	}
 	return true;
}
```