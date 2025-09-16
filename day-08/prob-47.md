# solution LC_566 reshape matrix

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
