# 1021. Remove Outermost Parentheses
## First solution
```
class Solution {
    public String removeOuterParentheses(String S) {
        char[] ans = new char[S.length()];
        int pointer = 0;
        
        int miss = 0;
        for(char c : S.toCharArray()) {
            if(c == '(') {
                if(miss != 0) {
                	ans[pointer] = c;
                	pointer++;
                }
                miss++;
            } else if (c == ')') {
            	miss--;
                if(miss != 0) {
                	ans[pointer] = c;
                	pointer++;
                }
            }
        }
        
        return new String(ans, 0, pointer);
    }
}
```
### Time complexity: O(n)
#### Where n is length of S
### Space complexity: O(n)
#### Where n is length of S
---
## Second solution
```
class Solution {
    public String removeOuterParentheses(String S) {
        int miss = 1;
		String ans = "";
		
		for(int i = 1; i < S.length(); i++) {
			if(S.charAt(i) == '(') {
				miss++;
			}else{
				miss--;
			}
			if(miss != 0) {
				ans = ans.concat(Character.toString(S.charAt(i)));
			}else {
				i++;
				miss++;
			}
		}
		
        return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of S
### Space complexity: O(n)
#### Where n is length of S