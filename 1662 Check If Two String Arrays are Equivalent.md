# 1662. Check If Two String Arrays are Equivalent
## concat all the sting in word1 and word2, then compare them
## First solution
```
class Solution {
    public boolean arrayStringsAreEqual(String[] word1, String[] word2) {
        String s1 = "", s2 = "";
		
		for(String s : word1) {
			s1 = s1.concat(s);
		}
		for(String s : word2) {
			s2 = s2.concat(s);
		}
        return s1.equals(s2);
    }
}
```

### Time complexity: O(n)
#### Where n is length of max(word1, word2)
### Space complexity: O(n)
#### Where n is length of max(str1 which is word1 after concat, str2 which is word2 after concat)
##### note: concat performance is better than operater '+'
---
## Second solution
```
class Solution {
    public boolean arrayStringsAreEqual(String[] word1, String[] word2) {
        StringBuilder s1 = new StringBuilder(), s2 = new StringBuilder();;
		for(String s : word1) {
			s1.append(s);
		}
		for(String s : word2) {
			s2.append(s);
		}
		
        return s1.toString().equals(s2.toString());
    }
}
```
### Time complexity: O(n)
#### Where n is length of max(word1, word2)
### Space complexity: O(n)
#### Where n is length of max(str1 which is word1 after append, str2 which is word2 after append)
##### StringBuilder's equals() is not same as equals() with String
##### StringBuilder's equals() compare reference, but String's equals() compare object 