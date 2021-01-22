# 1720. Decode XORed Array
## A XOR B = C; A XOR C = B
### Time complexity: O(n)
#### n is length of encoded array
### Space complexity: O(n + 1) = O(n)
#### n is length of encoded array
```
class Solution {
    public int[] decode(int[] encoded, int first) {
        int [] ans = new int[encoded.length + 1];
		ans[0] = first;
		for(int i = 0; i < encoded.length; i++) {
			ans[i + 1] = ans[i] ^ encoded[i]; 
		}
		
		return ans;
    }
}
```