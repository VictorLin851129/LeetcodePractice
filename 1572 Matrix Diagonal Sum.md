# 1572. Matrix Diagonal Sum
```
class Solution {
    public int diagonalSum(int[][] mat) {
        int front = 0, rear = mat[0].length - 1;
		int ans = 0;
		
		for(int[] row : mat) {
			ans += front == rear ? row[front] : row[front] + row[rear];
//			if(front == rear) {
//				ans += row[front];
//			}else {
//				ans += row[front] + row[rear];
//			}
			front++;
			rear--;
		}
		
		return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of mat[]
### Space complexity: O(1)