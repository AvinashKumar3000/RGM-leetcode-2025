# solution LC_566 reshape matrix

```python
class Solution:
    def matrixReshape(self, mat, r, c):
      m = len(mat)
      n = len(mat[0])
      if m*n != r*c:
        return mat
      temp = [0] * (m*n)
      k = 0
      for i in range(m):
        for j in range(n):
          temp[k] = mat[i][j]
          k+=1
        
      ans = [0] * r
      for i in range(r):
        row = [0] * c
        ans[i] = row
      k = 0
      for i in range(r):
        for j in range(c):
          ans[i][j] = temp[k]
          k+=1

      return ans
      

```


```c

/**
 * Return an array of arrays of size *returnSize.
 * The sizes of the arrays are returned as *returnColumnSizes array.
 * Note: Both returned array and *columnSizes array must be malloced, assume caller calls free().
 */
int** matrixReshape(
    int** mat, 
    int matSize, 
    int* matColSize, 
    int r, 
    int c, 
    int* returnSize, 
    int** returnColumnSizes
) {
    int m = matSize;
    int n = *matColSize;
   
    if(m*n != r*c) {
        *returnSize = m;
        *returnColumnSizes = (int*) calloc(m, sizeof(int));

        for(int i=0; i<m; i++)
            (*returnColumnSizes)[i] = n;
        return mat;
    }

    int temp[m*n];
    int k = 0;
    for(int i=0;i<m; i++) {
        for(int j=0; j<n; j++) {
            temp[k++] = mat[i][j];
        }
    }

    // answer
    int** ans = (int**) calloc(r, sizeof(int*));
    for(int i=0; i<r; i++){
        ans[i] = (int*) calloc(c, sizeof(int));
    }
    k = 0;
    for(int i=0;i<r; i++) {
        for(int j=0; j<c; j++) {
            ans[i][j] = temp[k++];
        }
    }

  
    *returnSize = r;
    *returnColumnSizes = (int*) calloc(r, sizeof(int));
  
    for(int i=0; i<r; i++)
        (*returnColumnSizes)[i] = c;
    return ans;
}
```


