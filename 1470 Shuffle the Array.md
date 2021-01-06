# 1470. Shuffle the Array
## Move each element to the correct place
## First solution
```
class Solution {
    public int[] shuffle(int[] nums, int n) {
        int [] results = new int[nums.length];
        for(int i = 0; i < n; i++) {
            for(int j = 0; j < nums.length / n; j++) {
                results[j + i * nums.length / n] = nums[i + j * n];
            }
        }
        return results;
    }
}
```

### Time complexity: O(2n) = O(n)
#### 2n : Because nums.length / n is always equals to 2
#### n is length of nums array
### Space complexity: O(n)
#### n is length of nums array
---
## Final solution

```
class Solution {
    public int[] shuffle(int[] nums, int n) {
        int [] results = new int[nums.length];
		int x = 0, y = n;
		for(int i = 0; i < nums.length; i++) {
			if(i % 2 == 0) {
				results[i] = nums[x++];
			}else {
				results[i] = nums[y++];
			}
		}
		return results;
    }
}
```
### Time complexity: O(n)
#### n is length of nums array
### Space complexity: O(n)
#### n is length of nums array



