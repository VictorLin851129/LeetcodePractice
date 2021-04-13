# 1374. Generate a String With Characters That Have Odd Counts
```
class Solution {
    public String generateTheString(int n) {
        StringBuilder ans = new StringBuilder(n);
        
		for(int i = 0; i < n - 1; i++) {
        	ans.append('a');
        }
        ans.append(n % 2 == 0 ? 'b' : 'a');
		
		return ans.toString();
    }
}
```
### Time complexity: O(n)
#### Where n is length of n
### Space complexity: O(n)
#### Where n is length of n