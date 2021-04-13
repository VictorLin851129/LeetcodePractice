# 1304. Find N Unique Integers Sum up to Zero
```
class Solution {
    public int[] sumZero(int n) {
        int[] ans = new int[n];
		
		for(int i = n / 2 * -1, count = 0; count < n ; i++) {
			if(i == 0 && n % 2 == 0) {
				continue;
			}
			ans[count] = i;
			count++;
		}
		
		return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of n
### Space complexity: O(n)
#### Where n is length of n