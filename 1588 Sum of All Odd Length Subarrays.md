# 1588. Sum of All Odd Length Subarrays
## 1. Follow the rule and do it step by step.
## 2. The value in the middle will have more times to be picked , and both side have the same chances to be picked. Concept like pascal's triangle .
## First solution
```
class Solution {
    public int sumOddLengthSubarrays(int[] arr) {
        int ans = 0, odd = 1;
		while(odd <= arr.length){
			for(int str = 0; str < arr.length; str++) {
				if(str + odd <= arr.length) {
					for(int i = str;  i < str + odd; i++) {
						ans += arr[i];
					}
				}else {
					break;
				}
			}
			odd += 2;
		}
		
		return ans;
    }
}
```
### Time complexity: O(n^3)
#### Where n is length of arr
### Space complexity: O(1)
---
## Second solution
```
class Solution {
    public int sumOddLengthSubarrays(int[] arr) {
        int i, s = 0;
        int l = arr.length;
        int start[] = new int[l];
        int end[] = new int[l];
        for(i = 0; i < l; i++){
            start[i] = l - i;
            end[i] = i + 1;
            s += (arr[i]) * ((start[i] * end[i] % 2 == 0 ? (start[i] * end[i]) / 2 : (start[i] * end[i]) / 2 + 1));
        }
        return s;
    }
}
```
### Time complexity: O(n)
#### Where n is length of arr
### Space complexity: O(n)
#### Where n is length of arr