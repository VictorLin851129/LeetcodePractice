# 1295. Find Numbers with Even Number of Digits
## First solution
```
class Solution {
    public int findNumbers(int[] nums) {
        int ans = 0;
        
        for(int i : nums) {
        	ans += Integer.toString(i).length() % 2 == 0 ? 1 : 0;
        }
       
        return ans;
    }
}
```
### Time complexity: O(n)
#### Where n is length of nums
### Space complexity: O(1)