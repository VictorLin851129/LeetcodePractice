# 1370. Increasing Decreasing String
## First solution
```
class Solution {
    public String sortString(String s) {
        StringBuilder ans = new StringBuilder();
		char[] alp = new char[26];
		int length = s.length();
		
		for(char c : s.toCharArray()) {
			alp[c - 97]++;
		}
		
		boolean reverse = false;
		while(length > 0) {
			
			if(reverse) {
				for(int i = alp.length - 1; i >= 0; i--) {
					if(alp[i] > 0) {
						ans.append((char)(i + 97));
						length--;
						alp[i]--;
					}
				}
			}else {
				for(int i = 0; i < alp.length; i++) {
					if(alp[i] > 0) {
						ans.append((char)(i + 97));
						length--;
						alp[i]--;
					}
				}
			}
			reverse = !reverse;
		}
		
		return ans.toString();
    }
}
```
### Time complexity: O(n)
#### Where n is length of s
### Space complexity: O(1)
#### Need length of alp places
---
## Second solution
```
class Solution {
    public String sortString(String s) {
        StringBuilder ans = new StringBuilder();
		boolean flag = true;
		char[] c_arr = s.toCharArray();
		Arrays.sort(c_arr);
		s = new String(c_arr, 0, c_arr.length);
		while(s.length() > 0) {
			StringBuilder temp = new StringBuilder();
			c_arr = s.toCharArray();
        	char current = c_arr[0];
        	ans.append(current);
            for(int i = 1; i <  c_arr.length; i++) {
            	if(flag) {
	        		if(c_arr[i] > current) {
	        			current = c_arr[i];
	        			ans.append(current);
	        		}else {
	        			temp.append(c_arr[i]);
	        		}
        		}else {
        			if(c_arr[i] < current) {
	        			current = c_arr[i];
	        			ans.append(current);
	        		}else {
	        			temp.append(c_arr[i]);
	        		}
        		}
        	}
            flag = !flag;
            s = temp.reverse().toString();
		}
        
		return ans.toString();
    }
}
```
### Time complexity: O(n)
#### Where n is length of s
### Space complexity: O(n)
#### Where n is length of s