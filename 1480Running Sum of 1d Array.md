# 1480. Running Sum of 1d Array
## Add previous number in the array
### Time complexity: O(n)
#### n is length of nums array
### Space complexity: O(1)
```
class Solution {
    public int[] runningSum(int[] nums) {
        for(int i = 1; i < nums.length; i++) {
			nums[i] += nums[i - 1];
		}
		return nums;
    }
}
```