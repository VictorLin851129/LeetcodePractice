# 728. Self Dividing Numbers
```
class Solution {
    public List<Integer> selfDividingNumbers(int left, int right) {
        List<Integer> ans = new ArrayList<Integer>();
        
        for(; left <= right; left++) {
        	int temp = left;
        	boolean flag = true;
        	
        	if(left % 10 == 0) {
        		continue;
        	}
        	
        	while(temp > 1) {
        		if((temp % 10 == 0) || (left % (temp % 10) != 0)) {
        			flag = false;
        			break;
        		}
        		temp /= 10;
        	}
        	
        	if(flag) {
        		ans.add(left);
        	}
        }
        
		return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of (right - left + 1)
### Space complexity: O(n)
#### Where n is length of (right - left + 1)