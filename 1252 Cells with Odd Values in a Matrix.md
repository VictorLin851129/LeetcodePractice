# 1252. Cells with Odd Values in a Matrix
#### Check if each sum of col and row is odd, then use exclusive OR to get the result.
## Solution
```
class Solution {
    public int oddCells(int m, int n, int[][] indices) {
        int row_odd = 0, col_odd = 0;
        int[] row = new int[m];
        int[] col = new int[n];
        
        for(int i = 0; i < indices.length; i++) {
        	row[indices[i][0]] = row[indices[i][0]] == 1 ? 0 : 1;
        	col[indices[i][1]] = col[indices[i][1]] == 1 ? 0 : 1;
        	row_odd += row[indices[i][0]] == 1 ? 1 : -1;
        	col_odd += col[indices[i][1]] == 1 ? 1 : -1;
        }
   
		return row_odd * n + col_odd * m - 2 * row_odd * col_odd;
    }
}
```
### Time complexity: O(n)
#### Where n is length of indexes
### Space complexity: O(m + n)