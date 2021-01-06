# 1672. Richest Customer Wealth
## Use for loop to calculate each row elements
### Time complexity: O(m*n)
### Space complexity: O(1)
```
class Solution {
    public int maximumWealth(int[][] accounts) {
        int maxVal = 0;
	    for(int i = 0; i < accounts.length; i++) {
			int sumVal = 0;
			for(int j = 0; j < accounts[0].length; j++) {
				sumVal += accounts[i][j];
			}
			if(sumVal > maxVal) {
				maxVal = sumVal;
			}
		}
		return maxVal;
    }
}
```