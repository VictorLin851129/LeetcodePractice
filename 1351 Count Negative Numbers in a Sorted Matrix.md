# 1351. Count Negative Numbers in a Sorted Matrix
## First solution
### Solve problem from bottom left
```
class Solution {
    public int countNegatives(int[][] grid) {
        int m = grid.length, n = grid[0].length, r = m - 1, c = 0, cnt = 0;
        while (r >= 0 && c < n) {
            if (grid[r][c] < 0) {
                --r;
                cnt += n - c; // there are n - c negative numbers in current row.
            }else {
                ++c;
            }
        }
        return cnt;
    }
}
```
### Time complexity: O(n)
#### Where n is length of grid[]
### Space complexity: O(1)
---
## Second solution
### Solve problem from bottom right
```
class Solution {
    public int countNegatives(int[][] grid) {
        int ans = 0;
        
        for(int i = grid.length - 1; i >= 0; i--) {
        	if(grid[i][grid[i].length - 1] > 0) {
        		break;
        	}
        	for(int j = grid[i].length - 1; j >= 0; j--) {
        		if(grid[i][j] >= 0) {
        			break;
        		}else {
        			ans++;
        		}
        	}
        }
        
        return ans;
    }
}
```
### Time complexity: O(m * n)
#### Where m is length of grid
#### Where n is length of grid[]
### Space complexity: O(1)