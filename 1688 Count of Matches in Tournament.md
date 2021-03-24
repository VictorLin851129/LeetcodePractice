# 1688. Count of Matches in Tournament
```
class Solution {
    public int numberOfMatches(int n) {
        int ans = 0;
		
		while(n > 1) {
			ans += n / 2;
			if(n % 2 == 1) {
				n = n / 2 + 1;
			}else {
				n = n / 2;
			}
		}
		
        return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of input n
### Space complexity: O(1)