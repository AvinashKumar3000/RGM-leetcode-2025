# solution LC_2373

```c

int** largestLocal(
	int** grid, 
	int   gridSize, 
	int*  gridColSize, 
	int*  returnSize, 
	int** returnColumnSizes
) {
   int n = gridSize;
	 int** ans = (int**) calloc((n-2), sizeof(int*));

	 for(int i=0; i<n-2; i++){
	    int* row = (int*) calloc((n-2), sizeof(int));
	    for(int j=0; j<n-2; j++) {
	    			int max = 0;
	    			for(int x=i; x<i+3; x++) {
		    			for(int y=j; y<j+3; y++) {
		    					 if (grid[x][y] > max)
		    					 		max = grid[x][y];
		    			}
	    			}
	    			row[j] = max;
	    }
	    ans[i] = row;
	 }

	 *returnSize = n-2;
	 *returnColumnSizes = (int*) calloc((n-2), sizeof(int));	 
	 for(int i=0; i<n-2; i++){
	 	  (*returnColumnSizes)[i] = n-2; 
	 }
	 return ans;
}
```

```python
class Solution:
  def largestLocal(self, grid):
    n = len(grid)
    res = [0] * (n-2)
    for i in range(n-2):
      row = [0] * (n-2)
      for j in range(n-2):
        max_val = 0
        for x in range(i,i+3):
          for y in range(j,j+3):
            if grid[x][y] > max_val:
              max_val = grid[x][y]
        row[j] = max_val
        res[i] = row
    return res

```
