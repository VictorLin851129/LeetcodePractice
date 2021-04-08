# 1684. Count the Number of Consistent Strings
## 1. Follow the rule and do it step by step.
## 2. The value in the middle will have more times to be picked , and both side have the same chances to be picked. Concept like pascal's triangle .
## First solution
```
class Solution {
    public int countConsistentStrings(String allowed, String[] words) {
        int ans = 0;
		for(int i = 0; i < words.length; i++) {
			for(int j = 0; j < allowed.length(); j++) {
				words[i] = words[i].replaceAll(Character.toString(allowed.charAt(j)), "");
                if(words[i].length() == 0) {
					break;
				}
			}
			if(words[i].length() == 0) {
				ans++;
			}
		}
		
		return ans;
    }
}
```
### Time complexity: O(26 * m * n)
#### Where n is length of words array
#### Where m is length of character of word for replaceAll
#### Allowed at most 26 alphabets
### Space complexity: O(1)
---
## Second solution
```
class Solution {
    public int countConsistentStrings(String allowed, String[] words) {
       int ans = words.length;
		int arr[] = new int[26];
		
		for(char c : allowed.toCharArray()) {
			arr[c - 'a'] = 1;
		}
		
		for(String s : words) {
			for(char c : s.toCharArray()) {
				if(arr[c - 'a'] != 1) {
					ans--;
					break;
				}
			}
		}
		
		return ans;
    }
}
```
### Time complexity: O(m * n)
#### Where n is length of words array
#### Where m is length of character of word 
### Space complexity: O(1)
#### arr array only need 26 places