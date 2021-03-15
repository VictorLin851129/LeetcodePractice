# 1389. Create Target Array in the Given Order
## Use list to insert value to correct index, then transfer it to array

```
class Solution {
    public int[] createTargetArray(int[] nums, int[] index) {
        List<Integer> ans = new ArrayList<Integer>();
		
		for(int i = 0; i < nums.length; i++) {
			ans.add(index[i], nums[i]);
		}
		
		int[] array = new int[ans.size()];
		
		for(int i = 0; i < ans.size(); i++) {
			array[i] = ans.get(i);
		}
		
		return array;
    }
}
```

### Time complexity: O(n^2)
#### Where n is length of nums
##### list.add(index, element) -> avg time complexity: O(n)
### Space complexity: O(n)
#### Where n is length of nums