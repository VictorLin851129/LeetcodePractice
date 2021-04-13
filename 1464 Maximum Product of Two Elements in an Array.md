# 1464. Maximum Product of Two Elements in an Array
```
class Solution {
    public int maxProduct(int[] nums) {
        int first_max = 0, second_max = 0;
        
        for(int i : nums) {
        	if(i > second_max && i <= first_max) {
        		second_max = i;
        	}else if(i > first_max) {
        		second_max = first_max;
        		first_max = i;
        	}
        }
        System.out.println(first_max + " " + second_max);
        return (first_max - 1) * (second_max - 1);
    }
}
```
### Time complexity: O(n)
#### Where n is length of nums
### Space complexity: O(1)