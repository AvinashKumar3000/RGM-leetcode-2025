# solution

```c
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* luckyNumbers(
  int** matrix,
  int matrixSize,
  int* matrixColSize,
  int* returnSize
) {
    int** m = matrix;
    int r = matrixSize;
    int c = *matrixColSize;
    int* ans = (int*) malloc((c*r) * sizeof(int));
    int k = 0;
    for(int i=0; i<r; i++) {
      // STEP 01: find min from row:
      int min_idx = 0;
      int min = m[i][0];  // taking first val
      for(int j=1; j<c; j++){
          if( m[i][j] < min ){
            min = m[i][j];
            min_idx = j;
          }
      }
      // STEP 02: find max in that col
      int max = m[0][min_idx];
      for(int j=1; j<r; j++){
          if( m[j][min_idx] > max ){
              max = m[j][min_idx];
          }
      }
      // STEP 03: min, max
      //  check condition
      if( min == max ){
          // add in ans array
          ans[k++] = min;
      }
    }
    *returnSize = k;
    return ans;
}
```
