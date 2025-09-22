# solution LC_374  Guess Number Higher or Lower

```c
/** 
 * Forward declaration of guess API.
 * @param  num   your guess
 * @return       -1 if num is higher than the picked number
 *                1 if num is lower than the picked number
 *               otherwise return 0
 * int guess(int num);
 */
int guess(int num);
int guessNumber(int n){
    long low  = 0;
    long high = n;
    while(low<=high){
        long mid = (low + high)/2;
        int res = guess(mid);
        if(res==0)
            return mid;
        else if( res==1 )
            low = mid+1;
        else
            high = mid-1;
    }
    return -1;
}
```
