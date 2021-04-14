# 1768. Merge Strings Alternately
```
class Solution {
    public String mergeAlternately(String word1, String word2) {
        StringBuilder ans = new StringBuilder();
        
        int count = 0;
        for(count = 0; count < word1.length() && count < word2.length(); count++) {
        	ans.append(word1.charAt(count));
        	ans.append(word2.charAt(count));
        }
        
        if(count < word1.length()) {
        	for(; count < word1.length(); count++) {
        		ans.append(word1.charAt(count));
        	}
        }
        
        if(count < word2.length()) {
        	for(; count < word2.length(); count++) {
        		ans.append(word2.charAt(count));
        	}
        }
        
        return ans.toString();
    }
}
```
### Time complexity: O(n)
#### Where n is max(word1, word2)
### Space complexity: O(n)
#### Where n is length of word1 + word2