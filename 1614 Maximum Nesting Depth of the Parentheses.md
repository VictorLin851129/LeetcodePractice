# 1614. Maximum Nesting Depth of the Parentheses
## Go through all characters in string. If '(' add 1; if ')' minus 1. And get the maximum count.
```
class Solution {
    public int maxDepth(String s) {
        int ans = 0;
        int count = 0;
        
        for(char c : s.toCharArray()) {
        	if(c == '(') {
        		count++;
        		if(ans < count) {
        			ans = count;
        		}
        	}else if(c == ')') {
        		count--;
        	}
        }
        
        return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of s
### Space complexity: O(1)