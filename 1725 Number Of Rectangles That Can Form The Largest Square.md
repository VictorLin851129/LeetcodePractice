# 1725. Number Of Rectangles That Can Form The Largest Square
```
class Solution {
    public int countGoodRectangles(int[][] rectangles) {
        int maxLen = Math.min(rectangles[0][0], rectangles[0][1]);
		int count = 1;
		for(int i = 1; i < rectangles.length; i++) {
			int compVal = Math.min(rectangles[i][0], rectangles[i][1]);
			if(maxLen < compVal) {
				maxLen = compVal;
				count = 1;
			}else if(maxLen == compVal) {
				count++;
			}
		}
		
		return count;
    }
}
```
### Time complexity: O(n)
#### Where n is length of rectangles
### Space complexity: O(1)