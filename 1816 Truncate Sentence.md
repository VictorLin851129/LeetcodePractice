# 1816. Truncate Sentence
## First solution
```
class Solution {
    public String truncateSentence(String s, int k) {
        StringBuilder ans = new StringBuilder();
        
        for(char c : s.toCharArray()) {
        	if(c == ' ') {
        		if(k == 1)
        			break;
        		k--;
        	}
        	ans.append(c);
        }
		return ans.toString();
    }
}
```
### Time complexity: O(n)
#### Where n is length of s
### Space complexity: O(n)
#### Where n is length of s
---
## Second solution
```
class Solution {
    public String truncateSentence(String s, int k) {
        StringBuilder ans = new StringBuilder();
        
        for(int i = 0; i < k; i++) {
        	ans.append(s.split(" ")[i]);
        	if(i + 1 != k)
        		ans.append(" ");
        }
        
		return ans.toString();
    }
}
```
### Time complexity: O(n * k)
#### Where n is length of s
#### Where k is given k
### Space complexity: O(n)
#### Where n is length of s