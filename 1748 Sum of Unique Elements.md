# 1748. Sum of Unique Elements
```
class Solution {
    public int sumOfUnique(int[] nums) {
        if(nums.length == 1) {
			return nums[0];
		}
		Arrays.sort(nums);
		int ans = (nums[0] == nums[1]) ? 0 : nums[0];
		int temp = nums[0];
		for(int i  = 0; i < nums.length; i++) {
			if(nums[i] == temp) {
				continue;
			}
			if((i < nums.length - 1) && (nums[i] != nums[i + 1])) {
				ans += nums[i];
				temp = nums[i];
			}else if(i == nums.length - 1) {
				ans += nums[i];
			}else {
				temp = nums[i];
			}
		}
		
        return ans;
    }
}
```
### Time complexity: O(nlogn + n) = O(nlogn)
#### Where n is length of nums
### Space complexity: O(1)