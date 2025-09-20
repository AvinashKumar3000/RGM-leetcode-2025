# solution 

## 1832. Check if the Sentence Is Pangram

```c 
bool checkIfPangram(char* sentence) {
    int freq[26] = {0};
    int n = strlen(sentence);
    for(int i=0; i<n; i++){
    	char ch = sentence[i];
    	freq[ch-'a']++;
    }
    for(int i=0; i<26; i++){
    	if( freq[i] == 0 )
    		return false;
    }
    return true;
}	
```