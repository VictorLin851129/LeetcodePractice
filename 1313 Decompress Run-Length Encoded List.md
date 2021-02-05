# 1313. Decompress Run-Length Encoded List
## Check how many times it nums[i + 1] need to be repeat in nums[i]
## First solution
```
class Solution {
    public int[] decompressRLElist(int[] nums) {
        int arrSize = 0;
		for(int i = 0; i < nums.length; i+=2) {
			arrSize += nums[i];
		}
		
		int[] ans = new int[arrSize];
		int count = 0;
		for(int i = 0; i < nums.length; i+=2) {
			for(int j = 0; j < nums[i]; j++) {
				ans[count++] = nums[i + 1];
			}
		}
		
		return ans;
    }
}
```

### Time complexity: O((n / 2) + (n / 2) * m) = O(n * m)
#### Where n is length of nums
#### Where m is times we need to repeat 
### Space complexity: O(m)
#### Where m is times we need to repeat 
---
## Second solution
```
class Solution {
    public int[] decompressRLElist(int[] nums) {
        int arrSize = 0;
        for (int i = 0; i < nums.length; i += 2) {
            arrSize += nums[i];
        }
        
        int[] result = new int[arrSize];

        int startIdx = 0;
        for (int i = 0; i < nums.length; i += 2) {
            Arrays.fill(result, startIdx, startIdx + nums[i], nums[i + 1]);
            startIdx += nums[i];
        }
        return result;
    }
}
```
### Time complexity: O((n / 2) + (n / 2) * m) = O(n * m)
#### Where n is length of nums
#### Where m is times we need to repeat 
### Space complexity: O(m)
#### Where m is times we need to repeat 




