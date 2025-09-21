# LC_383  Ransom Note

```c
bool canConstruct(char* ransomNote, char* magazine) {
    int freq[26] = {0};
    for(int i=0; magazine[i]!='\0'; i++){
        char ch = magazine[i];
        freq[ch-'a']++;
    }
    for(int i=0; ransomNote[i]!='\0'; i++){
        char ch = ransomNote[i];
        freq[ch-'a']--;
        if(freq[ch-'a'] <0)
            return false;
    }
    return true;
}
```
