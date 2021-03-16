# 1486. XOR Operation in an Array
## ^ represent XOR in java
```
class Solution {
    public int xorOperation(int n, int start) {
        int ans = 0;
		
		for(int i = 1; i <= n; i++) {
			ans ^= start;
			start += 2;
		}
		
		return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of n set in question
### Space complexity: O(1)