# 1299. Replace Elements with Greatest Element on Right Side
```
class Solution {
    public int[] replaceElements(int[] arr) {
        int max = arr[arr.length - 1];
		arr[arr.length - 1] = -1;
		
		for(int i = arr.length - 2; i >= 0; i--) {
			int temp = max;
			if(arr[i] > max) {
				max = arr[i];
			}
			arr[i] = temp;
		}
		
		return arr;
    }
}
```
### Time complexity: O(n)
#### Where n is length of arr
### Space complexity: O(1)