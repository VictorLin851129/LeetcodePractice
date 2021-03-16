# 1221. Split a String in Balanced Strings
## If 'R' add 1, if 'L' minus 1. If counter equal 0, it means it get same amount of 'R' and 'L'

```
class Solution {
    public int balancedStringSplit(String s) {
        int check = 0, ans = 0;
		for(int i = 0; i < s.length(); i++) {
			if(s.charAt(i) == 'R') {
				check++;
			}else {
				check--;
			}
			if(check == 0)
				ans++;
		}
		
		return ans;
    }
}
```

### Time complexity: O(n)
#### Where n is length of string
### Space complexity: O(1)