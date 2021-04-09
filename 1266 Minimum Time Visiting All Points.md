# 1266. Minimum Time Visiting All Points
```
class Solution {
    public int minTimeToVisitAllPoints(int[][] points) {
        int ans = 0;
		
		for(int i = 1; i < points.length; i++) {
			ans += Math.max(Math.abs(points[i][0] - points[i - 1][0]), Math.abs(points[i][1] - points[i - 1][1]));
		}
		
        return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of points
### Space complexity: O(1)