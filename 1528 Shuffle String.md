# 1528. Shuffle String
## Use for loop to assign string's index
### Time complexity: O(n + n + n) = O(n)
#### n is length of string
### Space complexity: O(n)
#### n is length of string
```
class Solution {
    public String restoreString(String s, int[] indices) {
        char[] SortS = s.toCharArray();
		for(int i = 0; i < indices.length; i++) {
			SortS[indices[i]] = s.charAt(i);
		}
	    return String.valueOf(SortS);
    }
}
```