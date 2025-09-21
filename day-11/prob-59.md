# 59. LC_2124 Check if All A's Appears Before All B's

```c
bool checkString(char* s) {
    bool isSeen = false;
    int n = strlen(s);
    for(int i=0; i<n ;i++){
        if(s[i]=='b')
            isSeen = true;
        if(isSeen && s[i]=='a')
            return false;
    }
    return true;
}
```
