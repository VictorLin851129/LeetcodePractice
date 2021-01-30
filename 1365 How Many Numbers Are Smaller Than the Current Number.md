# 1365. How Many Numbers Are Smaller Than the Current Number
## For each nums[i] you have to count the number of valid j's such that j != i and nums[j] < nums[i].
## First solution

```
class Solution {
    public int[] smallerNumbersThanCurrent(int[] nums) {
        int[] Sortnums = new int[nums.length];
		System.arraycopy(nums, 0, Sortnums, 0, nums.length);
		Arrays.sort(Sortnums);
		
		List<Integer> list = new ArrayList<>();
		for (int t : Sortnums) { 
            list.add(t); 
        } 
		
		for(int i = 0; i < nums.length; i++) {
			nums[i] = list.indexOf(nums[i]);
		}
		
		return nums;
    }
}
```

### Time complexity: O(n + nlogn + n + n) = O(nlogn)
#### n is length of nums[]
### Space complexity: O(2n)
#### n is length of nums[]
---
## Second solution

```
class Solution {
    public int[] smallerNumbersThanCurrent(int[] nums) {
		int[] numsCount = new int[101];
		int count = 0, temp = 0;
        
		for (int t : nums) { 
            numsCount[t] += 1;
        } 
		
		for (int t = 0; t < numsCount.length; t++) { 
			temp = numsCount[t];
            numsCount[t] = count;
            count += temp;
        } 
		
		for(int i = 0; i < nums.length; i++) {
			nums[i] = numsCount[nums[i]];
		}
		
		return nums;
    }
}
```
### Time complexity: O(n + m)
#### n is length of nums[]
#### m is max length of number which is 101
### Space complexity: O(n + m + 1)  = O(n + m)
#### m is max length of number which is 101
#### n is length of nums[]