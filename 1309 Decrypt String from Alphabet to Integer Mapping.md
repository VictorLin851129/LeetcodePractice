# 1309. Decrypt String from Alphabet to Integer Mapping
#### Use ASCII code to solve this problem.
```
class Solution {
    public String freqAlphabets(String s) {
        char[] ans = new char[s.length()];
		int index = 0;
		for(int i = 0; i < s.length(); i++) {
			if(s.charAt(i) != '#') {
				ans[index] = (char) (s.charAt(i) + 48);
			}else {
				index -= 2;
				ans[index] = (char)(Integer.parseInt(s.substring(i - 2, i)) + 96);
			}
			index++;
		}
		
		return new String(ans, 0, index);
    }
}
```
### Time complexity: O(n)
#### Where n is length of s
### Space complexity: O(n)
#### Where n is length of s