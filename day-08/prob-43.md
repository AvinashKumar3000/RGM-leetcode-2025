# solution.43 LC_1260 Shift 2D Grid.

```c
int** shiftGrid(int** grid,int gridSize,int* gridColSize,int k,int* returnSize,int** returnColumnSizes) {
    int r = gridSize;
    int c = *gridColSize;
    int n = r*c;
    int temp[n];
    int idx=0;
    for(int i=0; i<r; i++){
        for(int j=0; j<c; j++)
            temp[idx++] = grid[i][j];
    }
    k = k%n;
    int start = k==0 ? 0 : n-k;
    for(int i=0; i<r; i++){
        for(int j=0; j<c; j++){
            grid[i][j] = temp[start];
            start = (start+1)%n;
        }
    }
    *returnSize = r;
    *returnColumnSizes = (int*) malloc(r * sizeof(int) );
    for(int i=0; i<r; i++)
        (*returnColumnSizes)[i] = c; 
    return grid;
}
```